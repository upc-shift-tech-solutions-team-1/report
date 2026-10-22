# 6. Product Verification & Validation

## 6.1. Testing Suites & Validation

La estrategia de verificación y validación de AutoService contempla pruebas unitarias, pruebas de integración, pruebas de aceptación y escenarios automatizados mediante Behavior-Driven Development (BDD). Estas pruebas permiten comprobar el funcionamiento de los principales componentes de la aplicación y las reglas de negocio implementadas.

**Backend**

Para la verificación del backend se utilizó el proyecto `AutoServiceAW.API.Tests`, desarrollado con C# y .NET 10. Las pruebas fueron implementadas utilizando MSTest, Moq, ASP.NET Core TestServer y Reqnroll.

La selección de pruebas se realizó considerando la importancia de cada funcionalidad para el negocio, priorizando la gestión de órdenes de trabajo, las tareas de mantenimiento, la autenticación de usuarios y la administración de vehículos. Asimismo, se incorporaron pruebas para los demás Bounded Contexts según los comportamientos que se consideraron relevantes.

En total, se ejecutaron **92 pruebas automatizadas, con 92 aprobadas, 0 fallidas y 0 omitidas**, incluyendo nueve escenarios BDD implementados mediante Reqnroll.

![Resultado de ejecución de la suite automatizada del backend](../assets/images/chapter-6/chapter-6-backend-suite-summary.png)

*Figura 6.1. Ejecución satisfactoria de las 92 pruebas automatizadas del Backend de AutoService.*

Las pruebas de integración HTTP se realizaron con componentes reales de la API y dependencias simuladas mediante Moq. Por ello, estos resultados verifican los comportamientos seleccionados, pero no representan una validación completa con una base de datos MySQL real.

Las pruebas correspondientes a las aplicaciones Web y Mobile se documentarán por separado dentro de los siguientes apartados, conforme se implementen sus respectivos casos de prueba.

### 6.1.1. Core Entities Unit Tests

**Backend**

Las pruebas unitarias del backend se desarrollaron para verificar el comportamiento de las entidades, agregados y servicios de aplicación de AutoService. Se utilizó el patrón **Arrange, Act, Assert (AAA)**, que permite organizar cada prueba en tres etapas: preparación de los datos, ejecución de la funcionalidad y verificación del resultado esperado.

Para las pruebas de dominio se evaluaron reglas de negocio relacionadas con la creación y actualización de entidades, el cálculo de costos, la gestión del inventario y los cambios de estado de las órdenes de trabajo.

Se ejecutaron **28 pruebas unitarias correspondientes a entidades y agregados**, distribuidas entre los diferentes Bounded Contexts. Todas finalizaron satisfactoriamente.

![Pruebas unitarias de dominio del Backend](../assets/images/chapter-6/chapter-6-backend-unit-tests.png)

*Figura 6.2. Ejecución satisfactoria de 28 pruebas unitarias de entidades y agregados del Backend de AutoService.*

Adicionalmente, se implementaron pruebas de servicios de aplicación para verificar operaciones relacionadas con autenticación, gestión de vehículos y mantenimiento. Estas pruebas utilizan Moq para simular las dependencias externas y comprobar los resultados de los servicios de manera controlada.


Las pruebas unitarias de dominio se distribuyeron de la siguiente manera:

| Clase de prueba | Bounded Context | Cantidad | Comportamientos verificados |
|---|---|---:|---|
| `CustomerTests` | Customer Management | 2 | Creación y actualización de clientes. |
| `VehicleTests` | Fleet Management | 2 | Inicialización y actualización de vehículos. |
| `UserTests` | IAM | 2 | Creación de usuarios y actualización de contraseñas. |
| `InventoryItemTests` | Inventory Management | 4 | Cálculo del precio de compra, ingreso y consumo de stock, y validación de existencias insuficientes. |
| `MechanicTests` | Staff Coordination | 2 | Inicialización y actualización de información del mecánico. |
| `WorkshopTests` | Tenant Management | 1 | Creación del taller y generación de su identificador. |
| `TaskPartTests` | Workshop Operations | 5 | Validación de cantidades, normalización de información y cálculo de costos de materiales. |
| `TaskTests` | Workshop Operations | 5 | Inicialización de tareas, actualización de datos técnicos y cálculo de costos y márgenes. |
| `WorkOrderTests` | Workshop Operations | 5 | Creación de órdenes, actualización del checklist y control de cambios de estado. |
| **Total** | | **28** | **Pruebas unitarias de entidades y agregados.** |

En Workshop Operations se concentraron las pruebas de dominio relacionadas con órdenes de trabajo y tareas de mantenimiento. Se verificaron los cálculos de costos, la asignación de materiales, las actualizaciones de información técnica y los cambios de estado de las órdenes.

En Inventory Management se evaluó el aumento y disminución de existencias, incluyendo el rechazo de operaciones cuando la cantidad solicitada supera el stock disponible.

**Pruebas de servicios de aplicación**

Adicionalmente, se implementaron pruebas para servicios de aplicación de IAM, Fleet Management y Workshop Operations, así como para la construcción de resúmenes de Public Tracking.

Estas pruebas utilizan Moq cuando es necesario reemplazar las dependencias externas y verificar el comportamiento de los componentes sin establecer una conexión real con MySQL.

| Bounded Context | Clases de prueba | Cantidad |
|---|---|---:|
| IAM | `AuthServiceTests` | 2 |
| Fleet Management | `VehicleServiceTests` | 4 |
| Workshop Operations | `TaskServiceTests`, `WorkshopOperationsServiceTests` | 9 |
| Public Tracking | `TrackingSummaryFactoryTests` | 8 |
| **Total** | | **23** |

En IAM se verificó el registro e inicio de sesión de usuarios, incluyendo la gestión de contraseñas y la generación de tokens JWT.

En Fleet Management se evaluaron operaciones de gestión de vehículos realizadas a través del servicio de aplicación.

En Workshop Operations se verificaron procesos de creación y actualización de tareas y órdenes de trabajo, utilizando repositorios simulados.

Finalmente, en Public Tracking se evaluó la construcción de la información de seguimiento que se presenta al cliente durante el mantenimiento de su vehículo.

Estas pruebas complementan las verificaciones de dominio y permiten comprobar el comportamiento de los servicios y componentes de aplicación de manera controlada.



### 6.1.2. Core Integration Tests

**Backend**

Las pruebas de integración del backend se implementaron para verificar la comunicación entre los controladores REST y los servicios de aplicación de AutoService.

Para estas pruebas se utilizó `TestServer` de ASP.NET Core, que permite ejecutar solicitudes HTTP contra una aplicación configurada en memoria. Asimismo, se utilizó Moq para simular repositorios y otras dependencias externas, sin requerir una conexión a la base de datos MySQL.

Se ejecutaron **15 pruebas seleccionadas mediante el filtro `IntegrationTests`**, todas aprobadas, con 0 fallidas y 0 omitidas.

![Ejecución de las pruebas de integración HTTP del Backend](../assets/images/chapter-6/chapter-6-backend-integration-tests.png)

*Figura 6.3. Ejecución satisfactoria de 15 pruebas de integración HTTP del Backend de AutoService.*

Las pruebas realizadas abarcaron principalmente los siguientes Bounded Contexts:

| Bounded Context | Funcionalidades verificadas |
|---|---|
| IAM | Inicio de sesión mediante la API REST y devolución de los datos de autenticación. |
| Fleet Management | Operaciones de gestión de vehículos mediante solicitudes HTTP. |
| Workshop Operations | Creación y actualización de tareas, operaciones sobre órdenes de trabajo y comunicación con los servicios correspondientes. |
| Inventory Management | Recepción de materiales y validación de permisos para modificar el inventario. |
| Public Tracking | Consulta de información de seguimiento mediante la API REST. |

En Workshop Operations se verificaron operaciones relacionadas con el registro de tareas, la gestión de órdenes de trabajo y el consumo de materiales asociado al mantenimiento de vehículos.

En Inventory Management se implementaron dos pruebas adicionales para validar la recepción de materiales. La primera comprueba que un administrador pueda registrar una entrada de cinco unidades, aumentando el stock de 10 a 15. La segunda verifica que un usuario con rol de mecánico reciba una respuesta `403 Forbidden` cuando intenta registrar una recepción, sin realizar modificaciones en el inventario.

Las pruebas también permiten verificar respuestas HTTP, como `200 OK`, `201 Created`, `403 Forbidden` y `404 Not Found`, según la operación y las condiciones evaluadas.

Este enfoque permitió comprobar la integración de los componentes HTTP y la lógica de aplicación para los casos seleccionados. Sin embargo, al utilizar dependencias simuladas, no constituye una prueba de integración completa con la persistencia real en MySQL.



### 6.1.3. Core Behavior-Driven Development

**Backend**

Para verificar los principales comportamientos del negocio de AutoService se utilizó el enfoque Behavior-Driven Development (BDD), que permite describir las funcionalidades del sistema mediante escenarios escritos en lenguaje Gherkin.

Los escenarios fueron implementados utilizando Reqnroll, integrado con MSTest, permitiendo automatizar su ejecución dentro del proyecto `AutoServiceAW.API.Tests`.

Se desarrollaron **9 escenarios BDD automatizados**, distribuidos entre tres Bounded Contexts: Workshop Operations, Fleet Management e IAM.

| Bounded Context | Escenarios BDD | Funcionalidades verificadas |
|---|---:|---|
| Workshop Operations | 4 | Registro y actualización de tareas, avance de órdenes de trabajo y validación de tareas no aprobadas. |
| Fleet Management | 3 | Registro, actualización y consulta de vehículos. |
| IAM | 2 | Inicio de sesión con credenciales válidas e inválidas. |
| **Total** | **9** | **Escenarios automatizados mediante Reqnroll.** |

Los escenarios fueron organizados mediante archivos `.feature` y sus correspondientes clases de Step Definitions, donde se implementaron los pasos `Given`, `When` y `Then`.

**Workshop Operations**

En este Bounded Context se implementaron cuatro escenarios relacionados con la gestión de tareas de mantenimiento y el ciclo de vida de las órdenes de trabajo.

Los escenarios verifican el registro de tareas, la actualización de su estado y tiempo estimado, el avance de una orden cuando se completa una tarea aprobada y la restricción que impide iniciar tareas sin aprobación.

**Fleet Management**

Se implementaron tres escenarios para verificar las principales operaciones de gestión de vehículos.

Estos escenarios comprueban el registro de un vehículo asociado a un cliente, la actualización de su información operativa y técnica, y la consulta de vehículos mediante su identificador.

**IAM**

En IAM se implementaron dos escenarios relacionados con el inicio de sesión y la validación de credenciales.

El primero verifica que un administrador pueda iniciar sesión correctamente y obtener un token JWT con su rol correspondiente. El segundo comprueba que una contraseña incorrecta sea rechazada y que no se entregue un token de acceso.


**Estructura de los escenarios BDD**

Los archivos Gherkin y sus implementaciones se encuentran organizados dentro de las carpetas BDD de cada Bounded Context.

![Estructura BDD de Fleet Management e IAM](../assets/images/chapter-6/chapter-6-backend-bdd-structure-fleet-iam.png)

*Figura 6.4. Organización de los archivos Gherkin y Step Definitions de Fleet Management e IAM.*

![Estructura BDD de Workshop Operations](../assets/images/chapter-6/chapter-6-backend-bdd-structure-workshop.png)

*Figura 6.5. Organización de los archivos Gherkin y Step Definitions de Workshop Operations.*

**Resultados de ejecución**

Los nueve escenarios fueron ejecutados mediante MSTest y Reqnroll, obteniendo resultados satisfactorios en todos los casos.

![Resultados de los escenarios BDD automatizados](../assets/images/chapter-6/chapter-6-backend-bdd-results.png)

*Figura 6.6. Ejecución satisfactoria de los nueve escenarios BDD automatizados del Backend de AutoService.*

La ejecución registró **9 escenarios aprobados, 0 fallidos y 0 omitidos**.

Estas pruebas forman parte de las 92 pruebas automatizadas de la suite del Backend. Su implementación permite verificar los comportamientos seleccionados desde una perspectiva funcional, utilizando los controladores y servicios correspondientes con dependencias simuladas cuando resulta necesario.


### 6.1.4. Core System Tests

**Backend**

Para complementar las pruebas unitarias y de integración, se implementaron pruebas de aceptación orientadas a verificar flujos funcionales de AutoService.

Estas pruebas permiten comprobar el comportamiento de diferentes componentes del backend durante la ejecución de operaciones relacionadas con el registro de usuarios, la autenticación, la gestión de vehículos y las tareas de mantenimiento.

Se ejecutaron **5 pruebas de aceptación automatizadas**, distribuidas entre IAM, Fleet Management y Workshop Operations.

| Bounded Context | Pruebas de aceptación | Funcionalidades verificadas |
|---|---:|---|
| IAM | 2 | Registro de taller, autenticación mediante JWT y restricciones de acceso según el rol del usuario. |
| Fleet Management | 2 | Operaciones funcionales relacionadas con el registro y la gestión de vehículos. |
| Workshop Operations | 1 | Flujo de tareas de mantenimiento asociado a órdenes de trabajo. |
| **Total** | **5** | **Pruebas de aceptación automatizadas.** |

**Pruebas de aceptación de IAM**

En IAM se verificaron dos flujos relacionados con la autenticación y autorización de usuarios.

El primero comprueba el registro de un taller, el inicio de sesión de su administrador y el acceso a una operación protegida mediante un token JWT.

El segundo verifica que un usuario con rol de mecánico, aunque cuente con un token de autenticación válido, no pueda acceder a una operación reservada para administradores. En este caso, el sistema debe responder con el código HTTP `403 Forbidden`.

**Pruebas de aceptación de Fleet Management**

Las pruebas de aceptación de Fleet Management se enfocaron en verificar operaciones relacionadas con la administración de vehículos, utilizando solicitudes HTTP y comprobando las respuestas del sistema.

**Pruebas de aceptación de Workshop Operations**

En Workshop Operations se verificó un flujo funcional relacionado con la gestión de tareas de mantenimiento y su asociación con las órdenes de trabajo.

**Resultados de ejecución**

Las cinco pruebas fueron ejecutadas mediante MSTest, utilizando los componentes correspondientes del backend y dependencias simuladas cuando fue necesario.

![Resultados de las pruebas de aceptación del Backend](../assets/images/chapter-6/chapter-6-backend-acceptance-tests.png)

*Figura 6.7. Ejecución satisfactoria de cinco pruebas de aceptación del Backend de AutoService.*

La ejecución obtuvo **5 pruebas aprobadas, 0 fallidas y 0 omitidas**.

Estas pruebas forman parte de la suite general de 92 pruebas automatizadas del backend. Debido al uso de dependencias simuladas, los resultados no representan una validación completa del sistema desplegado con una base de datos real.

Las pruebas de interfaz de usuario y navegación de la aplicación Web, incluyendo las realizadas con Selenium, se documentarán posteriormente en este mismo apartado, de forma independiente de las pruebas del Backend.

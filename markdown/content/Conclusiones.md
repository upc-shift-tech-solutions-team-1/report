# Conclusiones y Recomendaciones

## Conclusiones

A partir del desarrollo, integración, verificación y despliegue de AutoService, se obtuvieron las siguientes conclusiones:

- **Integración de una solución multiplataforma:** AutoService consolida una solución compuesta por Landing Page, Web Application, Native Mobile Application y RESTful API. La arquitectura permite que los clientes Web y Mobile consuman los servicios proporcionados por el backend ASP.NET Core y accedan a la información persistida en MySQL.

- **Aplicación de una arquitectura modular y orientada al dominio:** La organización del backend mediante bounded contexts y la separación entre Domain, Application, Infrastructure e Interfaces permitió distribuir las responsabilidades del sistema de manera estructurada. Esta organización favorece la mantenibilidad del código y facilita la evolución independiente de los diferentes módulos del negocio.

- **Verificación automatizada del backend:** La implementación de pruebas unitarias, de integración y de aceptación permitió establecer una línea base automatizada de **31 pruebas ejecutadas satisfactoriamente, con 0 pruebas fallidas y 0 omitidas**. Estas pruebas validan comportamientos de entidades y agregados del dominio, autenticación mediante JWT, integración de la interfaz REST y restricciones de autorización basadas en roles.

- **Validación de autenticación y control de acceso:** Las pruebas desarrolladas comprobaron la generación de JWT, la incorporación de información como `email`, `role` y `WorkshopId`, así como la restricción de operaciones exclusivas para administradores. También se verificó que un usuario con rol `mechanic` no pueda ejecutar operaciones reservadas para el rol `admin`.

- **Automatización mediante Continuous Integration:** GitHub Actions permite verificar automáticamente los cambios enviados a las principales ramas del repositorio. El pipeline de Continuous Integration restaura dependencias, compila la solución en configuración `Release` y ejecuta la suite automatizada de pruebas, proporcionando una validación repetible antes de integrar cambios.

- **Implementación de Continuous Delivery:** El workflow de release permite generar versiones distribuibles del backend mediante tags basados en Semantic Versioning. La versión `v1.0.0` fue construida y publicada automáticamente mediante GitHub Actions, generando el artefacto `AutoServiceAW.zip` y su correspondiente GitHub Release.

- **Implementación de Continuous Deployment:** El backend se encuentra desplegado mediante Render utilizando Docker y la branch `main` como fuente de producción. La configuración `After CI Checks Pass` permite que el deployment automático se realice después de que las validaciones de Continuous Integration finalicen satisfactoriamente.

- **Infraestructura de producción desacoplada:** La solución utiliza Render para la ejecución de la RESTful API y Railway para la persistencia MySQL. Las credenciales y configuraciones sensibles se administran mediante Environment Variables, evitando incluir secretos directamente dentro del código fuente versionado.

- **Mejora en la comprensión y confianza del propietario (`EC-01`, `EC-05`):** Destacar la fecha estimada vigente y el motivo del retraso en la vista de seguimiento permitió que los participantes identificaran ambos datos sin ayuda (`M-01` pasó de 33,3 % a 100 %) y elevó las valoraciones favorables de confianza (`M-07` pasó de 0 % a 100 % en puntajes de 4 o más sobre 5), respaldando las premisas de transparencia del servicio.

- **Agilización del registro y recuperación de errores en web (`EC-02`, `EC-06`):** Incorporar indicaciones visibles de campos obligatorios y mensajes de validación específicos por campo en Vue permitió alcanzar 100 % de finalización autónoma (`M-02`) y de corrección de errores sin asistencia (`M-08`), reduciendo la mediana de tiempo de registro en 43 % (`M-03`, de 197,5 s a 112 s).

- **Reducción de errores operativos en Android (`EC-04`, `EC-08`):** Comparar existencias disponibles frente a las requeridas para una tarea (`EC-04`) evitó errores de cálculo manual (`M-06` alcanzó 100 %), mientras que ordenar y resaltar la siguiente tarea prioritaria del mecánico (`EC-08`) llevó a 100 % la actualización correcta (`M-10`) y redujo la tasa de errores de 55,6 % a 0 % (`M-11`).

- **Diferenciación entre entrega técnica y validación experimental (`EC-07`, `EC-03`):** El incremento de priorización web de órdenes (`EC-07`) demostró viabilidad técnica reutilizando los datos de la API existente, pero su hipótesis (`H7`) sigue pendiente al no haber sido evaluada con participantes. Por otro lado, excluir `EC-03` permitió concentrar los esfuerzos en los flujos operativos prioritarios.

- **Alcance exploratorio de los resultados:** Con pilotos de $n = 3$ participantes por experimento activo, la evidencia obtenida resulta útil para tomar decisiones de producto y reducir riesgos operativos iniciales, aunque no sustituye una validación estadística confirmatoria con muestras más amplias.

## Recomendaciones

A partir del estado actual del proyecto se plantean las siguientes recomendaciones para continuar fortaleciendo AutoService:

- **Automatizar completamente los escenarios BDD:** Actualmente se dispone de escenarios de autenticación especificados mediante Gherkin en `Authentication.feature`. Se recomienda incorporar sus correspondientes Step Definitions mediante una herramienta compatible con .NET para convertir estas especificaciones en pruebas BDD ejecutables dentro del pipeline.

- **Incrementar progresivamente la cobertura funcional:** Aunque la suite actual proporciona una línea base de 31 pruebas automatizadas, se recomienda continuar incorporando pruebas sobre los demás bounded contexts y escenarios críticos del negocio, especialmente aquellos relacionados con órdenes de trabajo, inventario, gestión de mecánicos y tracking público.

- **Completar la validación funcional del Native Mobile Application:** Se recomienda finalizar las pruebas del aplicativo Android contra la RESTful API desplegada en producción, verificando los flujos de autenticación, clientes, vehículos, mecánicos, inventario, órdenes de trabajo, tareas y tracking desde un dispositivo físico.

- **Fortalecer el monitoreo del entorno productivo:** El backend dispone de un endpoint `/health` para comprobar su disponibilidad. Como evolución futura, se recomienda complementar esta verificación con mecanismos de observabilidad, registro centralizado de errores y alertas que permitan detectar incidencias de producción de manera temprana.

- **Mantener el flujo controlado de releases:** Las futuras versiones del backend deberían continuar generándose desde estados estables de `main`, utilizando tags con Semantic Versioning y conservando la validación mediante GitHub Actions antes de cualquier deployment hacia producción.

- **Validar empíricamente la priorización de órdenes (`EC-07`):** Ejecutar sesiones moderadas con responsables de taller para medir `M-09` y `M-04` sobre el listado web ya integrado en `main`, cerrando la pregunta `Q-06` que conservó el mayor nivel de riesgo en la re-priorización (`8.4.2`).

- **Escalar los experimentos clave a escenarios de taller real:** Repetir las evaluaciones de `EC-01`, `EC-02` y `EC-08` con muestras de 8 a 10 participantes para confirmar las tendencias, probando además casos con múltiples repuestos por tarea en `EC-04` y jornadas con más de tres tareas simultáneas en Android Mechanic.

- **Estandarizar los patrones de usabilidad validados:** Replicar los mensajes específicos por campo (`EC-06`) en los demás formularios web de inventario y gestión de personal, y evaluar la incorporación de un historial breve de cambios de fecha en el seguimiento público (`EC-05`).

- **Planificar la mejora de la Landing Page (`EC-03`) en un ciclo futuro:** Retomar la diferenciación de rutas posteriores a la comparación de planes una vez consolidadas las mejoras operativas centrales de la plataforma.
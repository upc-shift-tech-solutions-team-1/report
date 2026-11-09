# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

La planificación de experimentos permite al equipo de AutoService investigar las necesidades que aún no se comprenden por completo y contrastar las creencias que sustentan la propuesta de valor. Para ello, se toman como punto de partida las entrevistas, la evaluación de usabilidad y los flujos de las aplicaciones web y móvil.

### 8.1.1. As-Is Summary.

AutoService integra la gestión de clientes, vehículos, personal, inventario, órdenes y tareas de un taller automotriz. Las aplicaciones web y móvil se conectan al mismo backend; además, el propietario de un vehículo puede consultar el estado de su servicio mediante un código de seguimiento.

Los técnicos y administradores entrevistados destacaron la utilidad de centralizar las operaciones del taller. Entre sus sugerencias se encuentran el acceso rápido a órdenes, la consulta de repuestos y una experiencia accesible para personas con menor familiaridad digital. También se identificó la necesidad de comprender cómo se maneja un volumen mayor de órdenes y vehículos.

La evaluación heurística documentó dificultades relacionadas con formularios, mensajes e idioma. Además, la auditoría de Teralume señaló problemas en la navegación de los planes y la accesibilidad del acceso web. Estos antecedentes orientan nuevas preguntas de usabilidad, considerando las versiones en las que se observaron.

Aunque las entrevistas aportan información sobre el trabajo del taller, no permiten conocer de forma directa cómo interpretan los propietarios de vehículos la información del seguimiento. Por ello, el equipo considera tanto a los responsables de taller como a los propietarios al diseñar los experimentos.


### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims.

El material inicial reúne percepciones de los participantes, observaciones de la evaluación de usabilidad y cuestiones que el equipo necesita investigar. Cada elemento identifica una incertidumbre relevante para la transparencia del servicio o la operación del taller.

| ID | Tipo | Material inicial | Fuente | Incertidumbre |
|---|---|---|---|---|
| RM-01 | Suposición | Consultar el avance y la fecha estimada puede aumentar la confianza del propietario en el servicio. | Propuesta de seguimiento e hipótesis Lean UX de AutoService. | Qué información necesita el propietario para confiar en el estado comunicado. |
| RM-02 | Afirmación | La organización de tareas y el control de inventario pueden facilitar el trabajo del taller. | Comentarios de técnicos independientes entrevistados. | Qué tareas logran completar los usuarios y dónde encuentran dificultades. |
| RM-03 | Idea | Facilitar la consulta rápida de órdenes y repuestos. | Sugerencias de los técnicos entrevistados. | Cuánto esfuerzo requiere localizar la información durante el trabajo diario. |
| RM-04 | Brecha de conocimiento | No se conoce cuánto tardan los responsables del taller en registrar una orden completa en cada plataforma. | Flujo de registro disponible en web y móvil. | Tiempo, errores y ayuda necesarios para completar la tarea. |
| RM-05 | Brecha de conocimiento | No se conoce si el propietario entiende por qué cambió la fecha estimada. | Flujo de seguimiento y registro de cambios de fecha. | Comprensión de la nueva fecha y del motivo del retraso. |
| RM-06 | Suposición | Consultar las existencias antes de realizar una tarea ayuda a identificar materiales insuficientes. | Flujo de inventario y tareas del taller. | Si el usuario reconoce la disponibilidad y sabe qué hacer ante un faltante. |
| RM-07 | Hallazgo de evaluación | El campo de contraseña no presentó un nombre accesible adecuado y el idioma declarado no cambió al seleccionar español. | Auditoría de Teralume sobre el acceso web. | Si los usuarios pueden identificar los campos de acceso y comprenderlos con tecnologías de asistencia. |
| RM-08 | Hallazgo de evaluación | Se identificaron problemas de validación en formularios de contacto y registro de clientes. | Evaluación heurística de formularios web. | Si los usuarios reconocen los datos que deben corregir antes de enviar un formulario. |
| RM-09 | Hallazgo de evaluación | Los botones Free y Business devolvieron al visitante al inicio de la Landing Page. | Auditoría de Teralume sobre la selección de planes. | Si los responsables de taller encuentran una ruta clara para comenzar a utilizar el producto o contactar al equipo. |
| RM-10 | Brecha de conocimiento | No se conoce cómo resuelve el taller la falta de un repuesto necesario para una tarea. | Necesidad de consultar existencias y proveedores mencionada en las entrevistas. | Qué información buscan los usuarios y qué acciones esperan realizar. |
| RM-11 | Brecha de conocimiento | No se conoce cómo localizan los responsables las órdenes y tareas que requieren atención cuando aumenta la carga de trabajo. | Comentario de un entrevistado sobre el manejo de numerosas órdenes y vehículos. | Qué obstáculos aparecen al buscar y priorizar trabajo pendiente. |
| RM-12 | Suposición | Mostrar el avance de la reparación puede ayudar al propietario a conocer la situación del vehículo sin consultar continuamente al taller. | Propuesta de seguimiento y comentarios de entrevistados sobre la consulta del estado. | Si el propietario entiende el avance y qué información adicional necesita. |


### 8.1.3. Experiment-Ready Questions.

Las preguntas identifican a la persona, la tarea y la información que se busca obtener. Algunas parten de una creencia y otras exploran situaciones sobre las que aún se cuenta con poca información.

| ID | Tipo | Pregunta | Motivación | Material |
|---|---|---|---|---|
| Q-01 | Basada en una creencia | ¿Los propietarios comprenden la fecha actualizada y el motivo del retraso al consultar el seguimiento sin ayuda? | Conocer si el seguimiento comunica claramente un cambio importante del servicio. | RM-01, RM-05, RM-12 |
| Q-02 | Exploratoria | ¿Qué dificultades encuentran los responsables de taller al registrar una orden completa en web y móvil? | Identificar obstáculos en una operación necesaria para organizar el servicio. | RM-02, RM-04 |
| Q-03 | Exploratoria | ¿Cómo comprueban los usuarios del taller si cuentan con los repuestos necesarios y qué hacen ante un faltante? | Entender las decisiones relacionadas con la disponibilidad de materiales. | RM-03, RM-06, RM-10 |
| Q-04 | Basada en una creencia | ¿Qué relación perciben los propietarios entre la información de seguimiento y su confianza en el servicio? | Investigar una premisa central de la propuesta de valor. | RM-01, RM-12 |
| Q-05 | Exploratoria | ¿Qué dificultades encuentran los usuarios al identificar los campos de acceso y corregir datos en los formularios? | Conocer si la interfaz facilita el acceso y ayuda a recuperarse de errores. | RM-07, RM-08 |
| Q-06 | Exploratoria | ¿Cómo localizan y priorizan los responsables las órdenes y tareas pendientes cuando hay varios servicios activos? | Identificar necesidades de organización ante una mayor carga de trabajo. | RM-02, RM-03, RM-11 |
| Q-07 | Exploratoria | ¿Los responsables de taller encuentran cómo comenzar a usar AutoService o contactar al equipo después de comparar los planes? | Examinar la continuidad del recorrido de una persona interesada en el producto. | RM-09 |

### 8.1.4. Question Backlog.

Las preguntas se ordenan según cuatro criterios valorados de 1 a 5: confianza en la relevancia de la pregunta, riesgo de mantener la incertidumbre, impacto para el producto e interés de investigación. La puntuación es la suma de los cuatro valores; ante un empate se da prioridad a la pregunta con mayor riesgo.

| Prioridad | Pregunta | Confianza | Riesgo | Impacto | Interés | Total |
|---:|---|---:|---:|---:|---:|---:|
| 1 | Q-01: comprensión de fechas y retrasos | 4 | 5 | 5 | 5 | 19 |
| 2 | Q-02: registro de órdenes | 4 | 4 | 5 | 5 | 18 |
| 3 | Q-07: acceso a partir de los planes | 4 | 4 | 4 | 5 | 17 |
| 4 | Q-03: disponibilidad de repuestos | 4 | 4 | 4 | 4 | 16 |
| 5 | Q-05: acceso y formularios | 4 | 4 | 4 | 3 | 15 |
| 6 | Q-06: identificación de trabajo pendiente | 3 | 3 | 4 | 4 | 14 |
| 7 | Q-04: confianza en el seguimiento | 3 | 3 | 4 | 3 | 13 |



### 8.1.5. Experiment Cards.

Las tarjetas presentan siete pilotos propuestos. Cada uno compara una condición de referencia con una alternativa experimental; los prototipos y materiales de comparación se prepararán para el estudio y no se consideran funcionalidades implementadas.

**EC-01 — Comprensión de la fecha de entrega**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Los propietarios comprenden la fecha actualizada y el motivo del retraso sin ayuda? |
| Por qué | El cliente necesita entender cuándo se espera la entrega y por qué cambió. |
| Hipótesis | La presentación de seguimiento de AutoService permitirá identificar correctamente ambos datos a una proporción mayor de participantes que una presentación de referencia. |
| Qué | Una tarea de consulta con órdenes ficticias y dos presentaciones de la misma clase de información. |
| Medidas | M-01 y M-04; observación de dudas y errores. |
| Condiciones | Una presentación de referencia y la interfaz de seguimiento, ambas con fecha vigente y motivo. |
| Escala | Tres propietarios de vehículos, en un piloto moderado. |

**EC-02 — Registro de una orden**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Qué dificultades encuentran los responsables al registrar una orden completa en web y móvil? |
| Por qué | El registro correcto permite organizar el trabajo y generar información para el seguimiento. |
| Hipótesis | Una mayor proporción completará correctamente el registro sin ayuda con indicaciones claras que con la presentación de referencia. |
| Qué | Registrar una orden en dos presentaciones equivalentes con datos ficticios. |
| Medidas | M-02, M-03 y M-04; registro de errores observados. |
| Condiciones | Referencia sin indicaciones adicionales y prototipo con campos obligatorios y mensajes de validación claros, evaluados por separado en web y móvil. |
| Escala | Tres responsables de taller, en un piloto moderado. |

**EC-03 — Acceso después de comparar planes**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Los responsables de taller encuentran cómo comenzar a usar AutoService o contactar al equipo después de comparar los planes? |
| Por qué | Una ruta poco clara puede interrumpir el interés de un taller en el producto. |
| Hipótesis | Una mayor proporción identificará el siguiente paso sin ayuda con opciones claramente diferenciadas que con la presentación de referencia. |
| Qué | Localizar una ruta después de revisar los planes en dos presentaciones, sin enviar solicitudes. |
| Medidas | M-05 y M-04; rutas elegidas, dudas y errores observados. |
| Condiciones | Referencia con la navegación actual y prototipo con destinos explícitos; prueba en escritorio y vista móvil. |
| Escala | Tres responsables de taller, en un piloto moderado. |

**EC-04 — Identificación de repuestos disponibles**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Cómo comprueban los usuarios del taller si cuentan con los repuestos necesarios y qué hacen ante un faltante? |
| Por qué | Reconocer materiales insuficientes permite anticipar dificultades al organizar el trabajo. |
| Hipótesis | Una mayor proporción interpretará correctamente la disponibilidad sin ayuda con una indicación explícita del stock que con la referencia. |
| Qué | Consultar casos ficticios con existencias suficientes e insuficientes en ambas presentaciones. |
| Medidas | M-06 y M-04; respuestas, dudas y acciones propuestas. |
| Condiciones | Referencia con cantidades y prototipo con cantidades más una indicación de disponibilidad; sin modificar inventario real. |
| Escala | Tres responsables de taller, en un piloto moderado. |

**EC-05 — Confianza percibida en el seguimiento**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Qué relación perciben los propietarios entre la información de seguimiento y su confianza en el servicio? |
| Por qué | Conocer la percepción del cliente ayuda a evaluar la claridad y utilidad de la comunicación del taller. |
| Hipótesis | Una mayor proporción valorará con 4 o 5 la utilidad para confiar al consultar un seguimiento detallado que al consultar uno resumido. |
| Qué | Consultar dos presentaciones de casos ficticios y valorar la utilidad de su información. |
| Medidas | M-07 y comentarios sobre información útil o faltante. |
| Condiciones | Referencia con estado y alternativa con estado, fecha y motivo; misma pregunta y escala de 1 a 5. |
| Escala | Tres propietarios de vehículos, en un piloto moderado. |

**EC-06 — Comprensión del acceso y de los formularios**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Qué dificultades encuentran los usuarios al identificar los campos de acceso y corregir datos en los formularios? |
| Por qué | Los controles y mensajes claros ayudan a las personas a acceder y completar sus tareas. |
| Hipótesis | Una mayor proporción completará ambas tareas sin ayuda con etiquetas y mensajes claros que con la referencia. |
| Qué | Identificar el campo de contraseña y corregir un dato inválido en dos formularios de prueba. |
| Medidas | M-08 y M-04; errores, dudas y explicaciones observadas. |
| Condiciones | Referencia con presentación básica y prototipo con etiquetas y mensajes claros; mismo idioma e instrucciones. |
| Escala | Tres responsables de taller, en un piloto moderado. |

**EC-07 — Localización y prioridad de órdenes**

| Elemento | Descripción |
|---|---|
| Pregunta | ¿Cómo localizan y priorizan los responsables las órdenes y tareas pendientes cuando hay varios servicios activos? |
| Por qué | Identificar el trabajo que necesita atención favorece la organización del taller. |
| Hipótesis | Una mayor proporción localizará la orden y reconocerá su prioridad sin ayuda con una organización destacada que con la referencia. |
| Qué | Buscar una orden y aplicar un criterio de prioridad en dos presentaciones de registros ficticios. |
| Medidas | M-09 y M-04; ruta, dudas y errores observados. |
| Condiciones | Referencia con lista básica y prototipo que destaca la información usada en el criterio de prioridad. |
| Escala | Tres responsables de taller, en un piloto moderado. |

## 8.2. Experiment Design

Los siete diseños son propuestas de pilotos: las condiciones, los prototipos y la participación descritos todavía no constituyen ejecuciones ni resultados observados.

### 8.2.1. Hypotheses.

Cada hipótesis expresa la respuesta que el equipo considera posible, la medida que aportará evidencia y las condiciones en las que se realizará la observación. La hipótesis nula describe un resultado contrario a la hipótesis de trabajo.

| Experimento | Hipótesis de trabajo: creencia, medida y condiciones | Hipótesis nula |
|---|---|---|
| EC-01 | **H1:** Creemos que la presentación de AutoService facilita la comprensión del retraso. Esto se reflejaría en una proporción mayor de propietarios que identifican sin ayuda la fecha vigente y el motivo (M-01), al consultar AutoService frente a una presentación de referencia con información equivalente. | **H0-1:** La proporción que identifica ambos datos sin ayuda con AutoService es igual o menor que con la presentación de referencia. |
| EC-02 | **H2:** Creemos que indicar los campos obligatorios y errores facilita el registro. Se reflejaría en una mayor proporción de órdenes completadas correctamente sin ayuda (M-02), al comparar el prototipo con la referencia en tareas equivalentes. | **H0-2:** La proporción con el prototipo es igual o menor que con la referencia. |
| EC-03 | **H3:** Creemos que diferenciar los destinos de los planes facilita encontrar el siguiente paso. Se reflejaría en una mayor proporción que identifica una ruta adecuada sin ayuda (M-05), con el prototipo frente a la referencia. | **H0-3:** La proporción con el prototipo es igual o menor que con la referencia. |
| EC-04 | **H4:** Creemos que una indicación explícita de disponibilidad facilita interpretar el stock. Se reflejaría en una mayor proporción de respuestas correctas sin ayuda (M-06), con el prototipo frente a la referencia. | **H0-4:** La proporción con el prototipo es igual o menor que con la referencia. |
| EC-05 | **H5:** Creemos que el seguimiento detallado se percibe como más útil para confiar en el servicio. Se reflejaría en una mayor proporción de valoraciones de 4 o 5 sobre 5 (M-07), frente a una presentación resumida. | **H0-5:** La proporción de esas valoraciones con el seguimiento detallado es igual o menor que con la presentación resumida. |
| EC-06 | **H6:** Creemos que etiquetas y mensajes claros facilitan identificar el campo y corregir un dato. Se reflejaría en una mayor proporción que completa ambas tareas sin ayuda (M-08), con el prototipo frente a la referencia. | **H0-6:** La proporción con el prototipo es igual o menor que con la referencia. |
| EC-07 | **H7:** Creemos que destacar los datos relevantes facilita encontrar una orden y reconocer su prioridad. Se reflejaría en una mayor proporción que completa ambas acciones sin ayuda (M-09), con el prototipo frente a la referencia. | **H0-7:** La proporción con el prototipo es igual o menor que con la referencia. |


### 8.2.2. Domain Business Metrics

| ID | Métrica | Cálculo | Recolección | Meta propuesta |
|---|---|---|---|---|
| M-01 | Comprensión autónoma del retraso | Participantes que identifican fecha y motivo sin ayuda / participantes evaluados × 100. | Respuestas registradas en cada condición. | Mayor proporción con AutoService. |
| M-02 | Finalización autónoma del registro | Participantes que completan la orden correctamente sin ayuda / participantes evaluados × 100. | Observación de la tarea por condición y plataforma. | Mayor proporción con el prototipo. |
| M-03 | Tiempo de registro | Segundos desde el inicio hasta la confirmación de creación; se resume con la mediana de tareas completadas. | Cronómetro durante cada tarea. | Establecer una línea base, sin umbral previo. |
| M-04 | Solicitudes de asistencia | Participantes que solicitan ayuda / participantes evaluados × 100. | Registro de intervenciones del moderador. | Identificar tareas que requieren ayuda, sin umbral previo. |
| M-05 | Identificación autónoma del siguiente paso | Participantes que identifican sin ayuda una ruta adecuada después de revisar los planes / participantes evaluados × 100. | Observación por condición y vista. | Mayor proporción con el prototipo. |
| M-06 | Interpretación autónoma de disponibilidad | Participantes que identifican correctamente si el stock cubre la necesidad sin ayuda / participantes evaluados × 100. | Respuestas por condición y caso. | Mayor proporción con el prototipo. |
| M-07 | Valoración de utilidad para confiar | Participantes que valoran con 4 o 5 sobre 5 / participantes evaluados × 100. | Misma pregunta de utilidad por condición. | Mayor proporción con el seguimiento detallado. |
| M-08 | Comprensión del acceso y corrección | Participantes que identifican el campo de contraseña y corrigen el dato inválido sin ayuda / participantes evaluados × 100. | Observación de ambas tareas por condición. | Mayor proporción con el prototipo. |
| M-09 | Localización y prioridad | Participantes que localizan la orden indicada y reconocen su prioridad sin ayuda / participantes evaluados × 100. | Observación por condición con el mismo criterio. | Mayor proporción con el prototipo. |

La comprensión del retraso se relaciona con la transparencia hacia el cliente; la finalización, el tiempo y la asistencia ayudan a evaluar la facilidad operativa del taller. La valoración M-07 recoge una percepción declarada de utilidad para confiar; las demás medidas no equivalen por sí solas a ingresos, retención o confianza.

### 8.2.3. Measures.

En el estudio de seguimiento, el moderador pedirá al participante que indique la fecha vigente y explique el motivo del retraso. La respuesta será correcta cuando ambos datos coincidan con el caso presentado y no se haya proporcionado ayuda. Se registrarán por separado las dudas, respuestas incompletas y solicitudes de asistencia.

En el registro de órdenes se comprobará que el participante complete los datos solicitados y llegue a la confirmación de creación. Se anotarán el tiempo, los errores observables y la ayuda requerida. Las tareas incompletas se registrarán como tales y no se incluirán en la mediana de tiempos de finalización.

Para los planes, el moderador registrará si la persona identifica una ruta coherente con la tarea sin ayuda, además de las opciones seleccionadas. La acción se detendrá antes de enviar información. Para los repuestos, comparará la respuesta sobre disponibilidad con las cantidades del caso y registrará la acción que el participante propone ante un faltante, sin suponer que dicha acción esté implementada.

Para la confianza, se preguntará: «¿Qué tan útil es esta información para confiar en el servicio del taller?», en una escala de 1 a 5, donde 1 significa nada útil y 5 muy útil. Se pedirá explicar la valoración. En acceso y formularios se comprobará la identificación del campo de contraseña y la corrección de un dato inválido; para órdenes pendientes se registrará si la persona encuentra el registro y aplica el criterio de prioridad proporcionado. Estas tareas no sustituyen una prueba específica con usuarios de tecnologías de asistencia.

### 8.2.4. Conditions.

| Experimento | Condiciones | Preparación y control |
|---|---|---|
| EC-01 | Referencia: presentación sencilla preparada para el estudio. Experimental: pantalla de seguimiento de AutoService. Ambas contienen fecha vigente y motivo. | Cada propietario revisará dos casos ficticios equivalentes con datos distintos. Se alternará el orden y se aplicarán las mismas instrucciones y criterios de respuesta. |
| EC-02 | Referencia: formulario sin indicaciones adicionales. Experimental: prototipo con campos obligatorios y errores claros. | Preparar tareas equivalentes por condición y evaluar por separado web y móvil, con registros ficticios. |
| EC-03 | Referencia: navegación actual desde los planes. Experimental: prototipo con destinos explícitos. | Usar tareas equivalentes en escritorio y vista móvil sin enviar solicitudes. |
| EC-04 | Referencia: cantidades de stock. Experimental: las mismas cantidades con indicación explícita de disponibilidad. | Preparar casos ficticios de stock suficiente e insuficiente en ambas condiciones. |
| EC-05 | Referencia: seguimiento resumido con estado. Experimental: seguimiento detallado con estado, fecha y motivo. | Aplicar la misma pregunta y escala a ambos casos ficticios; documentar que cambia la cantidad de información. |
| EC-06 | Referencia: formulario básico. Experimental: prototipo con etiquetas y mensajes claros. | Usar instrucciones, idioma y datos ficticios equivalentes; registrar la forma de interacción. |
| EC-07 | Referencia: lista básica. Experimental: lista que destaca datos relevantes para identificar prioridad. | Utilizar conjuntos equivalentes de órdenes ficticias y el mismo criterio de prioridad. |

Las dos presentaciones del primer experimento contienen la información necesaria para responder. Así se puede explorar la claridad de su organización, aunque el aprendizaje entre tareas y el tamaño reducido del piloto limitarán la interpretación de las diferencias.

En cada experimento, la condición de referencia permite comparar la medida con la alternativa experimental. Se propone que cada participante pruebe ambas condiciones del experimento asignado con casos equivalentes y que se alterne su orden. Las alternativas son materiales por preparar; las diferencias observadas en este piloto no permitirán establecer causalidad con certeza. Web y móvil se analizarán por separado cuando corresponda; no se consideran, por sí solas, condiciones de control y experimental.

Las sesiones requieren el consentimiento de los participantes. Se utilizarán cuentas y datos de prueba; las fichas no incluirán contraseñas ni datos personales de clientes.

### 8.2.5. Scale Calculations and Decisions.

Se propone un piloto de **tres participantes por experimento**: propietarios para los dos estudios de seguimiento y responsables de taller para los otros cinco. Para evitar que los estudios relacionados interfieran entre sí, el plan inicial contempla grupos distintos: seis propietarios y quince responsables, veintiuna personas en total. Cada participante evaluará las dos condiciones del experimento asignado. La captación, disponibilidad y viabilidad de esta escala aún no están confirmadas.

Con tres participantes por experimento, cada respuesta representa aproximadamente el 33,3 % del grupo. Esta escala permite explorar dificultades y comprobar la viabilidad del procedimiento, pero no permite generalizar los resultados ni concluir que exista una diferencia estadísticamente significativa.

Para una investigación confirmatoria se requiere definir un nivel de significación, una potencia estadística, el efecto mínimo que se desea detectar y una estimación de la variabilidad compatible con el diseño pareado. Sin esos datos no corresponde presentar un tamaño de muestra confirmatorio como calculado.

### 8.2.6. Methods Selection.

Se propone una prueba moderada de tareas con observación directa y preguntas breves. Para el seguimiento, el moderador presentará los dos casos y registrará las respuestas. En los estudios del taller observará los recorridos y anotará las dificultades y la asistencia solicitada.

Los participantes recibirán una explicación de la actividad y podrán detenerla cuando lo deseen. Se utilizarán grupos distintos para evitar la exposición simultánea a estudios relacionados y se alternará el orden de las condiciones de cada experimento. La repetición de tareas puede generar aprendizaje, por lo que se registrarán el orden y las observaciones correspondientes.

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection.

| Objetivo | Indicadores | Uso de la información |
|---|---|---|
| Evaluar la claridad de la comunicación de retrasos. | M-01 y M-04, acompañadas de dudas y errores observados. | Identificar si la fecha y el motivo se comprenden sin ayuda y qué partes de la presentación generan confusión. |
| Comprender las dificultades al registrar una orden. | M-02, M-03 y M-04 por plataforma. | Reconocer los pasos que requieren asistencia o dificultan la finalización. |
| Evaluar la continuidad del recorrido desde los planes. | M-05 y M-04 por vista, junto con las rutas observadas. | Identificar dónde las personas pierden el siguiente paso. |
| Comprender la consulta de disponibilidad de repuestos. | M-06 y M-04 por caso, junto con las acciones propuestas. | Identificar dificultades para reconocer stock suficiente o insuficiente. |
| Explorar la utilidad percibida del seguimiento para confiar en el servicio. | M-07 y explicaciones de los propietarios. | Reconocer qué información contribuye a la percepción declarada. |
| Evaluar la comprensión del acceso y los formularios. | M-08 y M-04, con dudas y errores observados. | Identificar controles o mensajes que dificultan las tareas. |
| Evaluar la localización y prioridad de órdenes. | M-09 y M-04, con rutas observadas. | Identificar dificultades al organizar el trabajo pendiente. |

La lectura combinará recuentos y porcentajes con observaciones cualitativas. Para el tiempo se utilizará la mediana de las tareas completadas, indicando cuántas personas finalizaron. Las diferencias observadas se interpretarán como señales exploratorias propias de un piloto.

### 8.2.8. Web and Mobile Tracking Plan.

La recolección propuesta es manual mediante fichas de observación. Cada sesión se identificará con un código anónimo y registrará la plataforma, la tarea, la condición, el resultado y la asistencia. No se requiere incorporar una herramienta de analítica automatizada para realizar estas pruebas.

| Actividad | Plataforma | Datos registrados | Métricas |
|---|---|---|---|
| Consultar fecha y motivo del retraso. | Web o móvil, según la presentación de AutoService seleccionada para la sesión. | Identificador anónimo, condición, respuesta sobre fecha, respuesta sobre motivo y ayuda. | M-01, M-04 |
| Registrar una orden. | Web y móvil. | Identificador anónimo, condición, plataforma, resultado, tiempo, errores y ayuda. | M-02, M-03, M-04 |
| Buscar el siguiente paso tras revisar los planes. | Landing Page en escritorio y vista móvil. | Identificador anónimo, condición, vista, ruta elegida, resultado y ayuda. | M-05, M-04 |
| Consultar la disponibilidad de un repuesto. | Web o móvil seleccionada para la sesión. | Identificador anónimo, condición, plataforma, caso, respuesta y ayuda. | M-06, M-04 |
| Valorar la utilidad del seguimiento para confiar en el servicio. | Web o móvil, según la presentación utilizada. | Identificador anónimo, condición, plataforma, valoración de 1 a 5 y explicación. | M-07 |
| Identificar el acceso y corregir un dato inválido. | Aplicación web. | Identificador anónimo, condición, resultado, interacción, errores y ayuda. | M-08, M-04 |
| Localizar una orden y reconocer su prioridad. | Web o móvil seleccionada para la sesión. | Identificador anónimo, condición, plataforma, resultado, ruta y ayuda. | M-09, M-04 |

## 8.3. Experimentation

Los pilotos descritos permiten orientar posibles mejoras para AutoService. Las historias y prioridades de esta sección constituyen propuestas de evolución derivadas de las preguntas de investigación; no representan cambios implementados ni resultados observados de sesiones que aún no se han realizado.

### 8.3.1. To-Be User Stories.

| ID | Historia de usuario propuesta | Criterio de aceptación propuesto |
|---|---|---|
| EXP-US-01 | Como propietario de un vehículo, quiero identificar la fecha estimada vigente y el motivo de un retraso para comprender cuándo se espera la entrega de mi vehículo. | El seguimiento presenta la fecha vigente y, cuando se haya registrado un retraso, su motivo de forma comprensible. |
| EXP-US-02 | Como responsable de taller, quiero registrar una orden de manera clara en web y móvil para organizar el trabajo sin omitir los datos requeridos. | Los campos necesarios se identifican y la aplicación comunica la confirmación o los errores del registro. |
| EXP-US-03 | Como responsable de taller, quiero consultar la disponibilidad de repuestos para reconocer posibles faltantes antes de continuar una tarea. | La información disponible permite identificar el repuesto y su cantidad registrada. |
| EXP-US-04 | Como usuario del taller, quiero comprender los mensajes de validación para corregir la información y completar una operación. | Los mensajes identifican el dato que requiere atención y se presentan en un lenguaje comprensible. |
| EXP-US-05 | Como responsable de taller interesado en AutoService, quiero acceder a una opción clara después de revisar los planes para iniciar el registro o contactar al equipo. | Cada opción comunica su propósito y conduce a la acción correspondiente. |
| EXP-US-06 | Como propietario de un vehículo, quiero consultar información comprensible sobre el servicio para valorar si me permite confiar en el seguimiento del taller. | La información del servicio se presenta con un estado, una fecha estimada y los datos disponibles del avance. |
| EXP-US-07 | Como responsable de taller, quiero encontrar una orden pendiente entre varios servicios para identificar el trabajo que requiere atención. | La lista permite localizar la orden y consultar la información necesaria para aplicar el criterio de prioridad definido por el taller. |

Estas historias describen necesidades y criterios a investigar; su inclusión no implica que la funcionalidad esté ausente ni que se haya verificado su cumplimiento con participantes.

### 8.3.2. To-Be Product Backlog

| Prioridad propuesta | Historia | Valor esperado | Relación con la investigación | Estado |
|---:|---|---|---|---|
| 1 | EXP-US-01 | Facilitar la comunicación de cambios en la entrega. | Comprensión de fecha y motivo. | Propuesta por contrastar. |
| 2 | EXP-US-02 | Facilitar la creación de órdenes en ambas plataformas. | Observación del registro de una orden. | Propuesta por contrastar. |
| 3 | EXP-US-03 | Favorecer decisiones informadas ante posibles faltantes. | Consulta de existencias y acciones ante falta de stock. | Propuesta por investigar. |
| 4 | EXP-US-04 | Ayudar a completar operaciones y corregir errores. | Comprensión de mensajes y formularios. | Propuesta por investigar. |
| 5 | EXP-US-05 | Facilitar el acceso al producto para talleres interesados. | Navegación desde los planes de la Landing Page. | Propuesta por investigar. |
| 6 | EXP-US-06 | Comprender qué información ayuda al cliente a valorar el seguimiento. | Percepción de utilidad para confiar en el servicio. | Propuesta por investigar. |
| 7 | EXP-US-07 | Facilitar la organización de órdenes pendientes. | Localización y prioridad de órdenes. | Propuesta por investigar. |

La prioridad expresa el valor esperado y la relación con las preguntas seleccionadas. No supone que los cambios estén desarrollados ni que un resultado experimental haya confirmado su necesidad.

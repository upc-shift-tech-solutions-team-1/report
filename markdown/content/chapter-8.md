# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

La planificación de experimentos permite al equipo de AutoService investigar las necesidades que aún no se comprenden por completo y contrastar las creencias que sustentan la propuesta de valor. Para ello, se toman como punto de partida las entrevistas, la evaluación de usabilidad y los flujos de las aplicaciones web y móvil.

### 8.1.1. As-Is Summary

AutoService integra la gestión de clientes, vehículos, personal, inventario, órdenes y tareas de un taller automotriz. Las aplicaciones web y móvil se conectan al mismo backend; además, el propietario de un vehículo puede consultar el estado de su servicio mediante un código de seguimiento.

Los técnicos y administradores entrevistados destacaron la utilidad de centralizar las operaciones del taller. Entre sus sugerencias se encuentran el acceso rápido a órdenes, la consulta de repuestos, la visibilidad clara del trabajo asignado al mecánico y una experiencia accesible para personas con menor familiaridad digital. También se identificó la necesidad de comprender cómo se maneja un volumen mayor de órdenes, vehículos y tareas pendientes.

La evaluación heurística documentó dificultades relacionadas con formularios, mensajes e idioma. Además, la auditoría externa señaló problemas en la navegación de los planes de la Landing Page y la accesibilidad del acceso web. Estos antecedentes orientan la definición de preguntas de investigación, considerando el alcance de las versiones As-Is evaluadas.

Aunque las entrevistas aportan información sobre el trabajo del taller, no permiten medir de forma directa cómo interpretan los propietarios de vehículos la información del seguimiento ni cómo responden los usuarios del taller ante mejoras específicas en la web y en Android. Por ello, el diseño experimental abarca tanto a propietarios de vehículos como a responsables de taller y mecánicos.

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

El material inicial reúne percepciones de los participantes, observaciones de la evaluación de usabilidad y cuestiones que el equipo necesita investigar. Cada elemento identifica una incertidumbre relevante para la transparencia del servicio o la operación del taller.

| ID | Tipo | Material inicial | Fuente | Incertidumbre |
|---|---|---|---|---|
| RM-01 | Suposición | Consultar el avance y la fecha estimada puede aumentar la confianza del propietario en el servicio. | Propuesta de seguimiento e hipótesis Lean UX de AutoService. | Qué información necesita el propietario para confiar en el estado comunicado. |
| RM-02 | Afirmación | La organización de tareas y el control de inventario pueden facilitar el trabajo del taller. | Comentarios de técnicos independientes entrevistados. | Qué tareas logran completar los usuarios y dónde encuentran dificultades. |
| RM-03 | Idea | Facilitar la consulta rápida de órdenes, repuestos y tareas asignadas. | Sugerencias de los técnicos entrevistados. | Cuánto esfuerzo requiere localizar la información durante el trabajo diario. |
| RM-04 | Brecha de conocimiento | No se conoce cuánto tardan los responsables del taller en registrar una orden completa en la aplicación web. | Flujo As-Is de registro de órdenes en la aplicación web. | Tiempo, errores y ayuda necesarios para completar la operación. |
| RM-05 | Brecha de conocimiento | No se conoce si el propietario entiende por qué cambió la fecha estimada. | Flujo de seguimiento y registro de cambios de fecha. | Comprensión de la nueva fecha vigente y del motivo del retraso. |
| RM-06 | Suposición | Consultar las existencias frente a la cantidad requerida para una tarea ayuda a identificar materiales insuficientes. | Flujo de inventario y tareas del taller en Android. | Si el usuario reconoce la suficiencia o insuficiencia de stock para una tarea. |
| RM-07 | Hallazgo de evaluación | El campo de contraseña no presentó un nombre accesible adecuado y el idioma declarado no cambió al seleccionar español. | Auditoría de accesibilidad sobre el acceso web (antecedente histórico). | Cómo impactan las etiquetas y el idioma en el acceso web (fuera del foco operativo TB2, conservado como antecedente). |
| RM-08 | Hallazgo de evaluación | Se identificaron problemas de validación poco específica en formularios operativos de la aplicación web. | Evaluación heurística de formularios web. | Si los usuarios identifican los campos obligatorios y corrigen los errores antes de confirmar el registro. |
| RM-09 | Hallazgo de evaluación | Los botones Free y Business devolvieron al visitante al inicio de la Landing Page. | Auditoría sobre la selección de planes (antecedente histórico). | Si los responsables de taller encuentran una ruta clara para comenzar a utilizar el producto (excluido del incremento técnico TB2). |
| RM-10 | Brecha de conocimiento | No se conoce cómo anticipa el taller la falta de un repuesto necesario antes de iniciar una tarea de reparación. | Necesidad de consultar existencias mencionada en las entrevistas. | Si la comparación entre stock disponible y requerido permite anticipar faltantes. |
| RM-11 | Brecha de conocimiento | No se conoce cómo localizan los responsables las órdenes que requieren atención prioritaria cuando aumenta la carga de trabajo. | Comentario de un entrevistado sobre el manejo de numerosas órdenes y vehículos. | Qué criterios visibles permiten identificar las órdenes urgentes sin ayuda. |
| RM-12 | Suposición | Mostrar el avance de la reparación puede ayudar al propietario a conocer la situación del vehículo sin consultar continuamente al taller. | Propuesta de seguimiento y comentarios de entrevistados sobre la consulta del estado. | Si el propietario entiende el avance y qué información contribuye a su confianza. |
| RM-13 | Brecha de conocimiento | No se conoce con qué facilidad un mecánico identifica su siguiente tarea relevante y actualiza su progreso desde Android. | Flujo As-Is del módulo Mechanic y coordinación administrador-mecánico. | Si destacar prioridad, estado y acción directa reduce errores al localizar y actualizar tareas asignadas. |

### 8.1.3. Experiment-Ready Questions

Las preguntas identifican al usuario involucrado, la tarea y la información que se busca obtener mediante la técnica 5W+1H. Se distingue entre preguntas basadas en una creencia (*Belief-led*) y preguntas exploratorias (*Exploratory*).

| ID | Tipo | Pregunta | Motivación | Material |
|---|---|---|---|---|
| Q-01 | Basada en una creencia (*Belief-led*) | ¿Los propietarios de vehículos comprenden la fecha actualizada de entrega y el motivo del retraso al consultar el seguimiento sin ayuda? | Mejorar la comunicación entre el taller y el propietario del vehículo, reduciendo dudas sobre el avance. | RM-01, RM-05, RM-12 |
| Q-02 | Exploratoria (*Exploratory*) | ¿Las indicaciones de obligatoriedad y validaciones claras facilitan que un responsable del taller registre correctamente una orden de trabajo en la aplicación web? | Reducir errores en el registro de órdenes y evitar información incompleta que afecte la planificación del servicio. | RM-02, RM-04 |
| Q-03 | Exploratoria (*Exploratory*) | ¿Los usuarios del taller pueden identificar en Android si los repuestos disponibles alcanzan para realizar una tarea de reparación? | Anticipar faltantes y evitar iniciar tareas sin los materiales necesarios. | RM-03, RM-06, RM-10 |
| Q-04 | Basada en una creencia (*Belief-led*) | ¿La información detallada sobre el seguimiento de una reparación mejora la utilidad percibida para que el propietario confíe en el servicio? | Conocer qué nivel de detalle informativo necesita el propietario para sentirse informado y confiar en el taller. | RM-01, RM-12 |
| Q-05 | Exploratoria (*Exploratory*) | ¿Los usuarios identifican y corrigen con mayor facilidad los errores de entrada al completar un formulario operativo en la aplicación web? | Evitar interrupciones por errores de validación poco claros y mejorar la finalización de operaciones administrativas. | RM-08 |
| Q-06 | Exploratoria (*Exploratory*) | ¿Los responsables del taller pueden identificar qué órdenes requieren atención prioritaria cuando existen varios servicios activos? | Mejorar la organización del trabajo diario y facilitar la identificación de servicios urgentes. | RM-02, RM-03, RM-11 |
| Q-07 | Exploratoria (*Exploratory*) | ¿Los responsables de taller encuentran cómo comenzar a usar AutoService o contactar al equipo después de comparar los planes en la Landing Page? | Examinar la continuidad del recorrido inicial de una persona interesada (conservada como histórico; excluida de TB2). | RM-09 |
| Q-08 | Exploratoria (*Exploratory*) | ¿Una presentación más clara de las tareas asignadas en Android permite que un mecánico identifique su siguiente actividad y actualice su progreso correctamente? | Mejorar la coordinación entre administrador y mecánico manteniendo actualizada la información de reparación. | RM-02, RM-03, RM-13 |

### 8.1.4. Question Backlog

Las preguntas se ordenan según cuatro criterios valorados de 1 a 5: confianza en la relevancia de la pregunta, riesgo de mantener la incertidumbre, impacto para el producto e interés de investigación. La puntuación total es la suma de los cuatro valores; ante un empate, la regla de desempate da prioridad a la pregunta con **mayor nivel de Riesgo**.

Los puntajes de `Q-01` a `Q-07` corresponden al registro de planificación de AV2, conservados sin alteración artificial. Para la entrega TB2 se incorpora `Q-08` (vinculada a `EC-08`) y se documenta que `Q-07` (`EC-03`) queda **no seleccionada** para el incremento técnico TB2 debido a que el equipo acordó no intervenir técnicamente la Landing Page en este ciclo (su sección 8.3.3.2 referenciará únicamente la evidencia existente).

| Prioridad | Pregunta | Confianza | Riesgo | Impacto | Interés | Total | Alcance en TB2 |
|---:|---|---:|---:|---:|---:|---:|---|
| 1 | Q-01: comprensión de fechas y retrasos | 4 | 5 | 5 | 5 | 19 | Seleccionada (`EC-01`) |
| 2 | Q-02: registro de órdenes en aplicación web | 4 | 4 | 5 | 5 | 18 | Seleccionada (`EC-02`) |
| 3 | Q-07: acceso a partir de los planes | 4 | 4 | 4 | 5 | 17 | **No seleccionada** (`EC-03` fuera de alcance técnico TB2) |
| 4 | Q-03: disponibilidad de repuestos frente a tarea | 4 | 4 | 4 | 4 | 16 | Seleccionada (`EC-04`) |
| 5 | Q-05: comprensión y corrección en formularios web | 4 | 4 | 4 | 3 | 15 | Seleccionada (`EC-06`) |
| 6 | Q-08: identificación y actualización de tareas del mecánico | 3 | 4 | 4 | 3 | 14 | Seleccionada (`EC-08`, nueva en TB2; desempata sobre Q-06 por mayor Riesgo) |
| 7 | Q-06: localización y prioridad de órdenes | 3 | 3 | 4 | 4 | 14 | Seleccionada (`EC-07`) |
| 8 | Q-04: confianza percibida en el seguimiento | 3 | 3 | 4 | 3 | 13 | Seleccionada (`EC-05`) |

### 8.1.5. Experiment Cards

Para la entrega TB2 se seleccionaron **siete Experiment Cards** (`EC-01`, `EC-02`, `EC-04`, `EC-05`, `EC-06`, `EC-07` y `EC-08`), concentradas en **cinco incrementos funcionales To-Be**:

1. **Seguimiento más claro para el propietario (`EC-01` + `EC-05`):** comparten una única mejora técnica en Customer Trust/seguimiento, pero miden preguntas y métricas distintas (comprensión objetiva frente a utilidad percibida para confiar).
2. **Flujo único de registro y recuperación de errores en formularios web (`EC-02` + `EC-06`):** comparten una única mejora técnica en el formulario web de órdenes en Vue, pero evalúan por separado la finalización del registro y la corrección autónoma de errores.
3. **Suficiencia de repuestos en inventario Android (`EC-04`):** incremento técnico único en Android para comparar existencias disponibles frente a requeridas.
4. **Priorización visible de órdenes (`EC-07`):** incremento técnico implementado en Frontend Web, que clasifica, ordena y filtra órdenes según su estado y fecha estimada de entrega, utilizando los datos existentes de la API.
5. **Localización y actualización de tareas del mecánico (`EC-08`):** incremento técnico en el módulo Mechanic de Android.

La tarjeta `EC-03` (`Q-07`) se conserva como pregunta no seleccionada para este ciclo. En todos los experimentos activos, se comparará una captura de la versión As-Is frente a la versión To-Be funcional utilizando casos y datos de prueba equivalentes, evitando mantener dos aplicaciones ejecutables en paralelo.

---

**EC-01 — Delivery Date Comprehension**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Los propietarios de vehículos comprenden la fecha actualizada de entrega y el motivo del retraso sin necesitar ayuda? |
| **Front Side** | **Why** | Cuando cambia la fecha estimada de entrega, la falta de claridad en la pantalla de seguimiento genera dudas constantes y obliga al propietario a contactar al taller. |
| **Front Side** | **What** | Actualizar la vista de seguimiento de AutoService para destacar la fecha estimada vigente, el motivo del retraso y el estado actual del servicio (implementación compartida con `EC-05`). |
| **Front Side** | **Hypothesis** | Creemos que si destacamos la fecha estimada vigente y el motivo del retraso en la vista de seguimiento, al menos el 66,7 % de los propietarios identificará ambos datos sin ayuda (`M-01`) y las solicitudes de asistencia (`M-04`) bajarán en al menos 33,3 puntos porcentuales frente a la presentación anterior. |
| **Back Side** | **Measures** | `M-01` (Comprensión autónoma del retraso) como métrica primaria y `M-04` (Solicitudes de asistencia) como métrica secundaria. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura de la pantalla de seguimiento As-Is con fecha vigente y motivo.<br>**Experimental Condition (B):** vista funcional To-Be de seguimiento evaluada con casos ficticios equivalentes. |
| **Back Side** | **Scale** | 3 propietarios de vehículos evaluados con dos casos equivalentes en sesiones moderadas. |

---

**EC-02 — Work Order Registration**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Las indicaciones de obligatoriedad y validaciones claras facilitan que un responsable del taller registre correctamente una orden de trabajo en la aplicación web? |
| **Front Side** | **Why** | Los registros incompletos o con errores de entrada retrasan la planificación del taller y generan reprocesos durante la atención del vehículo. |
| **Front Side** | **What** | Mejorar el formulario web de creación de órdenes en Vue mediante marcación visible de campos obligatorios, validaciones específicas y mensajes de corrección (implementación compartida con `EC-06`). |
| **Front Side** | **Hypothesis** | Creemos que si incorporamos campos obligatorios reconocibles y validaciones específicas en el formulario web de órdenes, al menos el 66,7 % de los responsables completará el registro sin ayuda (`M-02`), la mediana de tiempo (`M-03`) se reducirá en un 25 % y las solicitudes de asistencia (`M-04`) disminuirán en al menos 33,3 puntos porcentuales frente al flujo base. |
| **Back Side** | **Measures** | `M-02` (Finalización autónoma del registro) como métrica primaria; `M-03` (Mediana de tiempo de registro en segundos) y `M-04` (Solicitudes de asistencia) como métricas secundarias. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura/flujo del formulario As-Is sin indicaciones adicionales.<br>**Experimental Condition (B):** formulario web To-Be funcional probado con datos ficticios de cliente, vehículo y servicio. |
| **Back Side** | **Scale** | 3 responsables de taller evaluados durante el registro completo de órdenes en la aplicación web. |

---

**EC-03 — Access After Comparing Plans** *(Excluded from TB2)*

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Los responsables de taller encuentran cómo comenzar a usar AutoService o contactar al equipo después de comparar los planes? |
| **Front Side** | **Why** | Una ruta poco clara después de revisar los planes en la Landing Page puede hacer que un taller interesado abandone el sitio. |
| **Front Side** | **What** | Excluida del incremento técnico de TB2. No se realizan cambios ni pruebas nuevas sobre la Landing Page; la sección 8.3.3.2 referenciará únicamente la evidencia existente. |
| **Front Side** | **Hypothesis** | Creemos que diferenciar explícitamente los destinos posteriores a la comparación de planes permitiría que al menos el 66,7 % identifique el siguiente paso sin ayuda (`M-05`) frente a la navegación As-Is. |
| **Back Side** | **Measures** | `M-05` (Identificación autónoma del siguiente paso, conservada como histórica) y `M-04` (Solicitudes de asistencia). |
| **Back Side** | **Conditions** | **Control Condition (A):** navegación As-Is de la Landing Page.<br>**Experimental Condition (B):** no ejecutada en TB2 por decisión de alcance. |
| **Back Side** | **Scale** | 0 participantes (experimento fuera de alcance en TB2). |

---

**EC-04 — Available Spare Parts Identification**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Los usuarios del taller pueden identificar en Android si los repuestos disponibles alcanzan para realizar una tarea de reparación? |
| **Front Side** | **Why** | Mostrar solo el stock actual sin compararlo con la cantidad requerida impide anticipar faltantes antes de iniciar una reparación. |
| **Front Side** | **What** | Actualizar la consulta de inventario en Android para mostrar las existencias disponibles junto con la cantidad requerida para una tarea y un indicador de stock suficiente o insuficiente, usando datos de demostración declarados. |
| **Front Side** | **Hypothesis** | Creemos que si presentamos la cantidad disponible junto con la requerida y un indicador claro de suficiencia en Android, al menos el 66,7 % de los usuarios identificará correctamente cuándo el stock alcanza o falta (`M-06`) y las solicitudes de asistencia (`M-04`) bajarán en al menos 33,3 puntos porcentuales frente a la vista As-Is. |
| **Back Side** | **Measures** | `M-06` (Interpretación autónoma de disponibilidad) como métrica primaria y `M-04` (Solicitudes de asistencia) como métrica secundaria. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura As-Is con cantidades aisladas de inventario.<br>**Experimental Condition (B):** vista To-Be funcional en Android evaluando un caso con stock suficiente y otro con stock insuficiente. |
| **Back Side** | **Scale** | 3 responsables de taller evaluando ambos casos de inventario en sesiones moderadas. |

---

**EC-05 — Perceived Trust in Service Tracking**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿La información detallada sobre el seguimiento de una reparación mejora la utilidad percibida para confiar en el servicio del taller? |
| **Front Side** | **Why** | Un seguimiento que solo muestra el estado general no explica cambios de fecha ni demoras, lo que reduce la transparencia percibida por el cliente. |
| **Front Side** | **What** | Reutilizar la mejora implementada para `EC-01` (estado actual, fecha estimada vigente y motivo del retraso) evaluando la percepción de confianza del propietario. |
| **Front Side** | **Hypothesis** | Creemos que si ofrecemos el seguimiento detallado con estado, fecha vigente y motivo de retraso, al menos el 66,7 % de los propietarios valorará su utilidad para confiar en el servicio con 4 o 5 sobre 5 (`M-07`), superando en al menos 33,3 puntos porcentuales al seguimiento resumido As-Is. |
| **Back Side** | **Measures** | `M-07` (Porcentaje de valoraciones de 4 o 5 sobre 5 en utilidad para confiar) y comentarios cualitativos sobre información útil o faltante. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura de seguimiento resumido mostrando únicamente el estado general.<br>**Experimental Condition (B):** vista funcional To-Be con estado, fecha vigente y motivo; misma pregunta en escala de 1 a 5. |
| **Back Side** | **Scale** | 3 propietarios de vehículos evaluados bajo ambas presentaciones. |

---

**EC-06 — Form Comprehension and Error Correction**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Los usuarios identifican y corrigen con mayor facilidad los errores de validación al completar un formulario operativo del taller en la web? |
| **Front Side** | **Why** | Los mensajes genéricos bloquean el registro de información porque no indican qué campo tiene un dato inválido ni cómo resolverlo. En este ciclo el experimento se enfoca en formularios operativos web, separándose de la revisión histórica del acceso. |
| **Front Side** | **What** | Utilizar las validaciones y mensajes específicos por campo del formulario web mejorado en `EC-02` para evaluar la recuperación autónoma ante datos inválidos. |
| **Front Side** | **Hypothesis** | Creemos que si mostramos mensajes específicos por campo con indicaciones de corrección en los formularios operativos web, al menos el 66,7 % de los usuarios corregirá los errores sin ayuda (`M-08`) y las solicitudes de asistencia (`M-04`) se reducirán en al menos 33,3 puntos porcentuales frente al flujo As-Is. |
| **Back Side** | **Measures** | `M-08` (Corrección autónoma en formularios web) como métrica primaria y `M-04` (Solicitudes de asistencia) como métrica secundaria. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura/flujo As-Is con mensajes de error poco explicativos.<br>**Experimental Condition (B):** formulario web To-Be funcional con validaciones específicas y el mismo conjunto de errores inducidos. |
| **Back Side** | **Scale** | 3 responsables de taller evaluados con casos equivalentes de error en el formulario. |

---

**EC-07 — Order Localization and Prioritization**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Los responsables del taller pueden identificar qué órdenes requieren atención prioritaria cuando existen varios servicios activos? |
| **Front Side** | **Why** | Cuando un taller maneja varias órdenes simultáneamente, resulta difícil reconocer qué servicios requieren atención inmediata si el listado no presenta un criterio explícito de prioridad. |
| **Front Side** | **What** | Incorporar en el Frontend Web de AutoService una clasificación automática de órdenes según su estado y fecha estimada de entrega, mostrando el nivel de prioridad, su motivo, un ordenamiento por urgencia y un filtro de atención inmediata. La solución utiliza los datos existentes de la RESTful API, sin requerir modificaciones al Backend. |
| **Front Side** | **Hypothesis** | Creemos que si mostramos un criterio explícito de prioridad y permitimos filtrar las órdenes de atención inmediata, al menos el 66,7 % de los responsables localizará la orden prioritaria y explicará el criterio sin ayuda (`M-09`), reduciendo las solicitudes de asistencia (`M-04`) en al menos 33,3 puntos porcentuales frente al listado As-Is. |
| **Back Side** | **Measures** | `M-09` (Localización y prioridad de órdenes) como métrica primaria y `M-04` (Solicitudes de asistencia) como métrica secundaria. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura del listado Web As-Is, sin clasificación ni filtro explícito de prioridad.<br>**Experimental Condition (B):** listado Web To-Be con prioridades visibles, ordenamiento y filtro de atención inmediata. Ambas condiciones emplean las mismas órdenes ficticias para permitir la comparación. |
| **Back Side** | **Scale** | Piloto exploratorio planificado con 3 responsables de taller. La implementación técnica está completada, pero la hipótesis requiere validación mediante sesiones con participantes. |

**Reglas implementadas para la clasificación de prioridades**

| Prioridad | Criterio |
|---|---|
| **HIGH — Alta** | Orden activa vencida, con entrega estimada para hoy o mañana. |
| **REVIEW — Revisión** | Orden activa sin fecha estimada válida; requiere revisión de planificación. |
| **MEDIUM — Media** | Orden activa con entrega estimada dentro de 2 a 3 días. |
| **LOW — Baja** | Orden activa con entrega estimada posterior a 3 días. |
| **NONE — Sin prioridad operativa** | Orden finalizada, entregada o cancelada. |

Las órdenes se presentan considerando su urgencia y proximidad de entrega. El filtro **Ver atención inmediata** permite mostrar exclusivamente aquellas clasificadas como HIGH o REVIEW.

La funcionalidad se implementó en el Frontend Web utilizando los campos de estado y fecha estimada proporcionados por la API existente. Su implementación se integró en la rama `main` del repositorio Web mediante el Pull Request #29.

La demostración técnica utiliza órdenes ficticias y permite comprobar visualmente la clasificación y el filtrado. No constituye una medición de `M-09` o `M-04`, que requieren observaciones de participantes.

---

**EC-08 — Mechanic Task Identification and Update**

| Side | Element | Description |
|---|---|---|
| **Front Side** | **Question** | ¿Una presentación más clara de las tareas asignadas en Android permite que un mecánico identifique su siguiente actividad y actualice su progreso correctamente? |
| **Front Side** | **Why** | Si la vista del mecánico no resalta prioridad, estado y acción directa de actualización, aumenta el riesgo de elegir la tarea equivocada o dejar el avance desactualizado frente al administrador. |
| **Front Side** | **What** | Mejorar la pantalla de tareas asignadas del módulo Mechanic en Android, reutilizando la arquitectura y navegación existentes para destacar estado, prioridad y acción directa de actualización. |
| **Front Side** | **Hypothesis** | Creemos que si destacamos la siguiente tarea prioritaria junto con su estado y una acción clara de actualización en Android Mechanic, al menos el 66,7 % de los participantes identificará y actualizará su tarea correctamente sin ayuda (`M-10`), reduciendo la tasa de errores (`M-11`) en un 30 % y la asistencia (`M-04`) en al menos 33,3 puntos porcentuales frente a la vista As-Is. |
| **Back Side** | **Measures** | `M-10` (Identificación y actualización correcta de tareas) como métrica primaria; `M-11` (Tasa de errores en actualización de tareas) y `M-04` (Solicitudes de asistencia) como métricas secundarias. |
| **Back Side** | **Conditions** | **Control Condition (A):** captura de la pantalla As-Is de tareas asignadas en el módulo Mechanic.<br>**Experimental Condition (B):** flujo funcional To-Be en Android Mechanic con un escenario realista de múltiples tareas en distintos estados. |
| **Back Side** | **Scale** | 3 participantes con perfil técnico/mecánico evaluados en sesiones moderadas. |

---

## 8.2. Experiment Design

Los diseños presentados en esta sección definen el protocolo experimental para evaluar los incrementos To-Be en TB2. Las hipótesis, métricas y condiciones descritas corresponden a la planificación previa a la ejecución y no representan resultados observados; estos se consolidarán en la sección `8.4.1` una vez completadas las sesiones.

### 8.2.1. Hypotheses

Cada experimento se formula con su **Hypothesis Statement**, su **Alternative Hypothesis** ($H_n$) y su **Null Hypothesis** ($H_{0\text{-}n}$). Los porcentajes indican las metas esperadas para cada métrica (`M-XX`): en un estudio confirmatorio se contrastan con significación $p < 0{,}05$, mientras que en el piloto exploratorio de TB2 ($n = 3$) el umbral de 66,7 % equivale a al menos 2 de 3 participantes. *(La tarjeta `EC-03` se conserva solo como registro histórico sin ejecución en TB2).*

| Experimento | Hypothesis Statement | Alternative Hypothesis ($H_n$) | Null Hypothesis ($H_{0\text{-}n}$) |
|---|---|---|---|
| **EC-01** | Creemos que la respuesta es que destacar la fecha estimada vigente y el motivo del retraso en el seguimiento To-Be facilitará la comprensión del propietario, cuya evidencia se reflejará en al menos 66,7 % de identificación autónoma (`M-01`) y una reducción de al menos 33,3 p.p. en solicitudes de asistencia (`M-04`), bajo las circunstancias de consultas simuladas con 3 propietarios en AutoService. | **H1:** Destacar la fecha vigente y el motivo del retraso en el seguimiento To-Be permite alcanzar al menos 66,7 % de comprensión autónoma (`M-01`) y reduce las solicitudes de asistencia (`M-04`) en al menos 33,3 p.p. frente a la presentación As-Is ($p < 0{,}05$). | **H0-1:** La vista de seguimiento To-Be no produce mejora en la identificación autónoma (`M-01`) ni reduce la asistencia (`M-04`) frente a la presentación As-Is. Cualquier diferencia observada se debe al azar o a factores externos. |
| **EC-02** | Creemos que la respuesta es que incorporar campos obligatorios visibles y validaciones claras en el formulario web agilizará el registro, cuya evidencia se reflejará en al menos 66,7 % de finalización autónoma (`M-02`) y una reducción del 25 % en la mediana de tiempo (`M-03`), bajo las circunstancias del piloto con 3 responsables de taller en la aplicación web. | **H2:** El formulario web To-Be logra al menos 66,7 % de finalización autónoma (`M-02`), reduce en al menos 25 % la mediana de tiempo de registro (`M-03`) y reduce en al menos 33,3 p.p. la asistencia (`M-04`) frente al flujo As-Is ($p < 0{,}05$). | **H0-2:** El formulario web To-Be no genera mejora en la finalización autónoma (`M-02`) ni reduce el tiempo (`M-03`) o la asistencia (`M-04`) frente al flujo As-Is. Cualquier variación observada se debe al azar o a factores externos. |
| **EC-03** *(Excluded)* | Creemos que diferenciar los destinos desde los planes permitiría alcanzar al menos 66,7 % de identificación autónoma del siguiente paso (`M-05`) en la Landing Page. | **H3:** Los destinos diferenciados alcanzarían al menos 66,7 % en `M-05` frente a la navegación As-Is ($p < 0{,}05$). | **H0-3:** No habría diferencia en `M-05` respecto a la navegación As-Is. *(No ejecutada en TB2).* |
| **EC-04** | Creemos que la respuesta es que presentar en Android la cantidad disponible, la requerida y un indicador explícito de suficiencia evitará errores de interpretación, cuya evidencia se reflejará en al menos 66,7 % de respuestas autónomas correctas en casos suficientes e insuficientes (`M-06`), bajo las circunstancias de prueba con 3 responsables de taller. | **H4:** La consulta de inventario To-Be en Android alcanza al menos 66,7 % de interpretación autónoma correcta (`M-06`) y reduce la asistencia (`M-04`) en al menos 33,3 p.p. frente a la vista As-Is ($p < 0{,}05$). | **H0-4:** El indicador de suficiencia en Android no produce mejora en la interpretación del stock (`M-06`) ni reduce la asistencia (`M-04`) frente a la vista As-Is. Cualquier variación observada es producto del azar o factores externos. |
| **EC-05** | Creemos que la respuesta es que mostrar un seguimiento detallado con estado, fecha vigente y motivo aumentará la confianza percibida, cuya evidencia se reflejará en al menos 66,7 % de valoraciones de 4 o 5 sobre 5 (`M-07`) y un alza mínima de 33,3 p.p. frente al seguimiento resumido, bajo las circunstancias de evaluación con 3 propietarios. | **H5:** El seguimiento detallado To-Be logra al menos 66,7 % de valoraciones de 4 o 5 sobre 5 (`M-07`), incrementando en al menos 33,3 p.p. la proporción favorable frente al seguimiento resumido As-Is ($p < 0{,}05$). | **H0-5:** El seguimiento detallado To-Be no aumenta la proporción de valoraciones favorables (`M-07`) respecto al seguimiento resumido As-Is. Cualquier diferencia observada se debe al azar o a factores externos. |
| **EC-06** | Creemos que la respuesta es que mostrar mensajes específicos y guías de corrección en formularios operativos web facilitará la recuperación ante errores, cuya evidencia se reflejará en al menos 66,7 % de corrección autónoma (`M-08`), bajo las circunstancias de errores inducidos evaluados con 3 responsables. | **H6:** Los mensajes específicos en formularios operativos web To-Be permiten alcanzar al menos 66,7 % de corrección autónoma (`M-08`) y reducen la asistencia (`M-04`) en al menos 33,3 p.p. frente al flujo As-Is ($p < 0{,}05$). | **H0-6:** Los mensajes de validación del formulario web To-Be no mejoran la corrección autónoma (`M-08`) ni reducen la asistencia (`M-04`) respecto al flujo As-Is. Cualquier variación observada se atribuye al azar o a factores externos. |
| **EC-07** | Creemos que la respuesta es que exponer un criterio explícito de prioridad en el listado web de órdenes facilitará ubicar servicios urgentes, cuya evidencia se reflejará en al menos 66,7 % de localización y reconocimiento del criterio sin ayuda (`M-09`), bajo las circunstancias de múltiples órdenes activas con 3 responsables. | **H7:** El listado web To-Be con prioridad calculada en el Frontend Web a partir de los datos existentes de la API logra al menos 66,7 % de localización y comprensión autónoma (`M-09`) y reduce la asistencia (`M-04`) en al menos 33,3 p.p. frente al listado As-Is ($p < 0{,}05$). | **H0-7:** Exponer el criterio de prioridad en el listado web To-Be no produce mejora en la localización y priorización autónoma (`M-09`) frente al listado As-Is. Cualquier variación observada se debe al azar o a factores externos. |
| **EC-08** | Creemos que la respuesta es que destacar prioridad, estado y acción de actualización en Android Mechanic facilitará la ejecución del mecánico, cuya evidencia se reflejará en al menos 66,7 % de actualización autónoma correcta (`M-10`) y una reducción del 30 % en la tasa de errores (`M-11`), bajo las circunstancias de un escenario realista de tareas con 3 participantes. | **H8:** La vista de tareas To-Be en Android Mechanic logra al menos 66,7 % de identificación y actualización autónoma (`M-10`), reduce la tasa de errores (`M-11`) en al menos 30 % y reduce la asistencia (`M-04`) en al menos 33,3 p.p. frente a la vista As-Is ($p < 0{,}05$). | **H0-8:** La vista To-Be en Android Mechanic no genera mejora en la identificación y actualización autónoma (`M-10`) ni reduce la tasa de errores (`M-11`) o la asistencia (`M-04`) frente a la vista As-Is. Cualquier diferencia observada se atribuye al azar o a factores externos. |

### 8.2.2. Domain Business Metrics

Todas las medidas utilizadas en las Experiment Cards están formalmente catalogadas en esta sección. No se emplean métricas ad-hoc o informales fuera de este catálogo. Las metas deseadas expresan **umbrales objetivo de hipótesis** y no resultados observados.

| Código | Nombre de la Métrica | Fórmula de Cálculo | Técnica de Recolección | Meta Deseada |
|---|---|---|---|---|
| **M-01** | Comprensión autónoma del retraso | $(\text{Participantes que identifican fecha vigente y motivo sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada en sesiones `EC-01` (As-Is vs. To-Be). | $\ge 66{,}7\%$ en To-Be (incremento $\ge 33{,}3\text{ p.p.}$ vs. As-Is). |
| **M-02** | Finalización autónoma del registro | $(\text{Participantes que completan la orden web correctamente sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada y verificación de confirmación en `EC-02`. | $\ge 66{,}7\%$ en To-Be respecto a As-Is. |
| **M-03** | Tiempo de registro de orden | $\text{Mediana de segundos desde el inicio del formulario hasta la confirmación de creación}$ (tareas completadas) | Cronómetro registrado en ficha de observación durante `EC-02`. | Reducción $\ge 25\%$ en mediana de tiempo To-Be respecto a As-Is. |
| **M-04** | Solicitudes de asistencia | $(\text{Participantes que solicitan ayuda del moderador} / \text{Participantes evaluados}) \times 100$ | Conteo de intervenciones del moderador en la ficha de observación de cada card. | Reducción $\ge 33{,}3\text{ p.p.}$ en To-Be respecto a As-Is. |
| **M-05** | Identificación autónoma del siguiente paso *(Histórica — no aplicada en TB2)* | $(\text{Participantes que identifican una ruta adecuada tras revisar planes sin ayuda} / \text{Participantes evaluados}) \times 100$ | Registro histórico de diseño (`EC-03`, excluida de TB2). | No aplicable en TB2 (referencia histórica $\ge 66{,}7\%$). |
| **M-06** | Interpretación autónoma de disponibilidad | $(\text{Participantes que identifican correctamente si el stock es suficiente o insuficiente sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada con casos de stock suficiente e insuficiente en `EC-04`. | $\ge 66{,}7\%$ en To-Be respecto a As-Is. |
| **M-07** | Valoración de utilidad para confiar | $(\text{Participantes que valoran con 4 o 5 en escala de 1 a 5} / \text{Participantes evaluados}) \times 100$ | Cuestionario breve posterior a cada condición en `EC-05`. | $\ge 66{,}7\%$ de valoraciones $\ge 4$ (alza $\ge 33{,}3\text{ p.p.}$ vs. As-Is). |
| **M-08** | Corrección autónoma en formularios web | $(\text{Participantes que identifican y corrigen un dato inválido en el formulario operativo sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada sobre errores inducidos en `EC-06`. | $\ge 66{,}7\%$ en To-Be respecto a As-Is. |
| **M-09** | Localización y prioridad de órdenes | $(\text{Participantes que localizan la orden prioritaria y explican el criterio aplicado sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada sobre listado con múltiples órdenes en `EC-07`. | $\ge 66{,}7\%$ en To-Be respecto a As-Is. |
| **M-10** | Identificación y actualización correcta de tareas | $(\text{Participantes que identifican su tarea prioritaria y actualizan su estado al esperado sin ayuda} / \text{Participantes evaluados}) \times 100$ | Ficha de observación moderada y verificación de estado en Android Mechanic (`EC-08`). | $\ge 66{,}7\%$ en To-Be respecto a As-Is. |
| **M-11** | Tasa de errores en actualización de tareas | $(\text{Total de acciones erróneas o selecciones de tarea incorrecta} / \text{Total de intentos de tarea evaluados}) \times 100$ | Conteo estructurado de errores en la ficha de observación de `EC-08`. | Reducción $\ge 30\%$ en tasa de errores To-Be respecto a As-Is. |

La comprensión del retraso (`M-01`) y la utilidad percibida (`M-07`) se vinculan con la transparencia hacia el cliente; la finalización (`M-02`), el tiempo (`M-03`), la corrección de errores (`M-08`), la suficiencia de inventario (`M-06`), la priorización (`M-09`) y la ejecución del mecánico (`M-10`, `M-11`) miden eficiencia operativa. Ninguna de estas medidas equivale por sí sola a ingresos o retención financiera directa.

### 8.2.3. Measures

Para garantizar consistencia entre los cinco responsables al recoger datos reales:

- **Seguimiento (`EC-01` y `EC-05`):** el moderador solicitará al propietario indicar la fecha vigente y explicar el motivo del retraso (`M-01`). Se considerará correcta solo si ambos datos coinciden con el caso presentado y no medió asistencia (`M-04`). A continuación, se aplicará la pregunta de percepción (`EC-05`, `M-07`): *«¿Qué tan útil es esta información para confiar en el servicio del taller?»* en escala de 1 (nada útil) a 5 (muy útil), registrando comentarios cualitativos.
- **Registro y corrección de errores en formularios web (`EC-02` y `EC-06`):** en `EC-02` se comprobará que el responsable complete la orden hasta la confirmación de creación (`M-02`), cronometrando la duración (`M-03`); las tareas incompletas se excluyen de la mediana de tiempos y se reportan por separado. En `EC-06` se presentará un escenario con datos inválidos u omitidos y se verificará si el participante comprende el mensaje de error y lo corrige sin asistencia (`M-08`, `M-04`).
- **Disponibilidad de repuestos (`EC-04`):** el moderador presentará dos casos en Android (uno con stock suficiente y otro con stock insuficiente respecto a la cantidad requerida para una tarea) y registrará si el participante identifica correctamente ambos escenarios sin ayuda (`M-06`, `M-04`).
- **Localización y prioridad de órdenes (`EC-07`):** ante un conjunto equivalente de órdenes ficticias activas, se registrará si el participante localiza la orden que requiere atención prioritaria y reconoce el criterio aplicado sin ayuda (`M-09`, `M-04`).
- **Tareas del mecánico (`EC-08`):** ante un escenario realista de tareas asignadas en Android Mechanic, se verificará si el participante identifica la siguiente tarea relevante y actualiza su estado al valor solicitado sin ayuda (`M-10`), registrando el número de errores cometidos (`M-11`) y solicitudes de asistencia (`M-04`).

### 8.2.4. Conditions

En cada experimento activo, la condición de control se presenta mediante **capturas o registros equivalentes del estado As-Is** (sin mantener dos aplicaciones paralelas en ejecución), mientras que la condición experimental corresponde al **incremento To-Be funcional**. Se alternará el orden de exposición o se usarán conjuntos equivalentes de datos ficticios declarados para mitigar aprendizaje entre tareas.

| Experimento | Condición de Control / Referencia (As-Is) | Condición Experimental (To-Be) | Preparación y control |
|---|---|---|---|
| **EC-01** | Captura de pantalla de seguimiento As-Is con fecha vigente y motivo en formato base. | Pantalla funcional To-Be de seguimiento destacando fecha vigente, motivo y estado. | Dos casos ficticios equivalentes; orden alternado; mismos criterios de respuesta. |
| **EC-02** | Captura/flujo As-Is del formulario web de órdenes sin indicaciones de obligatoriedad ni mensajes guiados. | Formulario web To-Be funcional con campos obligatorios visibles y validaciones claras. | Datos ficticios equivalentes de cliente, vehículo y servicio en aplicación web. |
| **EC-03** | *No ejecutada en TB2.* | *No ejecutada en TB2.* | Excluida de ejecución; se conserva registro de decisión de alcance. |
| **EC-04** | Captura As-Is de inventario mostrando solo existencias actuales. | Vista Android To-Be funcional mostrando stock disponible, cantidad requerida e indicador de suficiencia. | Un caso de stock suficiente y un caso insuficiente con datos de demostración declarados. |
| **EC-05** | Captura de seguimiento resumido mostrando únicamente estado general. | Vista funcional To-Be (misma implementación de `EC-01`) con estado, fecha vigente y motivo. | Misma pregunta y escala 1–5 en ambas condiciones; se documenta que cambia el nivel de detalle. |
| **EC-06** | Captura/flujo As-Is con mensajes de error genéricos en formulario web. | Formulario web To-Be (misma implementación de `EC-02`) con mensajes específicos por campo. | Mismo conjunto de errores inducidos, mismo idioma e instrucciones equivalentes. |
| **EC-07** | Captura As-Is del listado básico de órdenes sin indicador ni ordenamiento de prioridad. | Listado web To-Be con prioridades calculadas en Vue, ordenamiento por urgencia y filtro de atención inmediata, utilizando los datos existentes de la API. | Las mismas tres órdenes ficticias en ambas condiciones, conservando sus estados y fechas estimadas para comparar la presentación As-Is y To-Be. |
| **EC-08** | Captura As-Is de la vista de tareas del módulo Mechanic en Android. | Flujo funcional To-Be en Android Mechanic destacando prioridad, estado y acción directa de actualización. | Escenario realista con múltiples tareas asignadas en estados distintos y cuenta de prueba. |

Las sesiones requieren el consentimiento informado de los participantes y utilizan cuentas y registros de prueba sin datos personales reales de clientes.

### 8.2.5. Scale Calculations and Decisions

Para determinar la escala de los experimentos se distinguen dos niveles metodológicos:

1. **Parámetros de referencia para un estudio confirmatorio:** conforme a la metodología XDPD, una validación estadística concluyente requeriría definir un nivel de significación ($\alpha = 5\%$), un poder estadístico ($1 - \beta = 80\% \text{ a } 95\%$) y un Efecto Mínimo Detectable (MDE) compatible con el diseño pareado para calcular el tamaño muestral formal.
2. **Escala real del piloto en TB2:** dado el alcance académico del incremento TB2, cada uno de los siete experimentos activos se ejecuta como un **piloto exploratorio moderado con $n = 3$ participantes por experimento** (cada respuesta representa $33{,}3\%$ del grupo).

Para evitar contaminación entre experimentos que comparten interfaz o dominio, se procurará asignar participantes distintos según segmento (propietarios para seguimiento `EC-01`/`EC-05`; responsables de taller para web `EC-02`/`EC-06`/`EC-07` e inventario `EC-04`; usuarios en rol mecánico/técnico para `EC-08`). Los resultados obtenidos con $n = 3$ se interpretarán estrictamente como **evidencia exploratoria para detectar dificultades y orientar decisiones de producto**, nunca como prueba estadísticamente concluyente.

### 8.2.6. Methods Selection

Se selecciona una **prueba moderada de tareas con observación directa y cuestionario breve posterior**. Durante cada sesión:

- El moderador explica el objetivo de la actividad, solicita autorización para registrar observaciones/capturas y aclara que el participante puede detener la sesión en cualquier momento.
- El participante revisa la referencia As-Is (mediante captura/caso base equivalente) y ejecuta la tarea solicitada en la aplicación To-Be funcional.
- El moderador no interviene salvo cuando el participante solicita ayuda explícita (lo cual queda registrado en `M-04`).
- Cada responsable de experimento registra los datos de sus tarjetas en una ficha estandarizada para evitar resúmenes informales y asegurar trazabilidad hacia `8.4.1`.

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

| Experimento | Objetivo analítico | Indicadores (`M-XX`) | Criterio de lectura exploratoria |
|---|---|---|---|
| **EC-01** | Evaluar comprensión autónoma de fecha vigente y motivo de retraso. | `M-01`, `M-04` | Comparar % de acierto autónomo y dudas observadas entre As-Is y To-Be. |
| **EC-02** | Evaluar finalización y eficiencia en el registro web de órdenes. | `M-02`, `M-03`, `M-04` | Comparar % de finalización sin ayuda, mediana de tiempo (solo completadas) y solicitudes de asistencia. |
| **EC-04** | Evaluar identificación de stock suficiente o insuficiente para una tarea. | `M-06`, `M-04` | Comparar % de respuestas correctas por caso (suficiente/insuficiente) y ayuda requerida. |
| **EC-05** | Explorar percepción de utilidad del seguimiento detallado para confiar. | `M-07` y comentarios | Comparar % de valoraciones $\ge 4$ sobre 5 y analizar motivos declarados. |
| **EC-06** | Evaluar comprensión y corrección autónoma de errores en formularios web. | `M-08`, `M-04` | Comparar % de corrección autónoma ante datos inválidos y asistencia solicitada. |
| **EC-07** | Evaluar localización de orden prioritaria y comprensión del criterio. | `M-09`, `M-04` | Comparar % de localización correcta y reconocimiento del criterio frente a As-Is. |
| **EC-08** | Evaluar identificación de siguiente tarea y actualización correcta en Android Mechanic. | `M-10`, `M-11`, `M-04` | Comparar % de tareas identificadas y actualizadas correctamente, tasa de errores y asistencia. |

### 8.2.8. Web and Mobile Tracking Plan

La recolección se realiza mediante fichas estructuradas de observación (sin incorporar herramientas externas de analítica automatizada en esta etapa). Cada registro se identifica con un código anónimo (`P-01`, `P-02`, ...) y documenta plataforma, condición, resultado cuantitativo por métrica y observaciones cualitativas.

| Experimento | Actividad observada | Plataforma | Datos registrados | Métricas vinculadas |
|---|---|---|---|---|
| **EC-01** | Consultar fecha estimada vigente y motivo del retraso. | Web (seguimiento público) | ID participante, orden de condición, acierto fecha, acierto motivo, asistencia y dudas. | `M-01`, `M-04` |
| **EC-02** | Registrar una orden de trabajo completa. | Aplicación Web (Vue) | ID participante, condición, finalización correcta, tiempo (s), campos con dificultad y asistencia. | `M-02`, `M-03`, `M-04` |
| **EC-04** | Verificar suficiencia de repuestos para una tarea de reparación. | Aplicación Móvil (Android) | ID participante, condición, caso (suficiente/insuficiente), respuesta correcta y asistencia. | `M-06`, `M-04` |
| **EC-05** | Valorar la utilidad del seguimiento para confiar en el taller. | Web (seguimiento público) | ID participante, condición, puntaje 1–5 y explicación cualitativa. | `M-07` |
| **EC-06** | Identificar y corregir errores inducidos en formulario web. | Aplicación Web (Vue) | ID participante, condición, corrección autónoma, mensajes revisados y asistencia. | `M-08`, `M-04` |
| **EC-07** | Localizar la orden prioritaria entre varios servicios activos. | Web + RESTful API | ID participante, condición, orden seleccionada, comprensión del criterio y asistencia. | `M-09`, `M-04` |
| **EC-08** | Identificar la siguiente tarea asignada y actualizar su estado. | Aplicación Móvil (Android Mechanic) | ID participante, condición, tarea elegida, estado final, conteo de errores y asistencia. | `M-10`, `M-11`, `M-04` |

## 8.3. Experimentation

Los incrementos descritos en esta sección corresponden a las siete tarjetas priorizadas para TB2 (agrupadas en cinco cambios funcionales) y a la exclusión documentada de `EC-03`. Los criterios de aceptación de `8.3.1` se redactan en formato Gherkin verificable (tercera persona, tiempo presente y orientados a reglas de negocio, sin referencias visuales específicas de interfaz).

### 8.3.1. To-Be User Stories

| ID | Card / Pregunta | Historia de usuario To-Be | Criterio de aceptación (Gherkin) |
|---|---|---|---|
| **EXP-US-01** | `EC-01` / `Q-01` | Como **Propietario de vehículo**, quiero consultar de forma destacada la fecha estimada vigente y el motivo de un retraso en el seguimiento para comprender cuándo se espera la entrega de mi vehículo sin solicitar ayuda. | **Given** que una orden de trabajo cuenta con fecha estimada y un motivo de retraso registrado,<br>**When** el propietario consulta el código de seguimiento,<br>**Then** el sistema presenta la fecha estimada vigente, el estado actual y el motivo del retraso de forma comprensible y diferenciada. |
| **EXP-US-02** | `EC-02` / `Q-02` | Como **Administrador del taller**, quiero registrar una orden de trabajo en la aplicación web con campos obligatorios identificados y validaciones claras para completar el servicio sin omitir información clave. | **Given** que el administrador inicia el registro de una nueva orden de trabajo,<br>**When** ingresa o envía los datos del servicio,<br>**Then** el sistema identifica los campos obligatorios requeridos y confirma el registro únicamente cuando la información cumple las reglas de validación. |
| **EXP-US-03** | `EC-04` / `Q-03` | Como **Administrador del taller**, quiero visualizar en Android si la cantidad disponible de un repuesto alcanza frente a la cantidad requerida para una tarea para anticipar faltantes antes de iniciar la reparación. | **Given** que una tarea de reparación requiere una cantidad específica de un repuesto registrado en inventario,<br>**When** el usuario consulta la disponibilidad del repuesto para dicha tarea,<br>**Then** el sistema compara la cantidad disponible con la requerida e indica explícitamente si el stock es suficiente o insuficiente. |
| **EXP-US-04** | `EC-06` / `Q-05` | Como **Administrador del taller**, quiero recibir mensajes específicos ante datos inválidos en los formularios operativos web para corregir los errores de entrada de forma autónoma y continuar la operación. | **Given** que el usuario ingresa un dato inválido u omite un campo obligatorio en un formulario operativo,<br>**When** el sistema evalúa las reglas de validación del formulario,<br>**Then** informa de manera específica qué dato requiere atención y qué corrección debe aplicarse para habilitar el envío. |
| **EXP-US-05** *(Excluida TB2)* | `EC-03` / `Q-07` | Como **Administrador del taller** interesado en AutoService, quiero identificar el siguiente paso después de comparar los planes para iniciar el registro o contactar al equipo. | *(Historia conservada en histórico; excluida del incremento técnico TB2 por decisión de alcance sobre la Landing Page).* |
| **EXP-US-06** | `EC-05` / `Q-04` | Como **Propietario de vehículo**, quiero consultar información detallada sobre el estado, la fecha estimada y el motivo de posibles cambios en el seguimiento para valorar la confiabilidad del servicio del taller. | **Given** que existe una orden de trabajo con seguimiento activo,<br>**When** el propietario consulta el detalle del servicio,<br>**Then** el sistema proporciona estado actual, fecha estimada vigente y justificación de cambios registrados como soporte informativo del servicio. |
| **EXP-US-07** | `EC-07` / `Q-06` | Como **Administrador del taller**, quiero consultar las órdenes activas con un criterio explícito de prioridad para localizar de forma inmediata los servicios que requieren atención urgente. | **Given** que existen múltiples órdenes de trabajo activas con distintas fechas comprometidas, estados y tareas pendientes,<br>**When** el administrador consulta el listado de órdenes,<br>**Then** la interfaz Web clasifica las órdenes utilizando su estado y fecha estimada, muestra el motivo de la prioridad, ordena los servicios por urgencia y permite filtrar las órdenes que requieren atención inmediata. |
| **EXP-US-08** | `EC-08` / `Q-08` | Como **Mecánico**, quiero visualizar con claridad mis tareas asignadas priorizadas y ejecutar la actualización de su estado en Android para identificar mi siguiente actividad y mantener actualizado el progreso de la reparación. | **Given** que el mecánico tiene tareas asignadas en diferentes estados dentro de órdenes activas,<br>**When** consulta su lista de tareas asignadas y selecciona actualizar el progreso de una actividad,<br>**Then** el sistema destaca la prioridad y el estado vigente de cada tarea y registra la transición de estado solicitada manteniendo la trazabilidad de la orden. |

### 8.3.2. To-Be Product Backlog

| Prioridad | Historia | Card vinculada | Incremento funcional To-Be | Valor esperado | Estado de implementación |
|---:|---|---|---|---|---|
| 1 | `EXP-US-01` | `EC-01` | Seguimiento To-Be (compartido con `EC-05`) | Mejorar la comprensión de fecha vigente y retraso. | Planificada para ejecución To-Be. |
| 2 | `EXP-US-02` | `EC-02` | Formulario web de órdenes (compartido con `EC-06`) | Reducir errores y tiempo en creación de órdenes web. | Planificada para ejecución To-Be. |
| 3 | `EXP-US-03` | `EC-04` | Consulta de suficiencia en inventario Android | Anticipar faltantes frente a tareas de reparación. | Planificada para ejecución To-Be. |
| 4 | `EXP-US-04` | `EC-06` | Formulario web de órdenes (compartido con `EC-02`) | Facilitar recuperación autónoma ante errores de entrada. | Planificada para ejecución To-Be. |
| 5 | `EXP-US-08` | `EC-08` | Vista y actualización de tareas en Android Mechanic | Mejorar identificación y registro de avance del mecánico. | Planificada para ejecución To-Be. |
| 6 | `EXP-US-07` | `EC-07` | Clasificación de prioridades, ordenamiento y filtro de atención inmediata en Frontend Web | Facilitar la identificación de órdenes urgentes para organizar el trabajo del taller. | Implementada en Web mediante PR #29 fusionado a `main`; validación experimental con participantes pendiente. |
| 7 | `EXP-US-06` | `EC-05` | Seguimiento To-Be (compartido con `EC-01`) | Evaluar utilidad percibida del detalle para confiar. | Planificada para ejecución To-Be. |
| — | `EXP-US-05` | `EC-03` | Landing Page (sin intervención técnica) | Histórico de navegación desde planes. | Excluida del incremento técnico TB2. |


### 8.3.3. To-Be Product Implementation and Deployment

El To-Be Sprint de AutoService comprende los incrementos funcionales asociados con las siete Experiment Cards seleccionadas para TB2. Las mejoras abarcan el seguimiento público de reparaciones, el registro de órdenes, la gestión de inventario, la priorización de servicios y las tareas del mecánico.

Cada incremento se documenta con su alcance funcional y las evidencias disponibles. Se distingue entre la implementación técnica de una funcionalidad y la validación experimental de su hipótesis, que requiere observaciones de participantes y mediciones de las métricas definidas en 8.2.

#### 8.3.3.1. To-Be Sprint Backlogs

El Sprint Backlog contempla cinco incrementos funcionales agrupados a partir de las siete tarjetas activas.

| Incremento | Experiment Cards | Producto | Evidencia en el informe |
|---|---|---|---|
| Seguimiento detallado de reparaciones | `EC-01`, `EC-05` | Seguimiento público | A documentar por el responsable |
| Registro de órdenes y corrección de errores | `EC-02`, `EC-06` | Frontend Web | A documentar por el responsable |
| Suficiencia de repuestos | `EC-04` | Android | Implementación y evidencias documentadas |
| Priorización de órdenes de trabajo | `EC-07` | Frontend Web | Implementación y evidencias documentadas |
| Identificación y actualización de tareas | `EC-08` | Android Mechanic | A documentar por el responsable |

La columna de evidencias indica el estado de documentación de este capítulo; no determina por sí sola si los demás incrementos se encuentran implementados. Los respectivos responsables incorporarán sus resultados técnicos y las evidencias verificables.

**Desglose del Sprint Backlog correspondiente a EC-04**

El incremento Android de `EC-04`, relacionado con `Q-03` y `EXP-US-03`, permite consultar si las existencias de un repuesto alcanzan para una tarea de reparación.

La siguiente tabla registra retrospectivamente las tareas de este incremento. No sustituye la consolidación del Sprint Backlog general ni acredita una reunión de planificación no documentada.

| Tarea | Responsable | Estado | Evidencia |
|---|---|---|---|
| Registrar el inventario anterior al cambio | Mario Fernández | Completada | Captura As-Is |
| Implementar el cálculo de suficiencia y cantidad faltante | Mario Fernández | Integrada | `StockAvailability.kt`; PR #23 |
| Consultar órdenes y tareas para la comparación | Mario Fernández | Integrada | `ManagementViewModel.kt`; PR #23 |
| Incorporar el panel y el selector de tareas en Inventario | Mario Fernández | Integrada | Capturas To-Be; PR #23 |
| Incorporar textos en inglés y español | Mario Fernández | Integrada | Recursos `stock_availability_strings.xml` |
| Verificar un caso suficiente con datos del Backend | Mario Fernández | Completada | Captura de Cambio de bujías |
| Verificar ambos resultados con datos locales controlados | Mario Fernández | Completada | Captura de vista previa interactiva |
| Evaluar comprensión y solicitudes de asistencia | Mario Fernández | Pendiente | Registro de participantes para `M-06` y `M-04` |
| Consolidar las tareas de los otros incrementos | Mario Fernández, con aportes del equipo | Pendiente | Información verificable de cada responsable |

La implementación se trabajó en la rama `feature/tb2-ec04-parts-availability` y se integró a `develop` mediante el [Pull Request #23](https://github.com/upc-shift-tech-solutions-team-1/autoservice-mobile/pull/23).

**Desglose del Sprint Backlog correspondiente a EC-07**

El incremento Web de `EC-07`, relacionado con `Q-06` y `EXP-US-07`, introduce clasificación de prioridades, ordenamiento por urgencia y un filtro de atención inmediata en las órdenes de trabajo.

| Tarea | Responsable | Estado | Evidencia |
|---|---|---|---|
| Registrar el listado de órdenes antes del cambio | Juan Sánchez | Completada | Captura As-Is |
| Implementar la clasificación por estado y fecha estimada | Juan Sánchez | Integrada | `work-order-list.vue`; PR Web #29 |
| Presentar prioridad y motivo en cada orden | Juan Sánchez | Integrada | `WorkOrderCard.vue`; PR Web #29 |
| Incorporar ordenamiento y filtro de atención inmediata | Juan Sánchez | Integrada | Capturas To-Be; PR Web #29 |
| Comprobar la presentación con órdenes ficticias equivalentes | Juan Sánchez | Completada | Capturas To-Be con `ECA-701`, `ECA-702` y `ECA-703` |
| Verificar la compilación de producción | Juan Sánchez | Completada | Ejecución satisfactoria de `npm run build` |
| Evaluar localización autónoma y solicitudes de asistencia | Juan Sánchez | Pendiente | Registro de participantes para `M-09` y `M-04` |

La implementación se integró en la rama `main` del repositorio Frontend Web mediante el Pull Request #29. No requirió modificaciones al Backend.

Los demás incrementos incorporarán sus propios desgloses de tareas cuando sus responsables proporcionen información verificable.

#### 8.3.3.2. To-Be Landing Page

La Experiment Card `EC-03`, relacionada con la navegación posterior a la comparación de planes, quedó fuera del incremento técnico de TB2. Por esta razón, no se implementó una modificación nueva de la Landing Page como parte de este ciclo.

Las observaciones previas sobre la Landing Page permanecen documentadas en los apartados correspondientes del informe. No se atribuyen resultados experimentales nuevos a `EC-03`.

#### 8.3.3.3. To-Be Web Application

##### EC-07 — Implementación de priorización de órdenes de trabajo

**Objetivo del incremento**

Facilitar que el administrador de un taller identifique las órdenes que necesitan atención prioritaria cuando existen varios servicios activos.

La mejora consiste en incorporar criterios visibles de prioridad, ordenamiento por urgencia y un filtro de atención inmediata en el listado Web de órdenes de trabajo.

**Situación As-Is**

Antes del incremento, el listado de órdenes permitía consultar los servicios registrados y sus estados, pero no contaba con una clasificación explícita de prioridades ni con un filtro específico para aislar las órdenes de atención inmediata.

Esto obligaba al administrador a revisar individualmente las fechas estimadas de entrega y los estados de las órdenes para decidir cuáles requerían atención primero.

Para establecer la referencia As-Is se utilizó una versión anterior del Frontend Web, conservando órdenes ficticias equivalentes a las empleadas en la demostración To-Be.

![EC-07 - Listado de órdenes de trabajo As-Is](../assets/images/chapter-8/ec-07-as-is-work-orders.jpeg)

*Figura 8.1. Estado As-Is del listado Web de órdenes de trabajo, antes de incorporar la clasificación explícita de prioridades.*

**Situación To-Be**

Se implementó una clasificación automática de las órdenes utilizando la información existente de su estado y fecha estimada de entrega.

La mejora se desarrolló en el Frontend Web con Vue, sin modificar los endpoints del Backend ni la estructura de persistencia.

Las reglas aplicadas fueron las siguientes:

| Clasificación | Condición | Interpretación operativa |
|---|---|---|
| HIGH — Alta | Orden activa vencida o con entrega estimada para hoy o mañana | Requiere atención urgente |
| REVIEW — Revisión | Orden activa sin fecha estimada válida | Requiere revisión de planificación |
| MEDIUM — Media | Orden activa con entrega estimada dentro de 2 a 3 días | Requiere seguimiento próximo |
| LOW — Baja | Orden activa con entrega estimada posterior a 3 días | Puede atenderse según planificación |
| NONE — Sin prioridad operativa | Orden finalizada, entregada o cancelada | No requiere priorización activa |

La interfaz presenta un indicador de prioridad y su motivo en cada orden. Asimismo, organiza los servicios por urgencia para facilitar su revisión.

**Evidencia del listado To-Be**

Para demostrar las diferencias entre las clasificaciones se utilizaron órdenes ficticias identificadas como `ECA-701`, `ECA-702` y `ECA-703`, con distintas fechas estimadas de entrega.

Estos registros son datos de demostración y no corresponden a vehículos de clientes reales.

![EC-07 - Priorización visible de órdenes To-Be](../assets/images/chapter-8/ec-07-to-be-priorities.jpeg)

*Figura 8.2. Listado Web To-Be con clasificación visible de prioridades y organización de las órdenes según su urgencia.*

**Filtro de atención inmediata**

Además de mostrar las prioridades, se incorporó el filtro **Ver atención inmediata**, que permite aislar las órdenes clasificadas como HIGH o REVIEW.

De esta manera, el administrador puede concentrar su atención en los servicios urgentes o que necesitan revisión de planificación, sin recorrer todo el listado.

![EC-07 - Filtro de atención inmediata To-Be](../assets/images/chapter-8/ec-07-to-be-urgent-filter.jpeg)

*Figura 8.3. Aplicación del filtro de atención inmediata en el listado Web To-Be, mostrando únicamente las órdenes que cumplen los criterios de urgencia o revisión.*

**Implementación técnica**

La funcionalidad se desarrolló en los siguientes componentes del Frontend Web:

- `src/domains/workshop-operations/presentation/work-order-list.vue`: clasificación de órdenes, ordenamiento por urgencia y control del filtro de atención inmediata.
- `src/domains/workshop-operations/presentation/components/work-orders/WorkOrderCard.vue`: presentación visual del nivel de prioridad y del motivo correspondiente.

La solución reutiliza los campos de estado y fecha estimada proporcionados por la API existente.

Se conservaron las funcionalidades previas del listado, incluyendo la búsqueda, los filtros por estado y la información existente sobre riesgo de retraso. El nuevo criterio de prioridad corresponde a una mejora adicional de apoyo a la gestión operativa.

**Integración del incremento**

La implementación se incorporó al repositorio del Frontend Web mediante el Pull Request **#29**, fusionado en la rama `main`.

La compilación de producción del Frontend Web finalizó satisfactoriamente después de la integración.

**Alcance de la evidencia**

Las capturas As-Is y To-Be permiten documentar el cambio visual y funcional, mientras que la integración del código y la compilación satisfactoria respaldan la entrega técnica.

Sin embargo, estas evidencias no demuestran todavía que los administradores localicen órdenes urgentes con mayor precisión ni que soliciten menos asistencia.

La hipótesis de `EC-07` se evaluará mediante las métricas `M-09` y `M-04`, utilizando el protocolo experimental establecido en 8.2 y registrando los resultados observados en 8.4.

#### 8.3.3.4. Implemented Native-Mobile Application To-Be Evidence

**EC-04 — Disponibilidad de repuestos para una tarea**

Se implementó en Android la consulta de suficiencia de repuestos asociados a una tarea de reparación. El incremento corresponde a `EXP-US-03` y permite comparar cantidades requeridas con las existencias consultadas en inventario.

**Estado anterior As-Is**

El inventario mostraba existencias, stock mínimo y datos comerciales del producto. Sin embargo, no comparaba esas cantidades con los repuestos requeridos para una tarea específica.

![Inventario anterior al incremento EC-04](../assets/images/chapter-8/ec04-01-inventario-as-is.png)

*Referencia As-Is conservada antes de modificar la pantalla.*

**Panel To-Be integrado en Inventario**

Se añadió un panel con selector de tareas obtenidas de las órdenes del Backend. La consulta mantiene el listado de productos existente y no modifica las cantidades almacenadas.

![Panel de disponibilidad integrado en Inventario](../assets/images/chapter-8/ec04-02-panel-to-be.png)

*Pantalla To-Be con el acceso a la consulta por tarea.*

Para cada repuesto, el panel muestra la cantidad requerida, la disponible y el resultado de la comparación. Cuando el stock es insuficiente, informa cuántas unidades faltan. Si un repuesto aparece varias veces en una tarea, suma sus cantidades requeridas.

La comparación considera suficiente una cantidad disponible mayor o igual que la requerida. Cuando no puede verificar las existencias o encuentra cantidades inválidas, muestra una indicación diferenciada en lugar de afirmar que el stock es suficiente.

**Verificación con datos del Backend**

En el emulador se seleccionó la tarea Cambio de bujías. La tarea requería 1 unidad y el inventario consultado mostraba 19 unidades disponibles. El panel presentó correctamente stock suficiente.

![Consulta de una tarea con stock suficiente](../assets/images/chapter-8/ec04-03-stock-suficiente.png)

*Caso observado en la aplicación conectada al Backend: 19 disponibles frente a 1 requerido.*

**Verificación local de suficiencia e insuficiencia**

Para comprobar ambos resultados sin alterar los registros compartidos, se utilizó una vista previa interactiva temporal de Jetpack Compose. Los datos fueron ficticios y estuvieron identificados como demostración local sin Backend.

| Repuesto de demostración | Disponible | Requerido | Resultado observado |
|---|---:|---:|---|
| Bujías | 6 | 4 | Stock suficiente |
| Filtro de aceite | 1 | 2 | Stock insuficiente; falta 1 |

![Verificación local con datos ficticios identificados](../assets/images/chapter-8/ec04-04-verificacion-local-suficiente-insuficiente.png)

*Comprobación del mismo componente y cálculo mediante datos locales controlados. No representa una ejecución del caso insuficiente contra el Backend. El archivo temporal de la vista previa se retiró antes de entregar el incremento.*

**Alcance y trazabilidad**

La consulta no reserva ni consume existencias. Su resultado corresponde a los datos consultados y no garantiza disponibilidad futura; por ello, la interfaz recomienda actualizar el inventario antes de tomar una decisión operativa.

El cambio está integrado en `develop` y puede revisarse en el [PR #23](https://github.com/upc-shift-tech-solutions-team-1/autoservice-mobile/pull/23).

Las capturas documentan la implementación y su verificación funcional. No constituyen resultados de evaluación con participantes. La recogida de datos de comprensión autónoma (`M-06`) y solicitudes de asistencia (`M-04`) permanece pendiente.

La evidencia del incremento Mechanic `EC-08` se incorporará con el aporte de su responsable, evitando duplicar o atribuir resultados todavía no verificados.
<br>

<div align="center">
  <img src="../assets/images/capitulo-3.png" alt="Capitulo 3" />
</div>

<br>

# 3.1. To-Be Scenario Mapping

(COMPLETAR)

# 3.2. User Stories

<p>
En la presente sección se definen las historias finales del producto AutoService, organizadas según los tres roles válidos del proyecto:
<b>Administrador</b>, <b>Mecánico</b> y <b>Cliente</b>. Las historias se orientan a la estrategia de negocio del taller, priorizando trazabilidad operativa, transparencia del servicio, coordinación del personal técnico, control de calidad, reducción de retrasos y mejora de la satisfacción del Cliente.
</p>

<p>
A diferencia de un enfoque centrado únicamente en pantallas o acciones CRUD, las User Stories se redactan considerando el valor que aportan al negocio automotriz. Cada historia incluye criterios de aceptación en formato Gherkin, permitiendo validar claramente el comportamiento esperado de la plataforma.
</p>

<div align="center">

<table style="margin: auto; text-align: left; width: 100%; border-collapse: collapse;">
<thead>
<tr>
<th style="width: 8%;">ID</th>
<th style="width: 14%;">Epic</th>
<th style="width: 16%;">Título</th>
<th style="width: 10%;">Rol</th>
<th style="width: 24%;">User Story</th>
<th style="width: 18%;">Objetivo de negocio</th>
<th style="width: 10%;">Criterios de aceptación</th>
</tr>
</thead>

<tbody>

<tr>
<td><b>US-01</b></td>
<td>EP-01 Acceso y experiencia por rol</td>
<td>Acceder de forma segura al sistema</td>
<td>Administrador / Mecánico / Cliente</td>
<td>Como <b>Administrador, Mecánico o Cliente</b>, quiero iniciar sesión de forma segura para acceder únicamente a las funciones que corresponden a mi participación en el servicio automotriz.</td>
<td>Proteger la información operativa del taller, evitar accesos incorrectos y mantener la trazabilidad de cada acción realizada.</td>
<td><b>Given</b> que el actor tiene credenciales registradas,<br><b>When</b> ingresa correo y contraseña válidos,<br><b>Then</b> la plataforma valida la identidad y redirige al panel correspondiente según su rol.</td>
</tr>

<tr>
<td><b>US-02</b></td>
<td>EP-01 Acceso y experiencia por rol</td>
<td>Acceder a una experiencia según rol operativo</td>
<td>Administrador / Mecánico / Cliente</td>
<td>Como <b>Administrador, Mecánico o Cliente</b>, quiero ingresar a una experiencia diferenciada según mi rol para evitar confusión y utilizar solo las funciones necesarias para mi participación.</td>
<td>Reducir errores de navegación y asegurar que cada actor cumpla correctamente su función dentro del flujo del taller.</td>
<td><b>Given</b> que el actor inició sesión correctamente,<br><b>When</b> la plataforma identifica su rol,<br><b>Then</b> redirige al Administrador al panel de gestión, al Mecánico a su espacio de tareas y al Cliente al seguimiento de su vehículo.</td>
</tr>

<tr>
<td><b>US-03</b></td>
<td>EP-01 Acceso y experiencia por rol</td>
<td>Crear cuenta según tipo de participación</td>
<td>Administrador / Cliente</td>
<td>Como <b>Administrador o Cliente</b>, quiero crear una cuenta según mi tipo de participación para que la plataforma configure desde el inicio una experiencia adecuada a mis necesidades.</td>
<td>Facilitar la adopción de AutoService y separar correctamente la gestión del taller del seguimiento del servicio.</td>
<td><b>Given</b> que el actor no tiene cuenta registrada,<br><b>When</b> selecciona crear cuenta y elige su tipo de participación,<br><b>Then</b> la plataforma solicita los datos necesarios y asigna permisos iniciales según el rol.</td>
</tr>

<tr>
<td><b>US-04</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Acceder al seguimiento mediante código seguro</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero acceder al seguimiento de mi vehículo mediante un código seguro para consultar el avance del servicio sin depender de llamadas constantes al taller.</td>
<td>Reducir consultas repetitivas, proteger la información del servicio y mejorar la autonomía del Cliente.</td>
<td><b>Given</b> que el Cliente recibió un código válido,<br><b>When</b> ingresa el código en la vista de seguimiento,<br><b>Then</b> la plataforma muestra la orden asociada a su vehículo sin exponer información de otros clientes.</td>
</tr>

<tr>
<td><b>US-05</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Monitorear avances reales de reparación</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero monitorear el avance real de reparación de mi vehículo mediante etapas visibles y porcentaje de progreso para reducir incertidumbre durante el servicio.</td>
<td>Incrementar transparencia, reducir llamadas repetitivas y mejorar la satisfacción del Cliente.</td>
<td><b>Given</b> que el Cliente accedió al seguimiento de su vehículo,<br><b>When</b> visualiza el estado del servicio,<br><b>Then</b> la plataforma muestra etapa actual, porcentaje de avance y etapas completadas según tareas registradas.</td>
</tr>

<tr>
<td><b>US-06</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Visualizar detalle operativo del servicio</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero visualizar el detalle operativo del servicio para comprender qué trabajos se realizan, qué tareas siguen pendientes y por qué mi vehículo se encuentra en determinada etapa.</td>
<td>Aumentar confianza y reducir reclamos mediante información clara sobre tareas, diagnóstico y avances.</td>
<td><b>Given</b> que el Cliente consulta el detalle del servicio,<br><b>When</b> selecciona la opción de ver detalles,<br><b>Then</b> la plataforma muestra diagnóstico resumido, tareas realizadas, tareas pendientes, evidencias y observaciones relevantes.</td>
</tr>

<tr>
<td><b>US-07</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Consultar fecha estimada de entrega actualizada</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero consultar la fecha y hora estimada de entrega de mi vehículo según el avance real del servicio para organizar mi disponibilidad.</td>
<td>Gestionar expectativas del Cliente y mejorar la percepción de cumplimiento del taller.</td>
<td><b>Given</b> que la orden tiene una fecha estimada,<br><b>When</b> el Cliente consulta el seguimiento,<br><b>Then</b> la plataforma muestra fecha y hora estimada e indica si depende de repuestos, recambios o bloqueos operativos.</td>
</tr>

<tr>
<td><b>US-08</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Identificar al Mecánico responsable del servicio</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero identificar al Mecánico asignado a mi vehículo para saber quién está atendiendo mi servicio y aumentar mi confianza en el taller.</td>
<td>Reforzar transparencia operativa sin exponer información interna innecesaria del taller.</td>
<td><b>Given</b> que la orden tiene un Mecánico asignado,<br><b>When</b> el Cliente visualiza el estado del vehículo,<br><b>Then</b> la plataforma muestra nombre, foto y especialidad del Mecánico sin mostrar carga laboral ni datos privados.</td>
</tr>

<tr>
<td><b>US-09</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Consultar historial de avances del servicio</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero consultar el historial de avances de mi servicio en una línea de tiempo para conocer qué etapas fueron completadas y cuándo ocurrieron.</td>
<td>Aumentar trazabilidad, transparencia y confianza mediante eventos visibles del servicio.</td>
<td><b>Given</b> que la orden tiene eventos registrados,<br><b>When</b> el Cliente accede al historial,<br><b>Then</b> la plataforma muestra etapas completadas con fecha y hora, diferenciando etapa actual y etapas pendientes.</td>
</tr>

<tr>
<td><b>US-10</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Consultar resumen económico y fecha del servicio</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero consultar un resumen económico con costo total, desglose y fecha estimada para entender el monto final antes de pagar el servicio.</td>
<td>Aumentar transparencia financiera y reducir reclamos por cobros no comprendidos.</td>
<td><b>Given</b> que la orden tiene cotización final confirmada,<br><b>When</b> el Cliente revisa el resumen del servicio,<br><b>Then</b> la plataforma muestra costo total, fecha estimada, desglose por conceptos y subtotal.</td>
</tr>

<tr>
<td><b>US-11</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Seleccionar y confirmar método de pago</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero seleccionar y confirmar el método de pago más conveniente para cerrar correctamente la atención de mi vehículo.</td>
<td>Facilitar el cierre del servicio, reducir fricción de pago y aumentar el cobro oportuno.</td>
<td><b>Given</b> que el Cliente desea pagar un servicio confirmado,<br><b>When</b> accede al método de pago,<br><b>Then</b> la plataforma permite seleccionar una opción disponible y confirma el resultado del pago.</td>
</tr>

<tr>
<td><b>US-12</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Consultar notificaciones y documentos del servicio</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero consultar notificaciones y documentos asociados al servicio para mantenerme informado sobre hitos, diagnósticos y presupuestos.</td>
<td>Reducir llamadas repetitivas, mejorar trazabilidad y reforzar transparencia documental.</td>
<td><b>Given</b> que existen eventos o documentos asociados a la orden,<br><b>When</b> el Cliente entra a notificaciones,<br><b>Then</b> la plataforma muestra avisos recientes, anteriores y documentos vinculados como presupuesto.</td>
</tr>

<tr>
<td><b>US-13</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Agendar mantenimiento preventivo</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero agendar mantenimiento preventivo seleccionando servicio, fecha, horario y vehículo para asegurar atención oportuna sin coordinación manual.</td>
<td>Fidelizar al Cliente, impulsar servicios recurrentes y mejorar la planificación del taller.</td>
<td><b>Given</b> que el Cliente selecciona un mantenimiento preventivo,<br><b>When</b> elige fecha, horario disponible y vehículo,<br><b>Then</b> la plataforma registra la cita y muestra confirmación de agendamiento.</td>
</tr>

<tr>
<td><b>US-14</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Consultar asistente virtual de ayuda</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero consultar un asistente virtual con accesos rápidos para resolver dudas sobre estado, costos, tiempo estimado o última revisión sin interrumpir al taller.</td>
<td>Disminuir carga operativa del Administrador y mejorar la atención inmediata al Cliente.</td>
<td><b>Given</b> que el Cliente entra a la sección de ayuda,<br><b>When</b> escribe una consulta o usa accesos rápidos,<br><b>Then</b> la plataforma responde con información relacionada al servicio activo.</td>
</tr>

<tr>
<td><b>US-15</b></td>
<td>EP-02 Seguimiento del servicio para Cliente</td>
<td>Gestionar perfil y cuenta del Cliente</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero gestionar mi perfil, datos de contacto, secciones personales y seguridad de cuenta para mantener actualizada mi información dentro de AutoService.</td>
<td>Mantener datos confiables para comunicación, seguimiento, pagos y notificaciones del servicio.</td>
<td><b>Given</b> que el Cliente accede a su perfil,<br><b>When</b> consulta o edita sus opciones personales,<br><b>Then</b> la plataforma muestra nombre, correo, vehículos, historial, notificaciones y métodos de pago.</td>
</tr>

<tr>
<td><b>US-16</b></td>
<td>EP-03 Gestión operativa del taller</td>
<td>Visualizar panel operativo del taller</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero visualizar un panel de control con vehículos activos, servicios en proceso, completados e ingresos para tomar decisiones rápidas sobre la operación del taller.</td>
<td>Mejorar supervisión operativa y permitir decisiones basadas en indicadores reales.</td>
<td><b>Given</b> que existen órdenes y vehículos registrados,<br><b>When</b> el Administrador ingresa al panel de control,<br><b>Then</b> la plataforma muestra vehículos activos, servicios en proceso, completados e ingresos totales.</td>
</tr>

<tr>
<td><b>US-17</b></td>
<td>EP-03 Gestión operativa del taller</td>
<td>Monitorear vehículos activos desde el panel</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero visualizar vehículos activos con porcentaje de avance para identificar rápidamente servicios pendientes, en proceso o completados.</td>
<td>Detectar prioridades operativas y evitar retrasos en la atención.</td>
<td><b>Given</b> que existen vehículos activos,<br><b>When</b> el Administrador revisa la sección de vehículos activos,<br><b>Then</b> la plataforma muestra cada vehículo con estado y porcentaje de avance.</td>
</tr>

<tr>
<td><b>US-18</b></td>
<td>EP-03 Gestión operativa del taller</td>
<td>Consultar ingresos semanales del taller</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero consultar ingresos semanales para evaluar rendimiento económico reciente y tomar decisiones de gestión.</td>
<td>Mejorar control financiero y decisiones comerciales.</td>
<td><b>Given</b> que existen servicios pagados durante la semana,<br><b>When</b> el Administrador revisa el panel financiero,<br><b>Then</b> la plataforma muestra el total acumulado semanal y una gráfica por día.</td>
</tr>

<tr>
<td><b>US-19</b></td>
<td>EP-04 Gestión de vehículos y trazabilidad técnica</td>
<td>Consultar y filtrar vehículos registrados</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero consultar, buscar y filtrar vehículos registrados por placa, propietario o estado para dar seguimiento operativo a cada servicio activo.</td>
<td>Centralizar el control de vehículos y reducir el tiempo administrativo de búsqueda.</td>
<td><b>Given</b> que existen vehículos registrados,<br><b>When</b> el Administrador accede al módulo de vehículos,<br><b>Then</b> la plataforma muestra lista con placa, propietario, estado y avance, permitiendo búsqueda y filtros.</td>
</tr>

<tr>
<td><b>US-20</b></td>
<td>EP-04 Gestión de vehículos y trazabilidad técnica</td>
<td>Registrar vehículo con datos técnicos y propietario</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero registrar un vehículo con datos técnicos y propietario para iniciar correctamente la trazabilidad del servicio.</td>
<td>Reducir errores de identificación y asegurar historial técnico desde el ingreso del vehículo.</td>
<td><b>Given</b> que un Cliente entrega su vehículo al taller,<br><b>When</b> el Administrador registra matrícula, marca, modelo, año, propietario y teléfono,<br><b>Then</b> la plataforma crea el registro y lo vincula con futuras órdenes.</td>
</tr>

<tr>
<td><b>US-21</b></td>
<td>EP-04 Gestión de vehículos y trazabilidad técnica</td>
<td>Consultar detalle técnico del vehículo</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero consultar el detalle técnico de un vehículo para revisar estado actual, problema reportado, diagnóstico y tareas de mantenimiento.</td>
<td>Mejorar trazabilidad técnica y facilitar decisiones operativas durante la reparación.</td>
<td><b>Given</b> que el vehículo tiene una orden activa,<br><b>When</b> el Administrador abre el detalle del vehículo,<br><b>Then</b> la plataforma muestra identificación, propietario, estado, avance, problema reportado, diagnóstico y tareas asociadas.</td>
</tr>

<tr>
<td><b>US-22</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Registrar problema reportado por el Cliente</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero registrar el problema reportado por el Cliente para que el taller tenga contexto inicial antes del diagnóstico técnico.</td>
<td>Evitar pérdida de información y mejorar precisión diagnóstica.</td>
<td><b>Given</b> que el Cliente informa una falla del vehículo,<br><b>When</b> el Administrador registra el problema reportado,<br><b>Then</b> la plataforma guarda la descripción en la orden para consulta del Mecánico.</td>
</tr>

<tr>
<td><b>US-23</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Registrar diagnóstico técnico del vehículo</td>
<td>Mecánico</td>
<td>Como <b>Mecánico</b>, quiero registrar el diagnóstico técnico del vehículo para sustentar las tareas necesarias y mejorar la transparencia del servicio.</td>
<td>Aumentar precisión técnica y reducir reclamos por trabajos no explicados.</td>
<td><b>Given</b> que una orden se encuentra en diagnóstico,<br><b>When</b> el Mecánico registra la evaluación técnica,<br><b>Then</b> la plataforma guarda el diagnóstico y lo relaciona con las tareas recomendadas.</td>
</tr>

<tr>
<td><b>US-24</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Gestionar tareas de mantenimiento verificables</td>
<td>Administrador / Mecánico</td>
<td>Como <b>Administrador o Mecánico</b>, quiero registrar y actualizar tareas de mantenimiento con estado y tiempo estimado para controlar el avance real del servicio.</td>
<td>Convertir la reparación en tareas verificables y mejorar el seguimiento operativo.</td>
<td><b>Given</b> que existe una orden activa,<br><b>When</b> se registra o actualiza una tarea,<br><b>Then</b> la plataforma solicita descripción, estado, responsable y tiempo estimado, recalculando el progreso de la orden.</td>
</tr>

<tr>
<td><b>US-25</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Consultar orden de trabajo con progreso de tareas</td>
<td>Administrador / Mecánico</td>
<td>Como <b>Administrador o Mecánico</b>, quiero consultar una orden de trabajo con progreso y tareas completadas para controlar el avance antes de continuar con el servicio.</td>
<td>Asegurar trazabilidad y control del trabajo realizado.</td>
<td><b>Given</b> que una orden tiene tareas registradas,<br><b>When</b> el actor consulta la orden de trabajo,<br><b>Then</b> la plataforma muestra ID, vehículo, progreso y tareas completadas respecto al total.</td>
</tr>

<tr>
<td><b>US-26</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Editar o cancelar tareas conservando trazabilidad</td>
<td>Administrador / Mecánico</td>
<td>Como <b>Administrador o Mecánico</b>, quiero editar o cancelar tareas de una orden con justificación operativa para mantener actualizado el servicio sin perder trazabilidad.</td>
<td>Adaptar el servicio a cambios técnicos sin romper el historial de la orden.</td>
<td><b>Given</b> que una tarea pertenece a una orden activa,<br><b>When</b> el actor edita o cancela la tarea,<br><b>Then</b> la plataforma registra el cambio y conserva evidencia del motivo y responsable.</td>
</tr>

<tr>
<td><b>US-27</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Detectar órdenes con riesgo de retraso</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero detectar órdenes con riesgo de retraso para intervenir antes de incumplir fechas comprometidas con el Cliente.</td>
<td>Reducir incumplimientos, mejorar satisfacción y proteger la reputación del taller.</td>
<td><b>Given</b> que existen órdenes activas con tareas pendientes,<br><b>When</b> la plataforma detecta progreso bajo o fecha estimada vencida,<br><b>Then</b> marca la orden como en riesgo o retrasada para priorizar acciones correctivas.</td>
</tr>

<tr>
<td><b>US-28</b></td>
<td>EP-05 Gestión de órdenes y tareas</td>
<td>Validar reparación antes de entrega</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero validar tareas, evidencias y checklist de calidad antes de cerrar una reparación para asegurar consistencia del servicio y evitar reclamos.</td>
<td>Asegurar calidad antes de la entrega y reducir reclamos posteriores.</td>
<td><b>Given</b> que una reparación fue marcada como completada,<br><b>When</b> el Administrador inicia control de calidad,<br><b>Then</b> la plataforma verifica tareas completadas, evidencia final, costos validados y aprobación antes de marcar listo para entrega.</td>
</tr>

<tr>
<td><b>US-29</b></td>
<td>EP-06 Coordinación del personal técnico</td>
<td>Gestionar personal técnico del taller</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero gestionar el personal técnico del taller para conocer especialidades, disponibilidad y capacidad operativa antes de asignar servicios.</td>
<td>Mejorar coordinación interna y asignación correcta de tareas.</td>
<td><b>Given</b> que el Administrador accede al módulo de personal,<br><b>When</b> la plataforma carga la lista de Mecánicos,<br><b>Then</b> muestra nombre, especialidad, disponibilidad, capacidad y acciones de gestión.</td>
</tr>

<tr>
<td><b>US-30</b></td>
<td>EP-06 Coordinación del personal técnico</td>
<td>Asignar Mecánico según disponibilidad y especialidad</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero asignar tareas a un Mecánico según disponibilidad, especialidad y carga para evitar sobrecarga y mejorar continuidad del servicio.</td>
<td>Mejorar coordinación operativa y reducir retrasos por mala asignación.</td>
<td><b>Given</b> que existe una tarea pendiente,<br><b>When</b> el Administrador selecciona un Mecánico,<br><b>Then</b> la plataforma muestra especialidad, carga y disponibilidad antes de confirmar la asignación.</td>
</tr>

<tr>
<td><b>US-31</b></td>
<td>EP-06 Coordinación del personal técnico</td>
<td>Consultar desempeño de un Mecánico</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero consultar desempeño, efectividad y carga de un Mecánico para tomar mejores decisiones de asignación.</td>
<td>Controlar productividad técnica y balancear carga de trabajo.</td>
<td><b>Given</b> que un Mecánico tiene tareas registradas,<br><b>When</b> el Administrador revisa su información,<br><b>Then</b> la plataforma muestra disponibilidad, efectividad, tareas asignadas, completadas y en proceso.</td>
</tr>

<tr>
<td><b>US-32</b></td>
<td>EP-06 Coordinación del personal técnico</td>
<td>Consultar y actualizar tareas asignadas desde workspace</td>
<td>Mecánico</td>
<td>Como <b>Mecánico</b>, quiero consultar mis tareas asignadas y actualizar su estado desde un workspace propio para mantener sincronizado el avance real del servicio con el Administrador.</td>
<td>Mejorar la coordinación operativa entre taller y Mecánicos, reduciendo retrasos por falta de actualización del avance.</td>
<td><b>Given</b> que el Mecánico tiene tareas asignadas,<br><b>When</b> accede a su workspace,<br><b>Then</b> la plataforma muestra tareas, orden asociada, vehículo, prioridad y tiempo estimado, permitiendo actualizar estados.</td>
</tr>

<tr>
<td><b>US-33</b></td>
<td>EP-07 Reportes y decisiones de negocio</td>
<td>Consultar informes estratégicos del taller</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero consultar informes estratégicos para evaluar ingresos, servicios completados, vehículos activos y rendimiento operativo.</td>
<td>Tomar decisiones de negocio basadas en información operativa y financiera.</td>
<td><b>Given</b> que la plataforma registra servicios, pagos y vehículos,<br><b>When</b> el Administrador accede a informes,<br><b>Then</b> visualiza ingresos totales, servicios completados, vehículos activos y comparaciones disponibles.</td>
</tr>

<tr>
<td><b>US-34</b></td>
<td>EP-07 Reportes y decisiones de negocio</td>
<td>Analizar tendencia semanal de servicios</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero analizar la tendencia semanal de servicios para identificar días de mayor demanda y planificar mejor la carga del taller.</td>
<td>Mejorar planificación operativa y asignación de personal según demanda.</td>
<td><b>Given</b> que existen servicios registrados durante la semana,<br><b>When</b> el Administrador revisa la tendencia semanal,<br><b>Then</b> la plataforma muestra un gráfico por día para identificar variaciones de demanda.</td>
</tr>

<tr>
<td><b>US-35</b></td>
<td>EP-07 Reportes y decisiones de negocio</td>
<td>Identificar servicios más frecuentes</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero identificar los servicios más frecuentes para optimizar precios, inventario y asignación de Mecánicos especializados.</td>
<td>Mejorar rentabilidad, planificación y especialización del taller.</td>
<td><b>Given</b> que existen servicios completados,<br><b>When</b> el Administrador consulta servicios frecuentes,<br><b>Then</b> la plataforma muestra cantidad realizada, monto asociado y oportunidades de planificación.</td>
</tr>

<tr>
<td><b>US-36</b></td>
<td>EP-08 Transparencia, comunicación y control</td>
<td>Aprobar costos adicionales antes de ejecutar reparaciones</td>
<td>Cliente</td>
<td>Como <b>Cliente</b>, quiero aprobar digitalmente costos adicionales antes de ejecutar reparaciones no contempladas para evitar conflictos posteriores.</td>
<td>Reducir reclamos, mejorar transparencia económica y validar cambios del servicio.</td>
<td><b>Given</b> que el diagnóstico detecta una reparación adicional,<br><b>When</b> el taller solicita aprobación del costo,<br><b>Then</b> la plataforma permite aprobar o rechazar antes de continuar con la reparación.</td>
</tr>

<tr>
<td><b>US-37</b></td>
<td>EP-08 Transparencia, comunicación y control</td>
<td>Alertar repuesto crítico faltante</td>
<td>Administrador / Mecánico</td>
<td>Como <b>Administrador o Mecánico</b>, quiero recibir alerta cuando falte un repuesto crítico para evitar que la reparación quede bloqueada sin seguimiento.</td>
<td>Evitar retrasos por inventario y mejorar coordinación entre taller y abastecimiento.</td>
<td><b>Given</b> que una tarea requiere un repuesto específico,<br><b>When</b> la plataforma detecta stock insuficiente,<br><b>Then</b> alerta al responsable y marca la tarea como bloqueada por repuesto faltante.</td>
</tr>

<tr>
<td><b>US-38</b></td>
<td>EP-08 Transparencia, comunicación y control</td>
<td>Centralizar comunicación del servicio</td>
<td>Administrador / Cliente</td>
<td>Como <b>Administrador o Cliente</b>, quiero centralizar comunicaciones del servicio para reducir pérdida de información y mantener confianza durante la reparación.</td>
<td>Reducir fricción comunicacional y dejar trazabilidad de mensajes importantes.</td>
<td><b>Given</b> que existe una orden activa,<br><b>When</b> se envía o recibe una comunicación relacionada al servicio,<br><b>Then</b> la plataforma registra el mensaje en el historial de la orden.</td>
</tr>

<tr>
<td><b>US-39</b></td>
<td>EP-08 Transparencia, comunicación y control</td>
<td>Auditar timeline de cambios de una orden</td>
<td>Administrador / Mecánico</td>
<td>Como <b>Administrador o Mecánico</b>, quiero auditar el timeline de cambios de una orden para identificar quién actualizó estados, tareas, evidencias o costos y en qué momento.</td>
<td>Garantizar trazabilidad operativa y responsabilidad sobre cambios del servicio.</td>
<td><b>Given</b> que una orden tuvo cambios registrados,<br><b>When</b> el actor autorizado consulta el timeline interno,<br><b>Then</b> la plataforma muestra evento, responsable, fecha y detalle del cambio.</td>
</tr>

<tr>
<td><b>US-40</b></td>
<td>EP-09 Perfil y configuración</td>
<td>Gestionar perfil y configuración administrativa</td>
<td>Administrador</td>
<td>Como <b>Administrador</b>, quiero gestionar mi perfil, configuración del taller, categorías, precios y seguridad para mantener la operación alineada con los servicios ofrecidos.</td>
<td>Centralizar administración del taller y proteger información crítica del negocio.</td>
<td><b>Given</b> que el Administrador está autenticado,<br><b>When</b> accede a su perfil administrativo,<br><b>Then</b> la plataforma muestra datos del taller, gestión de personal, configuración, categorías, precios y opciones de seguridad.</td>
</tr>

</tbody>
</table>

</div>

# 3.3. Product Backlog

A continuación, se presenta el Product Backlog del proyecto. Las historias han sido priorizadas en función de su valor estratégico para el negocio, asegurando que los requerimientos de captación (Landing Page) y cimientos arquitectónicos encabecen la lista para ser abordados en el primer Sprint. Asimismo, y de acuerdo con las buenas prácticas evaluadas, las historias vinculadas a la autenticación y seguridad han sido relegadas a un nivel posterior, garantizando la entrega temprana de funcionalidades del core business.

<div align="center">
  <table style="margin: auto; text-align: left; width: 100%;">
    <thead>
      <tr>
        <th style="text-align: left; width: 5%;"># Orden</th>
        <th style="text-align: left; width: 7%;">Story Id</th>
        <th style="width: 25%;">Título</th>
        <th style="width: 505%;">Descripción</th>
        <th style="text-align: left; width: 8%;">Story Points</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="text-align: left;">1</td>
        <td style="text-align: left;">US-01</td>
        <td>Visualizar landing page</td>
        <td>Como usuario potencial, quiero acceder a la landing page, para conocer el producto y sus beneficios.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">2</td>
        <td style="text-align: left;">US-02</td>
        <td>Visualizar beneficios del sistema</td>
        <td>Como usuario potencial, quiero ver los beneficios del sistema, para entender su valor.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">3</td>
        <td style="text-align: left;">US-03</td>
        <td>Acceder a la plataforma desde CTA</td>
        <td>Como usuario potencial, quiero hacer clic en un botón de acción, para acceder al sistema.</td>
        <td style="text-align: left;">1</td>
      </tr>
      <tr>
        <td style="text-align: left;">4</td>
        <td style="text-align: left;">US-04</td>
        <td>Visualizar landing responsive</td>
        <td>Como usuario, quiero que la landing sea responsive, para poder verla desde mi celular.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">5</td>
        <td style="text-align: left;">TS-01</td>
        <td>Definir arquitectura del sistema</td>
        <td>Como developer, quiero definir la arquitectura del sistema, para asegurar escalabilidad y mantenimiento.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">6</td>
        <td style="text-align: left;">TS-04</td>
        <td>Diseñar modelo de base de datos</td>
        <td>Como developer, quiero definir el modelo de datos, para estructurar la información del sistema.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">7</td>
        <td style="text-align: left;">TS-10</td>
        <td>Configurar entorno de desarrollo</td>
        <td>Como developer, quiero configurar el entorno, para trabajar de forma consistente.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">8</td>
        <td style="text-align: left;">TS-11</td>
        <td>Desplegar aplicación</td>
        <td>Como developer, quiero desplegar la aplicación, para que sea accesible.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">9</td>
        <td style="text-align: left;">US-08</td>
        <td>Registrar vehículo</td>
        <td>Como administrador, quiero registrar un vehículo, para gestionar su servicio.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">10</td>
        <td style="text-align: left;">US-09</td>
        <td>Crear orden de trabajo</td>
        <td>Como administrador, quiero crear una orden de trabajo, para iniciar un servicio.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">11</td>
        <td style="text-align: left;">US-10</td>
        <td>Visualizar vehículos en el taller</td>
        <td>Como administrador, quiero ver los vehículos activos, para conocer el estado del taller.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">12</td>
        <td style="text-align: left;">US-23</td>
        <td>Ingresar código de seguimiento</td>
        <td>Como cliente, quiero ingresar un código, para consultar mi vehículo.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">13</td>
        <td style="text-align: left;">US-24</td>
        <td>Visualizar estado del vehículo</td>
        <td>Como cliente, quiero ver el estado del vehículo, para conocer su progreso.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">14</td>
        <td style="text-align: left;">US-11</td>
        <td>Actualizar estado del vehículo</td>
        <td>Como administrador, quiero actualizar el estado de un vehículo, para reflejar su progreso.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">15</td>
        <td style="text-align: left;">US-12</td>
        <td>Visualizar detalle del vehículo</td>
        <td>Como administrador, quiero ver el detalle de un vehículo, para revisar información completa.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">16</td>
        <td style="text-align: left;">US-25</td>
        <td>Visualizar tareas del vehículo</td>
        <td>Como cliente, quiero ver las tareas realizadas, para entender el trabajo.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">17</td>
        <td style="text-align: left;">US-26</td>
        <td>Visualizar fechas estimadas</td>
        <td>Como cliente, quiero ver fechas estimadas, para saber cuándo estará listo.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">18</td>
        <td style="text-align: left;">US-27</td>
        <td>Visualizar costos del servicio</td>
        <td>Como cliente, quiero ver el costo estimado, para conocer el precio del servicio.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">19</td>
        <td style="text-align: left;">US-05</td>
        <td>Iniciar sesión</td>
        <td>Como usuario del sistema, quiero iniciar sesión, para acceder a mis funcionalidades.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">20</td>
        <td style="text-align: left;">US-06</td>
        <td>Acceso según rol</td>
        <td>Como usuario, quiero ver funcionalidades según mi rol, para usar el sistema correctamente.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">21</td>
        <td style="text-align: left;">US-07</td>
        <td>Cerrar sesión</td>
        <td>Como usuario, quiero cerrar sesión, para proteger mi cuenta.</td>
        <td style="text-align: left;">1</td>
      </tr>
      <tr>
        <td style="text-align: left;">22</td>
        <td style="text-align: left;">US-13</td>
        <td>Crear tareas para vehículo</td>
        <td>Como administrador, quiero crear tareas para un vehículo, para definir los trabajos a realizar.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">23</td>
        <td style="text-align: left;">US-14</td>
        <td>Asignar estado a tarea</td>
        <td>Como administrador, quiero definir el estado de una tarea, para controlar su progreso.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">24</td>
        <td style="text-align: left;">US-15</td>
        <td>Visualizar progreso por vehículo</td>
        <td>Como administrador, quiero ver el progreso de un vehículo, para conocer el avance del servicio.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">25</td>
        <td style="text-align: left;">US-16</td>
        <td>Editar tareas</td>
        <td>Como administrador, quiero editar tareas, para actualizar información del servicio.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">26</td>
        <td style="text-align: left;">US-17</td>
        <td>Eliminar tareas</td>
        <td>Como administrador, quiero eliminar tareas, para corregir errores o cambios en el servicio.</td>
        <td style="text-align: left;">1</td>
      </tr>
      <tr>
        <td style="text-align: left;">27</td>
        <td style="text-align: left;">US-18</td>
        <td>Registrar mecánico</td>
        <td>Como administrador, quiero registrar un mecánico, para gestionar el personal del taller.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">28</td>
        <td style="text-align: left;">US-19</td>
        <td>Visualizar lista de mecánicos</td>
        <td>Como administrador, quiero ver todos los mecánicos registrados, para gestionar el equipo.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">29</td>
        <td style="text-align: left;">US-20</td>
        <td>Asignar tareas a mecánico</td>
        <td>Como administrador, quiero asignar tareas a mecánicos, para distribuir el trabajo.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">30</td>
        <td style="text-align: left;">US-21</td>
        <td>Visualizar carga de trabajo</td>
        <td>Como administrador, quiero ver la carga de trabajo de cada mecánico, para equilibrar tareas.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">31</td>
        <td style="text-align: left;">US-22</td>
        <td>Ver detalle de mecánico</td>
        <td>Como administrador, quiero ver el detalle de un mecánico, para conocer su desempeño.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">32</td>
        <td style="text-align: left;">US-28</td>
        <td>Visualizar ingresos</td>
        <td>Como administrador, quiero ver los ingresos del taller, para evaluar rendimiento.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">33</td>
        <td style="text-align: left;">US-29</td>
        <td>Visualizar servicios realizados</td>
        <td>Como administrador, quiero ver los servicios realizados, para analizar actividad.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">34</td>
        <td style="text-align: left;">US-30</td>
        <td>Identificar trabajos frecuentes</td>
        <td>Como administrador, quiero identificar trabajos frecuentes, para optimizar servicios.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">35</td>
        <td style="text-align: left;">US-31</td>
        <td>Visualizar métricas del sistema</td>
        <td>Como administrador, quiero ver métricas generales, para tomar decisiones.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">36</td>
        <td style="text-align: left;">US-32</td>
        <td>Navegar interfaz intuitiva</td>
        <td>Como usuario, quiero una interfaz clara, para usar el sistema fácilmente.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">37</td>
        <td style="text-align: left;">US-33</td>
        <td>Visualizar diseño consistente</td>
        <td>Como usuario, quiero consistencia visual, para tener mejor experiencia.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">38</td>
        <td style="text-align: left;">US-34</td>
        <td>Usar sistema en móvil</td>
        <td>Como usuario, quiero usar el sistema en mi celular, para acceder desde cualquier lugar.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">39</td>
        <td style="text-align: left;">US-35</td>
        <td>Visualizar información clara</td>
        <td>Como usuario, quiero ver la información organizada, para entender rápidamente.</td>
        <td style="text-align: left;">2</td>
      </tr>
      <tr>
        <td style="text-align: left;">40</td>
        <td style="text-align: left;">TS-02</td>
        <td>Implementar API REST</td>
        <td>Como sistema, quiero exponer una API REST, para permitir comunicación con el frontend.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">41</td>
        <td style="text-align: left;">TS-03</td>
        <td>Estructurar backend modular</td>
        <td>Como developer, quiero organizar el backend en módulos, para mejorar mantenibilidad.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">42</td>
        <td style="text-align: left;">TS-05</td>
        <td>Implementar persistencia de datos</td>
        <td>Como sistema, quiero guardar la información, para mantener registros permanentes.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">43</td>
        <td style="text-align: left;">TS-06</td>
        <td>Gestionar relaciones entre entidades</td>
        <td>Como sistema, quiero manejar relaciones entre entidades, para garantizar consistencia de datos.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">44</td>
        <td style="text-align: left;">TS-07</td>
        <td>Consumir APIs externas</td>
        <td>Como sistema, quiero consumir APIs externas, para extender funcionalidades.</td>
        <td style="text-align: left;">5</td>
      </tr>
      <tr>
        <td style="text-align: left;">45</td>
        <td style="text-align: left;">TS-08</td>
        <td>Manejar respuestas de API</td>
        <td>Como sistema, quiero procesar respuestas de APIs, para utilizarlas correctamente.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">46</td>
        <td style="text-align: left;">TS-09</td>
        <td>Implementar manejo de errores</td>
        <td>Como sistema, quiero manejar errores de integración, para evitar fallos críticos.</td>
        <td style="text-align: left;">3</td>
      </tr>
      <tr>
        <td style="text-align: left;">47</td>
        <td style="text-align: left;">TS-12</td>
        <td>Configurar hosting y dominio</td>
        <td>Como developer, quiero configurar el hosting, para asegurar disponibilidad del sistema.</td>
        <td style="text-align: left;">2</td>
      </tr>
    </tbody>
  </table>
</div>

<br>

Para complementar la especificación detallada del Product Backlog y evidenciar su correcta trazabilidad en nuestra herramienta de gestión, a continuación se presenta la captura de pantalla del entorno de Jira Software. En dicha evidencia se aprecia el listado completo de las historias configuradas y listas para ser abordadas en sus respectivos ciclos de desarrollo, manteniendo el estricto orden de prioridad de negocio establecido y sus correspondientes estimaciones en Story Points.

(COMPLETAR CON NUEVA IMAGEN DE JIRA)

URL del tablero completo en Jira: (COMPLETAR CON NUEVO LINK DEL JIRA)

# 3.4. Impact Mapping

En esta sección se desarrolla el impact mapping, una técnica que permite visualizar la relación entre los objetivos del negocio, los actores involucrados, los impactos esperados y las funcionalidades del sistema. Esto facilita la alineación entre el desarrollo del producto y el valor que se busca generar. 

![alt text](</markdown/assets/images/chapter-3/Impact Map AutoService.png>)

---

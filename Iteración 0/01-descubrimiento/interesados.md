# Identificación de interesados (stakeholders)

> Documento de la Iteración 0 · [Volver al README](../README.md)

## 1. Criterio utilizado

Un interesado se incluye en este análisis si cumple al menos una de estas condiciones:

1. **Usa directamente la aplicación** (aparece como perfil en el PDF del obligatorio), o
2. **Se ve afectado por el resultado** de las interacciones que la aplicación habilita (por ejemplo, porque su propiedad o su recurso se usa), o
3. **Condiciona el alcance o la aceptación** del producto en esta etapa académica.

No se agregan interesados solo para aumentar la cantidad. Cada uno lleva su justificación.

**Nota de evidencia:** este análisis se redactó antes de las entrevistas. Todo lo que figura como necesidad, problema o frustración surge de la lectura del PDF, del análisis de competidores ([analisis-competidores.md](../02-competidores/analisis-competidores.md)) y del razonamiento del equipo. Por eso lo tratamos como **hipótesis a validar**, salvo cuando se indica que viene directamente del PDF. Las entrevistas ([guion-entrevistas.md](guion-entrevistas.md)) y los tests de prototipos de las Iteraciones 1 y 2 son los que las confirman o descartan.

## 2. Interesados primarios (usuarios directos, definidos en el PDF)

### 2.1 Conductor

**Descripción (PDF):** persona con un vehículo eléctrico que necesita cargarlo. El MVP está dirigido *principalmente* a conductores que **no tienen punto de carga propio**, porque viven en un apartamento sin cochera o porque su cochera no tiene instalación.

| Dimensión | Análisis |
|---|---|
| **Necesidades** | Encontrar un lugar donde cargar cerca de la zona donde va a estar, en el día y franja horaria en que puede dejar el vehículo. Saber de antemano que el conector es compatible. Saber cuánto va a tardar y cuánto le va a costar. Tener la franja asegurada (reserva). |
| **Problemas** | Sin cochera propia depende de la red pública o de arreglos informales. No tiene certeza de disponibilidad. Puede no conocer los tipos de conector ni cómo influye la potencia en el tiempo de carga (el PDF lo menciona explícitamente en los RNF). |
| **Frustraciones** *(hipótesis a validar)* | Llegar a un punto y encontrarlo ocupado. Llegar y que el conector no sirva. Sorpresas con el costo final. Enterarse tarde de que el anfitrión canceló. No saber cómo acceder al lugar (portón, cochera de edificio). |
| **Objetivos** | Cargar el vehículo lo suficiente para sus traslados, con el menor esfuerzo de planificación y a un costo previsible. |
| **Información que necesita** | Ubicación/zona del punto, tipo de conector, potencia (kW), tarifa por kWh, duración máxima por sesión, instrucciones de acceso, franjas disponibles, tiempo y costo estimados para *su* vehículo, evaluaciones de otros conductores. |
| **Funcionalidades que utiliza (PDF)** | Registro, login, recuperar contraseña, logout, editar usuario, registrar vehículo, buscar puntos disponibles por zona/día/franja/nivel de carga, ver solo puntos compatibles y disponibles, ver tiempo y costo estimados, reservar franja, cancelar reserva (implícito en notificaciones), evaluar punto con diferentes criterios, recibir notificaciones (cambio/cancelación del anfitrión y recordatorio 30 min antes). |
| **Valor que obtiene** | Acceso a una red de carga adicional a la pública, con franja reservada y costo conocido de antemano. Para quien no tiene cochera, esto puede ser la condición para que tener un vehículo eléctrico sea práctico. |

### 2.2 Anfitrión

**Descripción (PDF):** quien ofrece el servicio. Puede ser el **propietario de una vivienda con cargador instalado** o el **administrador de un edificio con cocheras**.

| Dimensión | Análisis |
|---|---|
| **Necesidades** | Publicar su punto de carga de forma simple. Definir sus propias condiciones (tarifa por kWh, duración máxima, instrucciones de acceso). Controlar en qué días y franjas está disponible. Saber quién va a usar el punto. |
| **Problemas** | El cargador está ocioso gran parte del tiempo (la inversión ya está hecha). No tiene un canal para ofrecerlo a desconocidos de forma ordenada. Si cambia su disponibilidad, necesita avisar a quien ya reservó. |
| **Objetivos** | Obtener un ingreso extra (o al menos recuperar el costo de la energía) sin que eso le complique su rutina. |
| **Riesgos** *(hipótesis a validar)* | Conductores que no respetan la franja o la duración máxima. Mal uso del equipo o del espacio. Seguridad al permitir el ingreso a su propiedad o a la cochera del edificio. Reservas canceladas a último momento. Fijar una tarifa que no cubra su costo real de energía. |
| **Información que necesita** | Reservas agendadas en su punto, datos básicos y reputación del conductor, historial de sesiones realizadas, ingreso acumulado, avisos de cancelación. |
| **Funcionalidades (PDF)** | Registro, login, recuperar contraseña, logout, editar usuario, registrar punto de carga (nombre, dirección, conector, potencia), publicar condiciones del servicio, gestionar agenda de franjas por día, cancelar/modificar franjas agendadas (con notificación al conductor), recibir aviso cuando un conductor cancela, evaluar conductores, ver historial de sesiones e ingreso acumulado. |
| **Valor económico** | Ingreso por kWh vendido según la tarifa que él mismo publica. Ejemplo tomado del PDF: una carga de 48 kWh a $8/kWh equivale a $384 por sesión. Cuánto de esto es margen sobre su costo de energía es una **hipótesis a validar** (depende de su tarifa residencial). |

**Sub-segmentos del anfitrión.** El PDF agrupa en un mismo perfil a dos tipos de anfitrión con contextos distintos. Los distinguimos porque probablemente tengan necesidades diferentes (**hipótesis a validar**):

| Sub-segmento | Diferencia relevante |
|---|---|
| Propietario de vivienda | Normalmente tiene un solo punto de carga. Le importan su privacidad y seguridad. Decide solo. |
| Administrador de edificio con cocheras | Puede gestionar más de un punto. Responde ante copropietarios. Las instrucciones de acceso (portería, portón, horarios del edificio) son más importantes. |

En el MVP ambos usan el mismo perfil y las mismas funcionalidades, como indica el PDF.

**Usuarios con ambos perfiles.** Una misma persona puede ser anfitrión y conductor (por ejemplo, alguien que carga su auto en su casa y viaja seguido a otra ciudad). Se decidió que una cuenta puede tener ambos perfiles y elegir con cuál ingresa (decisión D2 del [README](../README.md#decisiones-tomadas-y-pendientes)).

### 2.3 Administrador

**Descripción (PDF):** administradores de la aplicación. Su alta la hace **exclusivamente otro administrador** (no puede autorregistrarse).

| Dimensión | Análisis |
|---|---|
| **Necesidades** | Tener visibilidad sobre usuarios, evaluaciones y reportes. Contar con herramientas para actuar ante incumplimientos. |
| **Responsabilidades (PDF)** | Dar de baja usuarios por mala reputación o incumplimientos. Arbitrar discrepancias en evaluaciones. Gestionar reportes de la comunidad. Dar de alta a otros administradores. |
| **Funcionalidades** | Login, logout, alta de administradores, baja de usuarios, arbitraje de evaluaciones, gestión de reportes. |
| **Problemas que debe resolver** | Conflictos entre anfitrión y conductor (por ejemplo, evaluaciones que una parte considera injustas). Usuarios que incumplen reiteradamente. Reportes sobre puntos que no existen o datos falsos. |
| **Valor para el sistema** | La plataforma depende de que dos desconocidos confíen entre sí. El administrador protege esa confianza. Sin moderación, las evaluaciones pierden valor y los usuarios abandonan la plataforma (**hipótesis a validar**). |

## 3. Interesados secundarios (justificados)

| Interesado | Justificación para incluirlo | Cómo lo consideramos |
|---|---|---|
| **Comunidad de usuarios** | El PDF menciona explícitamente "reportes de la comunidad". Conductores y anfitriones, en conjunto, generan evaluaciones y reportes que benefician a otros usuarios. | No es un perfil distinto: es el conjunto de conductores y anfitriones actuando como fuente de información (evaluaciones, reportes). Se refleja en las historias de evaluación y reporte. |
| **Copropietarios del edificio** | Cuando el anfitrión es un administrador de edificio, las personas que viven allí se ven afectadas por el ingreso de conductores externos a las cocheras. | No usan la aplicación. Se consideran a través de las *instrucciones de acceso* y la *duración máxima por sesión* que publica el anfitrión. Queda como riesgo a indagar. |
| **Conductores potenciales (futuros adoptantes / indecisos)** | El PDF pide que la aplicación sea fácil de usar para personas que *recién adoptan* la movilidad eléctrica y no conocen conectores ni potencias. Incluye a quien **evalúa comprar un vehículo eléctrico pero no puede cargar en su casa**: necesita certeza de que va a poder cargar antes de comprar, y es una fuente de crecimiento futuro de la demanda. | Se reflejan en el RNF de usabilidad, en la historia de ayuda sobre conectores (US-13) y en la persona Martín. |
| **Equipo docente** | Define el alcance, la rúbrica y valida la herramienta de prototipado. | Condiciona el proceso, no el producto. Las decisiones pendientes se listan en el [README](../README.md#15-conclusiones-de-la-iteración-0). |

**Interesados que consideramos y descartamos para el MVP:** la empresa distribuidora de energía (UTE) y los operadores de redes públicas de carga. Son relevantes para el contexto del mercado (ver [competidores](../02-competidores/analisis-competidores.md)), pero el PDF no define ninguna interacción del sistema con ellos. Por eso no los tratamos como interesados del producto en esta etapa.

## 4. Tabla resumen de interesados

| Stakeholder | Descripción | Necesidades | Problemas | Objetivos | Funcionalidades | Valor |
|---|---|---|---|---|---|---|
| **Conductor** | Tiene vehículo eléctrico, sin punto de carga propio (foco del MVP). | Encontrar un punto compatible y disponible en su zona y franja; saber tiempo y costo. | Incertidumbre de disponibilidad y compatibilidad; desconocimiento técnico. | Cargar con poco esfuerzo y costo previsible. | Registro/login, vehículo, búsqueda, estimación, reserva, cancelación, evaluación, notificaciones. | Carga asegurada y predecible fuera de su casa. |
| **Anfitrión** | Propietario de vivienda con cargador o administrador de edificio con cocheras. | Publicar el punto, fijar condiciones y controlar la agenda. | Cargador ocioso; sin canal para ofrecerlo; riesgo de mal uso. | Ingreso extra sin alterar su rutina. | Registro/login, punto de carga, condiciones, agenda, evaluación de conductores, historial e ingresos, notificaciones. | Ingreso por kWh con condiciones propias. |
| **Administrador** | Administra la plataforma; lo da de alta otro administrador. | Visibilidad y herramientas de moderación. | Conflictos, incumplimientos, reportes. | Mantener la confianza en la plataforma. | Alta de administradores, baja de usuarios, arbitraje, reportes. | Sostiene la confianza que hace funcionar el intercambio. |
| **Comunidad** | Conductores y anfitriones como conjunto. | Información confiable sobre puntos y usuarios. | Datos desactualizados o falsos. | Que la información de la plataforma sea útil. | Evaluaciones, reportes. | Reputación como mecanismo de confianza. |
| **Copropietarios de edificio** | Viven donde está el punto del anfitrión-administrador. | Seguridad y orden en las cocheras. | Ingreso de terceros. | Que el uso no los perjudique. | Indirecto: instrucciones de acceso, duración máxima. | Condición para que los edificios participen. |
| **Conductores potenciales** | Personas que recién adoptan la movilidad eléctrica. | Entender conectores y potencias sin conocimiento previo. | Barrera técnica de entrada. | Decidir con confianza. | Ayuda de conectores; compatibilidad automática. | Amplía la base de usuarios. |

## 5. Funcionalidades por interesado

Esta lista responde al ítem de la rúbrica *"lista de funcionalidades por interesado"*. La columna **Origen** indica si la funcionalidad está en el PDF o si es una propuesta del equipo.

| # | Funcionalidad | Conductor | Anfitrión | Administrador | Origen | Historias |
|---|---|:-:|:-:|:-:|---|---|
| F01 | Registrar nuevo usuario (email, usuario, contraseña, uno o ambos perfiles) | ✔ | ✔ | — | PDF | US-01 |
| F02 | Login con usuario y contraseña, eligiendo el perfil | ✔ | ✔ | ✔ | PDF | US-02 |
| F03 | Recuperar contraseña | ✔ | ✔ | ✔ | PDF | US-03 |
| F04 | Logout | ✔ | ✔ | ✔ | PDF | US-04 |
| F05 | Editar usuario (todo menos el email) | ✔ | ✔ | — | PDF | US-05 |
| F06 | Registrar punto de carga (nombre, dirección, conector, potencia) | — | ✔ | — | PDF | US-06 |
| F07 | Publicar condiciones del servicio (tarifa/kWh, duración máxima, instrucciones de acceso) | — | ✔ | — | PDF | US-07 |
| F08 | Gestionar agenda de franjas por día | — | ✔ | — | PDF | US-08 |
| F09 | Cancelar o modificar una franja ya agendada | — | ✔ | — | PDF (en Notificaciones) | US-09 |
| F10 | Ver reservas recibidas en el punto | — | ✔ | — | Propuesta (necesaria para F09) | US-10 |
| F11 | Ver historial de sesiones e ingreso acumulado | — | ✔ | — | PDF | US-11 |
| F12 | Registrar vehículo (marca, modelo, batería, conector) | ✔ | — | — | PDF | US-12 |
| F13 | Ayuda para identificar el tipo de conector | ✔ | ✔ | — | Propuesta (deriva del RNF de usabilidad) | US-13 |
| F14 | Buscar por zona, día, franja y nivel de carga actual | ✔ | — | — | PDF | US-14 |
| F15 | Mostrar solo puntos compatibles y disponibles | ✔ | — | — | PDF | US-15 |
| F16 | Ver tiempo y costo estimados por punto | ✔ | — | — | PDF | US-16 |
| F17 | Ver detalle y condiciones de un punto | ✔ | — | — | Propuesta (necesaria para decidir) | US-17 |
| F18 | Reservar una franja | ✔ | — | — | PDF | US-18 |
| F19 | Cancelar una reserva | ✔ | — | — | PDF (en Notificaciones) | US-19 |
| F20 | Ver mis reservas | ✔ | — | — | Propuesta (necesaria para F19) | US-20 |
| F21 | Evaluar el punto de carga con diferentes criterios | ✔ | — | — | PDF | US-21 |
| F22 | Evaluar al conductor | — | ✔ | — | PDF | US-22 |
| F23 | Reportar un problema, usuario o punto | ✔ | ✔ | — | Propuesta (origen de los "reportes de la comunidad" del PDF) | US-23 |
| F24 | Notificación al conductor por cancelación/modificación del anfitrión | ✔ | — | — | PDF | US-24 |
| F25 | Notificación al anfitrión por cancelación del conductor | — | ✔ | — | PDF | US-25 |
| F26 | Recordatorio 30 minutos antes de la reserva | ✔ | — | — | PDF | US-26 |
| F27 | Alta de administrador (solo por otro administrador) | — | — | ✔ | PDF | US-27 |
| F28 | Dar de baja usuarios por mala reputación o incumplimientos | — | — | ✔ | PDF | US-28 |
| F29 | Arbitrar discrepancias en evaluaciones | — | — | ✔ | PDF | US-29 |
| F30 | Gestionar reportes de la comunidad | — | — | ✔ | PDF | US-30 |

Las funcionalidades marcadas como **Propuesta** no contradicen el PDF. Las agregamos porque sin ellas algunas funcionalidades obligatorias no se pueden completar. Por ejemplo, para cancelar una reserva, el conductor tiene que poder verla primero.

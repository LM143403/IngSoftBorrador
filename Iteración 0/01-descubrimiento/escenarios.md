# Escenarios principales

> Documento de la Iteración 0 · [Volver al README](../README.md)

Los escenarios describen situaciones concretas de uso de los perfiles definidos en el PDF. Usan a las [personas hipotéticas](personas.md) como protagonistas. Los flujos son **propuestas iniciales**: el diseño definitivo de pantallas se va a idear y validar en las Iteraciones 1 y 2. Los identificadores de historias (US-xx) remiten a [historias-usuario.md](../04-product-backlog/historias-usuario.md).

---

## E1 — Un conductor necesita cargar su vehículo

| Campo | Descripción |
|---|---|
| **Actor** | Conductor (Lucía) |
| **Situación** | Tiene la batería al 25 % y no puede cargar en su casa. Todavía no usó la aplicación. |
| **Objetivo** | Quedar en condiciones de buscar carga: tener cuenta y vehículo registrado. |
| **Flujo principal** | 1. Descarga la app y elige "Registrarme". 2. Ingresa email, nombre de usuario y contraseña y elige el perfil *Conductor*. 3. Inicia sesión eligiendo el perfil *Conductor*. 4. Registra su vehículo: marca, modelo, capacidad de batería (kWh) y tipo de conector. 5. La app queda lista para buscar. |
| **Flujos alternativos** | 2a. El email o el usuario ya existen: se informa y no se crea la cuenta. 3a. Olvidó la contraseña: usa "Recuperar contraseña". 4a. No sabe qué conector tiene: consulta la ayuda con imágenes. |
| **Problema que aborda** | Barrera de entrada y desconocimiento técnico. |
| **Valor de negocio** | Sin cuenta ni vehículo no hay búsqueda compatible. Es el primer paso para convertir a un conductor en usuario activo. |
| **Funcionalidades / historias** | US-01, US-02, US-03, US-12, US-13 |

> **Variante nocturna (a considerar en los prototipos):** para quien no tiene cochera, un caso típico es llegar al 20 % de batería y reservar de noche cerca de su casa, por ejemplo **de 22:00 a 06:00**. Esa franja cruza la medianoche; ver la decisión pendiente D10 en el [README](../README.md#decisiones-tomadas-y-pendientes).

## E2 — El conductor busca un punto compatible y disponible

| Campo | Descripción |
|---|---|
| **Actor** | Conductor (Lucía) |
| **Situación** | Ya tiene cuenta y vehículo registrado. Necesita cargar el martes de noche cerca de su casa. |
| **Objetivo** | Ver los puntos que realmente puede usar. |
| **Flujo principal** | 1. Abre "Buscar carga". 2. Indica zona (Pocitos), día (martes), franja (19:00–23:00) y nivel de carga actual (25 %). 3. La app muestra **solo** los puntos con conector compatible con su vehículo **y** con disponibilidad en esa franja. |
| **Flujos alternativos** | 3a. No hay resultados: la app lo informa claramente y sugiere cambiar zona o franja. 1a. Tiene más de un vehículo: elige con cuál busca (**hipótesis a validar**). |
| **Problema que aborda** | Incertidumbre de compatibilidad y disponibilidad. |
| **Valor de negocio** | Es el núcleo de la propuesta de valor para el usuario principal del MVP. |
| **Funcionalidades / historias** | US-14, US-15 |

## E3 — El conductor compara tiempo y costo

| Campo | Descripción |
|---|---|
| **Actor** | Conductor (Lucía, Martín) |
| **Situación** | Tiene una lista de puntos compatibles y disponibles. |
| **Objetivo** | Elegir el punto más conveniente según tiempo, costo y condiciones. |
| **Flujo principal** | 1. Ve cada punto con tiempo y costo estimados. Ejemplo: batería de 40 kWh al 25 % → 30 kWh; en un punto de 7 kW ≈ 4 h 17 min; a $8/kWh ≈ $240. 2. Ordena por costo o por tiempo. 3. Abre el detalle de un punto: potencia, conector, tarifa, duración máxima, instrucciones de acceso y evaluaciones. |
| **Flujos alternativos** | 1a. La duración máxima del punto es menor que el tiempo estimado: se advierte que la carga será parcial y se muestra la energía y el costo para esa duración (supuesto S5). |
| **Problema que aborda** | Sorpresas de tiempo y costo. |
| **Valor de negocio** | Diferencial frente a los competidores relevados (ver [análisis](../02-competidores/analisis-competidores.md#6-insights)). |
| **Funcionalidades / historias** | US-16, US-17 |

## E4 — El conductor realiza una reserva

| Campo | Descripción |
|---|---|
| **Actor** | Conductor (Lucía) |
| **Situación** | Eligió un punto. |
| **Objetivo** | Asegurar la franja. |
| **Flujo principal** | 1. Desde el detalle, elige la franja disponible. 2. Ve un resumen: punto, dirección, día, franja, tiempo y costo estimados. 3. Confirma. 4. La franja pasa a estar ocupada para otros conductores y la reserva aparece en "Mis reservas". 5. 30 minutos antes del inicio recibe un recordatorio. |
| **Flujos alternativos** | 3a. Otra persona reservó la franja mientras decidía: la app informa que ya no está disponible. 5a. Decide cancelar: cancela desde "Mis reservas" y el anfitrión es notificado. |
| **Problema que aborda** | Falta de certeza de disponibilidad. |
| **Valor de negocio** | Es la transacción central que genera valor para ambos lados. |
| **Funcionalidades / historias** | US-18, US-20, US-19, US-25, US-26 |

## E5 — El anfitrión publica un punto de carga

| Campo | Descripción |
|---|---|
| **Actor** | Anfitrión (Andrés; Carolina para el caso de edificio) |
| **Situación** | Tiene un cargador ocioso y quiere ofrecerlo. |
| **Objetivo** | Que su punto aparezca en las búsquedas de conductores compatibles. |
| **Flujo principal** | 1. Se registra con el perfil *Anfitrión* e inicia sesión con ese perfil. 2. Registra el punto: nombre, dirección, tipo de conector (Tipo 2, CCS2, CHAdeMO, GB/T o toma domiciliaria) y potencia en kW. 3. Publica las condiciones: tarifa por kWh, duración máxima por sesión e instrucciones de acceso. 4. Carga su agenda (E6). |
| **Flujos alternativos** | 2a. Carolina registra un segundo punto en la misma dirección. 3a. Deja la tarifa vacía: la app no permite publicar. |
| **Problema que aborda** | Falta de un canal para ofrecer el cargador con condiciones propias. |
| **Valor de negocio** | Sin oferta de puntos no hay resultados de búsqueda. Es el lado "oferta" del marketplace. |
| **Funcionalidades / historias** | US-01, US-02, US-06, US-07, US-13 |

## E6 — El anfitrión administra su disponibilidad

| Campo | Descripción |
|---|---|
| **Actor** | Anfitrión (Andrés) |
| **Situación** | Su punto está publicado. |
| **Objetivo** | Definir y ajustar cuándo está disponible. |
| **Flujo principal** | 1. Entra a la agenda del punto. 2. Para cada día agrega franjas (ej.: lunes 9:00–13:00 y 14:00–17:00). 3. Ve qué franjas están libres y cuáles reservadas. 4. Elimina franjas libres que ya no quiere ofrecer. |
| **Flujos alternativos** | 2a. Intenta cargar una franja que se superpone con otra: la app no lo permite. 4a. La franja que quiere quitar ya está reservada: pasa al escenario E7. |
| **Problema que aborda** | Control del anfitrión sobre su tiempo y su propiedad. |
| **Valor de negocio** | Una agenda confiable es condición para que las búsquedas del conductor muestren disponibilidad real. |
| **Funcionalidades / historias** | US-08, US-10 |

## E7 — Cancelación o modificación con notificaciones

| Campo | Descripción |
|---|---|
| **Actores** | Anfitrión (Andrés) y Conductor (Lucía) |
| **Situación** | Hay una reserva confirmada y una de las partes necesita cambiarla. |
| **Objetivo** | Que la otra parte se entere a tiempo y la agenda quede consistente. |
| **Flujo principal A (cancela el anfitrión)** | 1. Andrés abre la reserva desde "Reservas recibidas". 2. Elige cancelar o modificar el horario e indica un motivo. 3. Lucía recibe una notificación con el cambio. 4. Si fue una cancelación, la reserva de Lucía queda como "cancelada por el anfitrión". |
| **Flujo principal B (cancela el conductor)** | 1. Lucía cancela desde "Mis reservas". 2. Andrés recibe una notificación. 3. La franja vuelve a quedar disponible en la agenda. |
| **Flujo C (recordatorio)** | 30 minutos antes del inicio de una reserva vigente, el conductor recibe un recordatorio. |
| **Problema que aborda** | Que alguien vaya hasta el punto para nada o que el anfitrión espere a alguien que no viene. |
| **Valor de negocio** | Reduce viajes inútiles y franjas perdidas; sostiene la confianza. Los tres casos de notificación son obligatorios en el PDF. |
| **Funcionalidades / historias** | US-09, US-19, US-24, US-25, US-26 |

## E8 — El administrador gestiona una incidencia

| Campo | Descripción |
|---|---|
| **Actores** | Administrador (Sofía); conductor y anfitrión involucrados |
| **Situación** | Lucía evaluó con 1 estrella el punto de Andrés porque el conector no coincidía. Andrés considera la evaluación injusta y además reportó a Lucía por llegar tarde. |
| **Objetivo** | Resolver la discrepancia y actuar si hay un incumplimiento. |
| **Flujo principal** | 1. Sofía inicia sesión como administradora. 2. En "Reportes" ve el reporte pendiente con los datos de la reserva. 3. En "Evaluaciones en disputa" revisa ambas evaluaciones. 4. Decide mantener o anular la evaluación y registra el motivo. 5. Si detecta incumplimientos reiterados, da de baja al usuario indicando el motivo. 6. El reporte queda como resuelto. |
| **Flujos alternativos** | 5a. Es un primer incidente: solo registra la decisión sin dar de baja. |
| **Problema que aborda** | Pérdida de confianza por evaluaciones injustas o usuarios que incumplen. |
| **Valor de negocio** | La reputación solo sirve si está moderada. |
| **Funcionalidades / historias** | US-21, US-22, US-23, US-28, US-29, US-30 (y US-27 para dar de alta a otros administradores) |

---

## Escenario complementario E9 — El anfitrión revisa su actividad

| Campo | Descripción |
|---|---|
| **Actor** | Anfitriona (Carolina) |
| **Situación** | Fin de mes. |
| **Objetivo** | Saber cuántas sesiones hubo y cuánto ingresó. |
| **Flujo principal** | 1. Abre "Historial". 2. Ve la lista de sesiones realizadas (fecha, punto, conductor, energía, importe). 3. Ve el ingreso acumulado. 4. Evalúa a un conductor de una sesión reciente. |
| **Valor de negocio** | Le hace visible al anfitrión el beneficio económico, que es su motivación principal (hipótesis H5). |
| **Funcionalidades / historias** | US-11, US-22 |

## Matriz escenario × actor

| Escenario | Conductor | Anfitrión | Administrador |
|---|:-:|:-:|:-:|
| E1 Necesita cargar (alta y vehículo) | ● | | |
| E2 Busca punto compatible | ● | | |
| E3 Compara tiempo y costo | ● | | |
| E4 Reserva | ● | ○ (su agenda se actualiza) | |
| E5 Publica punto | | ● | |
| E6 Administra disponibilidad | | ● | |
| E7 Cancelación y notificaciones | ● | ● | |
| E8 Gestión de incidencia | ○ | ○ | ● |
| E9 Revisa actividad | | ● | |

● actor principal · ○ participante

# Historias de usuario y criterios de aceptación

> Documento de la Iteración 0 · [Volver al README](../README.md) · [Resumen del Product Backlog](product-backlog.md)

## Convenciones

- **Formato:** *Como [actor], quiero [objetivo], para [beneficio].*
- **Criterios de aceptación** en formato *Dado / Cuando / Entonces* (estilo Gherkin). Describen comportamientos **observables en el frontend**.
- **Estimación:** puntos de historia (serie de Fibonacci 1-2-3-5-8), relativos entre sí. Es una **estimación inicial** del equipo que se va a recalibrar en la Sprint Planning de la Iteración 1, cuando tengamos velocidad real.
- **MoSCoW / release:** ver el orden y la prioridad en el [Product Backlog](product-backlog.md#3-product-backlog-ordenado).
- **Origen:** *Letra* = requisito explícito de la letra del obligatorio; *Propuesta* = agregada por el equipo porque es necesaria para completar un requisito de la letra (ver [funcionalidades por interesado](../README.md#12-funcionalidades-por-interesado): cada US-xx corresponde a la funcionalidad F-xx con el mismo número).
- Como el alcance es un **frontend con prototipos**, "el sistema guarda" significa que el dato queda disponible en la aplicación (por ejemplo, con datos simulados). La persistencia real no forma parte del alcance de la letra.

## Índice de épicas

| Épica | Nombre | Historias |
|---|---|---|
| [EP01](#ep01--acceder-a-mi-cuenta) | Acceder a mi cuenta | US-01 a US-05 |
| [EP02](#ep02--gestionar-mi-punto-de-carga) | Gestionar mi punto de carga | US-06 a US-11 |
| [EP03](#ep03--registrar-mi-vehículo) | Registrar mi vehículo | US-12, US-13 |
| [EP04](#ep04--buscar-y-comparar-puntos) | Buscar y comparar puntos | US-14 a US-17 |
| [EP05](#ep05--reservar-una-franja) | Reservar una franja | US-18 a US-20 |
| [EP06](#ep06--recibir-avisos) | Recibir avisos | US-24 a US-26 |
| [EP07](#ep07--evaluar-y-reportar) | Evaluar y reportar | US-21 a US-23 |
| [EP08](#ep08--administrar-la-plataforma) | Administrar la plataforma | US-27 a US-30 |

---

## EP01 — Acceder a mi cuenta

**Objetivo de la épica:** que conductores, anfitriones y administradores accedan de forma segura y simple, cada uno con su perfil. La letra pide un acceso *"seguro y simplificado para fomentar la retención de usuarios"*.

### US-01 — Registrar nuevo usuario con perfil

> **Como** persona interesada en usar la aplicación,
> **quiero** registrarme con mi email, nombre de usuario y contraseña, eligiendo si soy anfitrión, conductor o ambos,
> **para** acceder a las funcionalidades de mi perfil.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión | Letra | Must | 3 | — | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** estoy en la pantalla de registro, **cuando** completo email, nombre de usuario, contraseña, elijo al menos un perfil (*Anfitrión*, *Conductor* o ambos) y confirmo, **entonces** se crea mi cuenta con los perfiles elegidos y se me indica que ya puedo iniciar sesión *(decisión DP2)*.
2. **Dado que** ingreso un email que ya está registrado, **cuando** confirmo, **entonces** se muestra "Este email ya está registrado" y no se crea la cuenta.
3. **Dado que** ingreso un nombre de usuario ya existente, **cuando** confirmo, **entonces** se muestra un mensaje que lo indica y no se crea la cuenta.
4. **Dado que** dejo algún campo obligatorio vacío o el email no tiene formato válido, **cuando** intento confirmar, **entonces** se marca el campo con error y no se crea la cuenta.
5. **Dado que** ingreso una contraseña de menos de 8 caracteres, **cuando** intento confirmar, **entonces** se informa el requisito mínimo *(regla propuesta por el equipo, a validar)*.
6. **Dado que** estoy en el registro, **cuando** veo las opciones de perfil, **entonces** solo aparecen *Anfitrión* y *Conductor*; *Administrador* no es seleccionable.
7. **Dado que** no marqué ningún perfil, **cuando** intento confirmar, **entonces** se me pide elegir al menos uno.

### US-02 — Iniciar sesión eligiendo el perfil

> **Como** usuario registrado,
> **quiero** iniciar sesión con mi nombre de usuario y contraseña eligiendo con qué perfil ingreso,
> **para** usar la aplicación con las funcionalidades de ese perfil.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión, Administrador | Letra | Must | 3 | US-01 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** tengo una cuenta con perfil *Conductor*, **cuando** ingreso usuario y contraseña correctos y elijo *Conductor*, **entonces** accedo a la pantalla principal del conductor.
2. **Dado que** tengo una cuenta con perfil *Anfitrión*, **cuando** ingreso credenciales correctas y elijo *Anfitrión*, **entonces** accedo a la pantalla principal del anfitrión.
3. **Dado que** soy administrador, **cuando** ingreso credenciales correctas y elijo *Administrador*, **entonces** accedo al panel de administración.
4. **Dado que** elijo un perfil que no corresponde a mi cuenta, **cuando** confirmo, **entonces** se muestra un mensaje indicando que la cuenta no tiene ese perfil.
5. **Dado que** ingreso un usuario o contraseña incorrectos, **cuando** confirmo, **entonces** se muestra "Usuario o contraseña incorrectos", sin indicar cuál de los dos falló.
6. **Dado que** estoy en el login, **cuando** miro la pantalla, **entonces** veo el acceso a "Recuperar contraseña" y a "Registrarme".
7. **Dado que** mi cuenta fue dada de baja por un administrador, **cuando** intento iniciar sesión, **entonces** se me informa que la cuenta está inhabilitada.
8. **Dado que** mi cuenta tiene ambos perfiles, **cuando** ingreso con uno de ellos, **entonces** veo solo las funcionalidades de ese perfil y puedo cambiar al otro desde el menú sin volver a ingresar la contraseña *(decisión DP2; el cambio sin contraseña es propuesta del equipo)*.

### US-03 — Recuperar contraseña

> **Como** usuario que olvidó su contraseña,
> **quiero** recuperarla a partir de mi email,
> **para** volver a acceder sin crear una cuenta nueva.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión, Administrador | Letra | Should | 2 | US-01 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** estoy en "Recuperar contraseña", **cuando** ingreso un email y confirmo, **entonces** se muestra "Si el email está registrado, te enviamos instrucciones", exista o no la cuenta (para no revelar qué emails están registrados).
2. **Dado que** abrí el enlace de recuperación recibido, **cuando** ingreso una nueva contraseña válida dos veces, **entonces** se actualiza y vuelvo al login con un mensaje de confirmación.
3. **Dado que** las dos contraseñas nuevas no coinciden, **cuando** confirmo, **entonces** se informa el error y la contraseña no cambia.

### US-04 — Cerrar sesión

> **Como** usuario autenticado,
> **quiero** cerrar sesión,
> **para** que nadie más use mi cuenta desde mi dispositivo.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión, Administrador | Letra | Should | 1 | US-02 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo la sesión iniciada, **cuando** elijo "Cerrar sesión" y confirmo, **entonces** vuelvo a la pantalla de login.
2. **Dado que** cerré sesión, **cuando** uso "atrás" en el dispositivo, **entonces** no puedo volver a pantallas que requieren autenticación.

### US-05 — Editar mis datos de usuario

> **Como** usuario registrado,
> **quiero** modificar los datos que usé para registrarme, excepto el email,
> **para** mantener mi cuenta actualizada.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión | Letra | Should | 2 | US-01, US-02 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** estoy en "Mi cuenta", **cuando** modifico mi nombre de usuario o mi contraseña y guardo, **entonces** los cambios quedan aplicados y se muestra una confirmación.
2. **Dado que** estoy en "Mi cuenta", **cuando** veo mi email, **entonces** aparece como dato de solo lectura y no puede editarse.
3. **Dado que** cambio el nombre de usuario por uno que ya existe, **cuando** guardo, **entonces** se informa el error y no se aplica el cambio.
4. **Dado que** quiero cambiar la contraseña, **cuando** la modifico, **entonces** se me pide la contraseña actual.
5. **Dado que** mi cuenta tiene un solo perfil, **cuando** elijo "Agregar perfil" (*Anfitrión* o *Conductor*), **entonces** la cuenta queda con ambos perfiles y puedo ingresar con cualquiera de ellos *(decisión DP2)*.

---

## EP02 — Gestionar mi punto de carga

**Objetivo de la épica:** que el anfitrión publique su punto con sus condiciones, controle la agenda y vea el resultado económico. Constituye el lado "oferta" del producto.

### US-06 — Registrar punto de carga

> **Como** anfitrión,
> **quiero** registrar mi punto de carga con nombre, dirección, tipo de conector y potencia disponible,
> **para** que los conductores con vehículos compatibles puedan encontrarlo.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Must | 3 | US-02 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** inicié sesión como anfitrión, **cuando** completo nombre, dirección, tipo de conector y potencia (kW) y guardo, **entonces** el punto aparece en "Mis puntos".
2. **Dado que** elijo el tipo de conector, **cuando** despliego las opciones, **entonces** solo puedo elegir entre *Tipo 2, CCS2, CHAdeMO, GB/T* o *Toma domiciliaria*.
3. **Dado que** ingreso una potencia no numérica, igual a 0 o negativa, **cuando** guardo, **entonces** se muestra un error y no se registra el punto.
4. **Dado que** falta algún dato obligatorio, **cuando** guardo, **entonces** se señala el campo faltante.
5. **Dado que** administro un edificio, **cuando** registro un segundo punto con la misma dirección y otro nombre, **entonces** ambos aparecen en "Mis puntos" *(caso de edificio: en la [entrevista 4](../entrevistas/transcripciones/entrevista-4-silvia.md) el edificio tiene dos cargadores)*.
6. **Dado que** la aplicación ya tiene 300 puntos registrados (límite del RNF-01, decisión DP4), **cuando** un anfitrión intenta registrar uno más, **entonces** se muestra un mensaje indicando que se alcanzó el límite de puntos de la plataforma y el punto no se registra.
7. **Dado que** registré el punto, **cuando** todavía no publiqué condiciones ni agenda, **entonces** el punto figura como "Incompleto" y no aparece en las búsquedas.
8. **Dado que** acabo de registrar un punto, **cuando** se confirma el alta, **entonces** se me invita a publicar sus condiciones de servicio (US-07) para completarlo.

### US-07 — Publicar condiciones del servicio

> **Como** anfitrión,
> **quiero** publicar la tarifa por kWh, la duración máxima por sesión y las instrucciones de acceso de mi punto,
> **para** que el conductor sepa de antemano cuánto va a pagar, cuánto tiempo puede quedarse y cómo entrar.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Must | 2 | US-06 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** tengo un punto registrado, **cuando** ingreso tarifa ($/kWh), duración máxima (horas y minutos) e instrucciones de acceso y guardo, **entonces** las condiciones quedan asociadas al punto.
2. **Dado que** la tarifa o la duración máxima están vacías, son 0 o son negativas, **cuando** guardo, **entonces** se muestra un error y no se publican.
3. **Dado que** modifico la tarifa, **cuando** guardo, **entonces** la nueva tarifa se usa en las estimaciones de nuevas búsquedas y las reservas ya confirmadas conservan la tarifa con la que se hicieron.
4. **Dado que** las instrucciones de acceso superan 500 caracteres, **cuando** escribo, **entonces** se muestra un contador y no se permite exceder el límite *(límite propuesto)*.

### US-08 — Gestionar la agenda de franjas horarias por día

> **Como** anfitrión,
> **quiero** definir las franjas horarias en que mi punto está disponible cada día,
> **para** ofrecerlo solo cuando me conviene.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Must | 5 | US-06 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** estoy en la agenda de un punto, **cuando** elijo un día y agrego una franja con hora de inicio y fin, **entonces** la franja aparece en ese día como *Libre*.
2. **Dado que** agrego una franja cuya hora de fin es anterior o igual a la de inicio, **cuando** guardo, **entonces** se muestra un error. *(Revisar según la decisión DP10: las franjas nocturnas, como 22:00–06:00, cruzan la medianoche; ver SPK-03.)*
3. **Dado que** agrego una franja que se superpone con otra del mismo día, **cuando** guardo, **entonces** se muestra un error y no se agrega.
4. **Dado que** tengo una franja *Libre*, **cuando** la elimino, **entonces** deja de estar disponible para los conductores.
5. **Dado que** una franja está *Reservada*, **cuando** la veo en la agenda, **entonces** se distingue visualmente de las libres y no puede eliminarse directamente: se me dirige a cancelar o modificar la reserva (US-09).
6. **Dado que** la agenda tiene al menos una franja libre futura y las condiciones están publicadas, **cuando** un conductor busca, **entonces** el punto puede aparecer en los resultados.

### US-09 — Cancelar o modificar una franja agendada

> **Como** anfitrión,
> **quiero** cancelar o modificar una franja que ya tiene una reserva,
> **para** adaptarme a un imprevisto dejando avisado al conductor.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra (sección Notificaciones) | Should | 3 | US-10, US-18 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo una reserva futura en mi punto, **cuando** elijo "Cancelar", ingreso un motivo y confirmo, **entonces** la reserva queda *Cancelada por el anfitrión* y se dispara la notificación al conductor (US-24).
2. **Dado que** tengo una reserva futura, **cuando** elijo "Modificar", selecciono un nuevo horario y confirmo, **entonces** la reserva muestra el nuevo horario y se dispara la notificación al conductor (US-24).
3. **Dado que** voy a cancelar, **cuando** estoy por confirmar, **entonces** se me pide confirmación explícita, indicando que el conductor será notificado.
4. **Dado que** la reserva ya pasó, **cuando** la veo, **entonces** no aparecen las opciones de cancelar ni modificar.

> **Decisión pendiente:** si una modificación requiere que el conductor la acepte. En este backlog, la modificación se aplica y se notifica; el conductor puede cancelar si no le sirve (US-19).

### US-10 — Ver las reservas recibidas en mi punto

> **Como** anfitrión,
> **quiero** ver las reservas de mis puntos con el día, la franja y el conductor,
> **para** saber quién viene y cuándo.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Propuesta (necesaria para US-09 y US-22) | Should | 2 | US-08, US-18 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo reservas futuras, **cuando** abro "Reservas recibidas", **entonces** veo cada una con punto, día, franja, nombre de usuario del conductor y su calificación promedio.
2. **Dado que** no tengo reservas, **cuando** abro la pantalla, **entonces** se muestra un mensaje indicando que no hay reservas.
3. **Dado que** tengo varias reservas, **cuando** las veo, **entonces** aparecen ordenadas de la más próxima a la más lejana.

### US-11 — Ver historial de sesiones e ingreso acumulado

> **Como** anfitrión,
> **quiero** ver el historial de sesiones realizadas en mis puntos y el ingreso acumulado,
> **para** conocer el resultado económico de compartir mi cargador.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Should | 3 | US-18 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo sesiones realizadas, **cuando** abro "Historial", **entonces** veo cada sesión con fecha, punto, conductor, energía (kWh) e importe.
2. **Dado que** tengo sesiones realizadas, **cuando** veo el historial, **entonces** se muestra el ingreso acumulado igual a la suma de los importes listados.
3. **Dado que** una reserva fue cancelada, **cuando** veo el historial, **entonces** no aparece como sesión ni suma al ingreso.
4. **Dado que** tengo más de un punto, **cuando** filtro por punto, **entonces** el listado y el ingreso acumulado corresponden solo a ese punto.

> **Supuesto S7:** como no hay integración con el cargador, una *sesión realizada* es una reserva no cancelada cuya franja ya terminó, y su importe es el costo estimado al reservar. A validar con el profesor.

---

## EP03 — Registrar mi vehículo

**Objetivo de la épica:** conocer el vehículo del conductor para calcular compatibilidad, tiempo y costo.

### US-12 — Registrar mi vehículo

> **Como** conductor,
> **quiero** registrar mi vehículo con marca, modelo, capacidad de batería y tipo de conector,
> **para** que la aplicación me muestre solo puntos compatibles y calcule tiempo y costo.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Must | 3 | US-02 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** inicié sesión como conductor, **cuando** completo marca, modelo, capacidad de batería (kWh) y tipo de conector y guardo, **entonces** el vehículo queda registrado y se muestra en "Mi vehículo".
2. **Dado que** elijo el tipo de conector, **cuando** despliego las opciones, **entonces** son las mismas que para los puntos: *Tipo 2, CCS2, CHAdeMO, GB/T, Toma domiciliaria*.
3. **Dado que** ingreso una capacidad de batería no numérica, igual a 0 o negativa, **cuando** guardo, **entonces** se muestra un error.
4. **Dado que** no tengo vehículo registrado, **cuando** intento buscar carga, **entonces** se me indica que primero debo registrar mi vehículo y se ofrece un acceso directo.
5. **Dado que** tengo un vehículo registrado, **cuando** edito sus datos y guardo, **entonces** las próximas búsquedas usan los datos nuevos.

> **Propuesta surgida de las entrevistas:** los anfitriones quieren conocer la **matrícula** del auto antes de que llegue ([entrevista 3](../entrevistas/transcripciones/entrevista-3-alejandro.md), [entrevista 4](../entrevistas/transcripciones/entrevista-4-silvia.md)). Se propone agregarla como dato opcional del vehículo; queda **a confirmar por el PO** porque la letra no la pide (ver [hallazgos](product-backlog.md#9-hallazgos-de-las-entrevistas-que-impactan-en-el-backlog)).

### US-13 — Recibir ayuda para identificar el tipo de conector

> **Como** conductor (o anfitrión) que no conoce los tipos de conector,
> **quiero** ver una ayuda con imagen y descripción breve de cada tipo,
> **para** elegir el correcto sin conocimientos técnicos.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión | Propuesta (deriva del RNF-02 de la letra) | Should | 2 | US-12, US-06 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** estoy eligiendo el tipo de conector, **cuando** toco el ícono de ayuda, **entonces** veo cada tipo con una imagen y una descripción de una o dos líneas en lenguaje no técnico.
2. **Dado que** estoy viendo la ayuda, **cuando** elijo un tipo desde ahí, **entonces** queda seleccionado en el formulario.
3. **Dado que** no encuentro mi conector, **cuando** leo la ayuda, **entonces** se sugiere consultar el manual del vehículo o la tapa de carga *(texto a validar)*.

---

## EP04 — Buscar y comparar puntos

**Objetivo de la épica:** que el conductor vea solo los puntos que puede usar en su zona y franja, con el tiempo y el costo de su carga. Es el núcleo de la propuesta de valor.

### US-14 — Buscar puntos por zona, día, franja y nivel de carga

> **Como** conductor,
> **quiero** indicar la zona, el día, la franja horaria y el nivel de carga actual de mi vehículo,
> **para** buscar dónde cargar cuando lo necesito.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Must | 5 | US-12, US-08 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** tengo un vehículo registrado, **cuando** abro "Buscar carga", **entonces** veo campos para zona, día, franja horaria (desde–hasta) y nivel de carga actual (%).
2. **Dado que** completo todos los campos y busco, **entonces** se muestra el listado de resultados (filtrado según US-15).
3. **Dado que** el nivel de carga es menor que 0 o mayor que 99, **cuando** busco, **entonces** se muestra un error *(con 100 % no se necesita cargar)*.
4. **Dado que** elijo un día pasado, **cuando** busco, **entonces** se muestra un error.
5. **Dado que** no hay resultados, **cuando** termina la búsqueda, **entonces** se muestra "No hay puntos compatibles disponibles en esa zona y franja" con la sugerencia de cambiar zona o franja.
6. **Dado que** hay 300 puntos registrados (RNF-01), **cuando** busco, **entonces** el listado se muestra correctamente (se verificará con datos simulados).

> **Decisión pendiente (DP8):** cómo se representa la "zona" (barrio/localidad de una lista, texto libre o mapa). Se explorará en los prototipos de la Iteración 1 (spike SPK-02 del [Product Backlog](product-backlog.md#7-historias-con-incertidumbre-spikes)).

### US-15 — Ver solo puntos compatibles y disponibles

> **Como** conductor,
> **quiero** que los resultados incluyan únicamente puntos con conector compatible con mi vehículo y disponibilidad en la franja que indiqué,
> **para** no perder tiempo con opciones que no puedo usar.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Must | 3 | US-14 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** mi vehículo tiene conector *Tipo 2*, **cuando** busco, **entonces** no aparece ningún punto con otro tipo de conector.
2. **Dado que** un punto compatible no tiene franjas libres que se superpongan con la franja buscada ese día, **cuando** busco, **entonces** ese punto no aparece.
3. **Dado que** un punto compatible tiene una franja libre dentro de la franja buscada, **cuando** busco, **entonces** aparece e indica el horario disponible.
4. **Dado que** un punto está *Incompleto* (sin condiciones o sin agenda), **cuando** busco, **entonces** no aparece.
5. **Dado que** un anfitrión fue dado de baja, **cuando** busco, **entonces** sus puntos no aparecen.

> **Regla de compatibilidad (supuesto S8):** conector del vehículo = conector del punto. Adaptadores y la compatibilidad AC/DC (por ejemplo, un vehículo CCS2 que también acepta Tipo 2) quedan como **hipótesis a validar**.

### US-16 — Ver tiempo y costo estimados de la carga

> **Como** conductor,
> **quiero** ver para cada punto el tiempo y el costo estimados de mi carga,
> **para** comparar alternativas antes de reservar.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Must | 3 | US-15, US-07 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** mi vehículo tiene batería de 60 kWh y busco con nivel 20 %, **cuando** veo un punto de 7 kW con tarifa $8/kWh, **entonces** se muestra energía ≈ 48 kWh, tiempo ≈ 7 h (6 h 51 min) y costo ≈ $384 *(ejemplo de la letra; cálculo hasta el 100 % y sin pérdidas, decisión DP3)*.
2. **Dado que** veo el listado, **cuando** comparo dos puntos, **entonces** cada uno muestra tiempo y costo calculados con **su propia** potencia y tarifa.
3. **Dado que** la duración máxima del punto es menor que el tiempo estimado, **cuando** veo el resultado, **entonces** se advierte "Carga parcial" y se muestran la energía y el costo correspondientes a esa duración máxima *(supuesto S5)*.
4. **Dado que** veo los resultados, **cuando** elijo ordenar por costo o por tiempo, **entonces** el listado se reordena de menor a mayor.
5. **Dado que** veo una estimación, **cuando** la leo, **entonces** se aclara que es aproximada.

> **Spike SPK-01:** la fórmula está confirmada (DP3); la forma de presentarla se valida con el prototipo de búsqueda ([Product Backlog §7](product-backlog.md#7-historias-con-incertidumbre-spikes)).

### US-17 — Ver el detalle y las condiciones de un punto

> **Como** conductor,
> **quiero** ver el detalle de un punto con sus condiciones, franjas libres y evaluaciones,
> **para** decidir si lo reservo.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Propuesta (necesaria para US-18) | Must | 2 | US-14, US-07 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** toco un resultado, **cuando** se abre el detalle, **entonces** veo nombre, zona, conector, potencia, tarifa, duración máxima, tiempo y costo estimados y las franjas libres del día buscado.
2. **Dado que** el punto tiene evaluaciones, **cuando** veo el detalle, **entonces** se muestra el promedio por criterio y la cantidad de evaluaciones.
3. **Dado que** no tengo una reserva confirmada en ese punto, **cuando** veo el detalle, **entonces** la dirección exacta y las instrucciones de acceso **no** se muestran completas *(propuesta por la privacidad del anfitrión, inspirada en EVmatch; hipótesis a validar)*.

---

## EP05 — Reservar una franja

**Objetivo de la épica:** asegurar la franja para el conductor y darle visibilidad al anfitrión.

### US-18 — Reservar una franja horaria

> **Como** conductor,
> **quiero** reservar una franja horaria en un punto de carga,
> **para** tener asegurado el lugar cuando llegue.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Must | 3 | US-17, US-08 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** estoy en el detalle de un punto, **cuando** elijo una franja libre, **entonces** veo un resumen con punto, día, horario, tiempo y costo estimados antes de confirmar.
2. **Dado que** confirmo la reserva, **entonces** se muestra un mensaje de éxito, la reserva aparece en "Mis reservas" y se habilitan la dirección exacta y las instrucciones de acceso.
3. **Dado que** reservé una franja, **cuando** otro conductor busca en ese horario, **entonces** esa franja ya no figura como libre.
4. **Dado que** la franja fue tomada por otro conductor mientras yo decidía, **cuando** confirmo, **entonces** se informa que ya no está disponible, no se crea la reserva y vuelvo al listado de resultados actualizado.
5. **Dado que** el horario elegido supera la duración máxima por sesión del punto, **cuando** intento confirmar, **entonces** se informa el límite y se ajusta la hora de fin.
6. **Dado que** mi cuenta también tiene perfil anfitrión, **cuando** busco carga, **entonces** mis propios puntos no aparecen en los resultados y no puedo reservarlos *(consecuencia de DP2)*.

### US-19 — Cancelar una reserva

> **Como** conductor,
> **quiero** cancelar una reserva que ya no voy a usar,
> **para** liberar la franja y avisar al anfitrión.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra (sección Notificaciones) | Should | 2 | US-20 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo una reserva futura, **cuando** elijo "Cancelar" y confirmo, **entonces** la reserva queda *Cancelada por el conductor*.
2. **Dado que** cancelé, **cuando** el anfitrión mira su agenda, **entonces** la franja vuelve a figurar como *Libre* y se dispara la notificación al anfitrión (US-25).
3. **Dado que** la reserva ya comenzó o pasó, **cuando** la veo, **entonces** no aparece la opción de cancelar.

> **Decisión pendiente:** si existe un plazo mínimo de cancelación o una penalización. La letra no lo menciona; por ahora no se incluye.

### US-20 — Ver mis reservas

> **Como** conductor,
> **quiero** ver mis reservas próximas y pasadas,
> **para** recordar dónde y cuándo tengo que ir y consultar las instrucciones de acceso.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Propuesta (necesaria para US-19 y US-21) | Must | 2 | US-18 | R1 (It. 1) |

**Criterios de aceptación**

1. **Dado que** tengo reservas, **cuando** abro "Mis reservas", **entonces** veo las próximas separadas de las pasadas, con punto, día, horario, costo estimado y estado.
2. **Dado que** abro una reserva próxima, **cuando** veo su detalle, **entonces** se muestran dirección e instrucciones de acceso.
3. **Dado que** una reserva fue cancelada o modificada por el anfitrión, **cuando** la veo, **entonces** se muestra el estado actualizado y el motivo.

---

## EP06 — Recibir avisos

**Objetivo de la épica:** mantener informadas a ambas partes ante cambios en una reserva. Las tres historias corresponden textualmente a la sección *Notificaciones* de la letra.

### US-24 — Notificar al conductor cuando el anfitrión cancela o modifica su franja

> **Como** conductor con una reserva,
> **quiero** recibir una notificación si el anfitrión cancela o modifica mi franja,
> **para** no ir al punto en vano y reorganizarme.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Should | 2 | US-09 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** el anfitrión canceló mi reserva, **cuando** ocurre la cancelación, **entonces** recibo una notificación con el punto, el día, el horario y el motivo.
2. **Dado que** el anfitrión modificó el horario, **cuando** ocurre el cambio, **entonces** recibo una notificación con el horario anterior y el nuevo.
3. **Dado que** toco la notificación, **cuando** se abre la app, **entonces** voy al detalle de esa reserva.

### US-25 — Notificar al anfitrión cuando un conductor cancela

> **Como** anfitrión,
> **quiero** ser notificado cuando un conductor cancela su reserva,
> **para** saber que la franja quedó libre en mi agenda.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Should | 1 | US-19 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** un conductor canceló una reserva en mi punto, **cuando** ocurre, **entonces** recibo una notificación con punto, día y horario liberado.
2. **Dado que** toco la notificación, **cuando** se abre la app, **entonces** voy a la agenda del punto con la franja marcada como *Libre*.

### US-26 — Recordatorio 30 minutos antes de la reserva

> **Como** conductor con una reserva,
> **quiero** recibir un recordatorio 30 minutos antes del horario pautado,
> **para** llegar a tiempo al punto de carga.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Should | 2 | US-18 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo una reserva vigente a las 19:00, **cuando** son las 18:30, **entonces** recibo un recordatorio con el nombre del punto, la dirección, el horario y acceso a las instrucciones de acceso.
2. **Dado que** la reserva fue cancelada antes de las 18:30, **cuando** llega ese horario, **entonces** no recibo el recordatorio.
3. **Dado que** la reserva se hizo con menos de 30 minutos de anticipación, **cuando** se confirma, **entonces** el comportamiento queda **pendiente de definir** (enviar recordatorio inmediato o no enviarlo).

> En el prototipo de frontend, las notificaciones se representarán como notificaciones simuladas dentro de la app o en la bandeja del sistema. El mecanismo real (push) queda a validar con el profesor.

---

## EP07 — Evaluar y reportar

**Objetivo de la épica:** construir confianza mutua mediante la reputación y darle a la comunidad un canal para reportar problemas.

### US-21 — Evaluar el punto de carga con diferentes criterios

> **Como** conductor que usó un punto,
> **quiero** evaluarlo con diferentes criterios,
> **para** ayudar a otros conductores a elegir.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor | Letra | Should | 3 | US-20 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo una sesión realizada en un punto, **cuando** abro la reserva pasada, **entonces** veo la opción "Evaluar".
2. **Dado que** evalúo, **cuando** completo la evaluación, **entonces** califico de 1 a 5 estrellas cada criterio: *exactitud de la información publicada, facilidad de acceso, estado del equipo y trato del anfitrión* *(criterios propuestos, a validar)*, con un comentario opcional.
3. **Dado que** envié la evaluación, **cuando** otro conductor ve el detalle del punto, **entonces** el promedio por criterio incluye mi evaluación.
4. **Dado que** ya evalué esa sesión, **cuando** vuelvo a la reserva, **entonces** no puedo evaluarla de nuevo.
5. **Dado que** la reserva fue cancelada, **cuando** la veo, **entonces** no aparece la opción de evaluar.

### US-22 — Evaluar al conductor

> **Como** anfitrión,
> **quiero** evaluar a los conductores que usaron mi punto,
> **para** que otros anfitriones conozcan su reputación.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Anfitrión | Letra | Could | 2 | US-10, US-11 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** tengo una sesión realizada, **cuando** la abro desde el historial, **entonces** veo la opción "Evaluar conductor".
2. **Dado que** evalúo, **cuando** envío, **entonces** califico de 1 a 5 estrellas *puntualidad, respeto de las condiciones y cuidado del equipo* *(criterios propuestos)*, con comentario opcional.
3. **Dado que** evalué a un conductor, **cuando** otro anfitrión ve una reserva de ese conductor (US-10), **entonces** ve su calificación promedio.
4. **Dado que** ya evalué esa sesión, **cuando** vuelvo, **entonces** no puedo evaluarla de nuevo.

### US-23 — Reportar un problema a la administración

> **Como** conductor o anfitrión,
> **quiero** reportar un problema con un punto, un usuario o una evaluación,
> **para** que la administración lo revise.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Conductor, Anfitrión | Propuesta (origen de los "reportes de la comunidad" de la letra) | Could | 3 | US-02 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** estoy en el detalle de un punto, de una reserva o de una evaluación, **cuando** elijo "Reportar", **entonces** puedo elegir un motivo de una lista y escribir una descripción.
2. **Dado que** envío el reporte, **cuando** se registra, **entonces** veo una confirmación y el reporte queda *Pendiente* en la bandeja del administrador (US-30).
3. **Dado que** reporto una evaluación que recibí, **cuando** elijo el motivo "Discrepo con esta evaluación", **entonces** el caso se deriva al arbitraje de evaluaciones (US-29).
4. **Dado que** la descripción está vacía, **cuando** intento enviar, **entonces** se me pide completarla.

---

## EP08 — Administrar la plataforma

**Objetivo de la épica:** proteger la confianza en la plataforma mediante moderación. Todas las historias corresponden al *Modo administrador* de la letra.

### US-27 — Dar de alta a otro administrador

> **Como** administrador,
> **quiero** dar de alta a otro administrador,
> **para** compartir las tareas de moderación sin que nadie pueda autoasignarse ese rol.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Administrador | Letra | Could | 2 | US-02 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** inicié sesión como administrador, **cuando** ingreso email, nombre de usuario y contraseña temporal de la nueva persona y confirmo, **entonces** se crea la cuenta con perfil *Administrador*.
2. **Dado que** el email o el usuario ya existen, **cuando** confirmo, **entonces** se informa el error.
3. **Dado que** soy conductor o anfitrión, **cuando** navego por la app, **entonces** no tengo acceso a esta funcionalidad.

### US-28 — Dar de baja usuarios por mala reputación o incumplimientos

> **Como** administrador,
> **quiero** dar de baja a un usuario indicando el motivo,
> **para** proteger a la comunidad de quienes incumplen reiteradamente.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Administrador | Letra | Could | 2 | US-02 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** busco un usuario, **cuando** abro su ficha, **entonces** veo su perfil, calificación promedio y cantidad de reportes recibidos.
2. **Dado que** elijo "Dar de baja", **cuando** selecciono un motivo (*mala reputación* o *incumplimiento*), agrego un comentario y confirmo, **entonces** el usuario queda *Inhabilitado*.
3. **Dado que** un usuario fue inhabilitado, **cuando** intenta iniciar sesión, **entonces** no puede (US-02, criterio 7).
4. **Dado que** un anfitrión fue inhabilitado, **cuando** un conductor busca, **entonces** sus puntos no aparecen (US-15, criterio 5).
5. **Dado que** el usuario inhabilitado tenía reservas futuras, **cuando** se lo da de baja, **entonces** el tratamiento de esas reservas queda **pendiente de definir**.

### US-29 — Arbitrar discrepancias en evaluaciones

> **Como** administrador,
> **quiero** revisar las evaluaciones en disputa y decidir si se mantienen o se anulan,
> **para** que la reputación refleje información justa.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Administrador | Letra | Could | 3 | US-21, US-22, US-23 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** hay evaluaciones en disputa, **cuando** abro "Evaluaciones en disputa", **entonces** veo cada caso con la evaluación, el motivo de la discrepancia y los datos de la reserva.
2. **Dado que** reviso un caso, **cuando** elijo "Mantener" o "Anular" y escribo la justificación, **entonces** el caso queda *Resuelto*.
3. **Dado que** anulé una evaluación, **cuando** se recalcula la reputación, **entonces** esa evaluación no cuenta en el promedio.

### US-30 — Gestionar reportes de la comunidad

> **Como** administrador,
> **quiero** ver y resolver los reportes enviados por los usuarios,
> **para** actuar sobre problemas de puntos, usuarios o evaluaciones.

| Actor | Origen | Prioridad | Estimación | Dependencias | Release |
|---|---|---|---|---|---|
| Administrador | Letra | Could | 3 | US-23 | R2 (It. 2) |

**Criterios de aceptación**

1. **Dado que** hay reportes, **cuando** abro "Reportes", **entonces** los veo con fecha, quién reporta, sobre qué, motivo y estado (*Pendiente, En revisión, Resuelto*).
2. **Dado que** abro un reporte, **cuando** cambio su estado y agrego un comentario de resolución, **entonces** el estado se actualiza.
3. **Dado que** filtro por estado, **cuando** elijo *Pendiente*, **entonces** solo veo los pendientes.
4. **Dado que** el reporte amerita una baja, **cuando** estoy en el reporte, **entonces** tengo un acceso directo a la ficha del usuario (US-28).

---

## Requerimientos no funcionales (restricciones transversales)

> Las decisiones (DP) y los supuestos (S) que se citan en los criterios están en el [Product Backlog §8](product-backlog.md#8-supuestos-y-decisiones-de-producto).

No son historias. Son **restricciones** que aplican a varias historias y que se incorporan a la Definition of Done del equipo (pendiente de redactar) y se verifican desde la Iteración 1.

| ID | RNF (letra) | Historias afectadas | Cómo se verificará |
|---|---|---|---|
| RNF-01 | Registro de hasta 300 puntos de carga (límite máximo, decisión DP4). | US-06, US-14, US-15 | Prueba con 300 puntos simulados; intento de registrar el punto 301. |
| RNF-02 | Fácil de usar para un rango etario amplio, incluidos usuarios que recién adoptan la movilidad eléctrica. | US-01, US-12, US-13, US-14, US-16, US-18 | Test de usabilidad con participantes de distintas edades (Iteraciones 1-2). |
| RNF-03 | Interfaz principalmente móvil (iOS y/o Android). | Todas | Revisión de prototipos en formato móvil. |
| RNF-04 | Seguir las guías de interfaz de cada plataforma. | Todas | Checklist de Material Design / Human Interface Guidelines en la revisión. |

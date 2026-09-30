# Product Backlog

> Documento de la Iteración 0 · [Volver al README](../README.md) · [Historias completas con criterios de aceptación](historias-usuario.md)

## 1. Descripción

El Product Backlog es la lista **ordenada** de todo lo que sabemos hoy que necesita el producto. Es un artefacto vivo: se va a refinar en cada iteración (en particular en la Iteración 2, donde la letra anticipa **cambios de requerimientos**).

- **Responsable:** el Product Owner del equipo.
- **Orden:** por prioridad MoSCoW y, dentro de cada categoría, por dependencias y valor (la priorización de los prototipos está a cargo de Sebastián).
- **Estimación:** puntos de historia (Fibonacci), inicial y relativa. Se recalibra en la Sprint Planning de la Iteración 1.
- **Criterios de aceptación:** cada historia los tiene completos en [historias-usuario.md](historias-usuario.md). La columna *CA* de la tabla indica cuántos tiene.

## 2. Jerarquía de épicas

```text
Producto: App de carga compartida para vehículos eléctricos
│
├── EP01 Acceder a mi cuenta ............ US-01 · US-02 · US-03 · US-04 · US-05
├── EP02 Gestionar mi punto de carga .... US-06 · US-07 · US-08 · US-09 · US-10 · US-11
├── EP03 Registrar mi vehículo .......... US-12 · US-13
├── EP04 Buscar y comparar puntos ....... US-14 · US-15 · US-16 · US-17
├── EP05 Reservar una franja ............ US-18 · US-19 · US-20
├── EP06 Recibir avisos ................. US-24 · US-25 · US-26
├── EP07 Evaluar y reportar ............. US-21 · US-22 · US-23
└── EP08 Administrar la plataforma ...... US-27 · US-28 · US-29 · US-30
```

**Justificación de las épicas.** Partimos de las secciones de la letra (*Registro y usuarios, Perfil anfitrión, Perfil conductor, Modo administrador, Notificaciones*) y las reorganizamos por **objetivo del usuario**, en lugar de por perfil, para no mezclar objetivos distintos en una misma épica. Por ejemplo, *Perfil conductor* de la letra se reparte entre *Registrar mi vehículo*, *Buscar y comparar puntos*, *Reservar una franja* y *Evaluar y reportar*. Siguiendo la convención acordada en la reunión del 30/09 (DP2), **cada épica tiene el mismo nombre que una actividad del [story map](../story-map/story-map.md)**, y cada historia US-xx corresponde a la funcionalidad F-xx con el mismo número del [README](../README.md#12-funcionalidades-por-interesado).

## 3. Product Backlog ordenado

Leyenda de release: **R1** = MVP, prototipos de la Iteración 1 · **R2** = completar la letra, prototipos de la Iteración 2.

| Orden | ID | Épica | Historia | Actor | Descripción breve | Valor | Prioridad | CA | Est. (pts) | Depende de | Release |
|:-:|---|---|---|---|---|:-:|:-:|:-:|:-:|---|:-:|
| 1 | [US-01](historias-usuario.md#us-01--registrar-nuevo-usuario-con-perfil) | EP01 | Registrar usuario con perfil | Conductor, Anfitrión | Email, usuario, contraseña y uno o ambos perfiles | Alto | Must | 7 | 3 | — | R1 |
| 2 | [US-02](historias-usuario.md#us-02--iniciar-sesión-eligiendo-el-perfil) | EP01 | Iniciar sesión eligiendo perfil | Todos | Usuario, contraseña y perfil | Alto | Must | 8 | 3 | US-01 | R1 |
| 3 | [US-06](historias-usuario.md#us-06--registrar-punto-de-carga) | EP02 | Registrar punto de carga | Anfitrión | Nombre, dirección, conector, kW | Alto | Must | 7 | 3 | US-02 | R1 |
| 4 | [US-07](historias-usuario.md#us-07--publicar-condiciones-del-servicio) | EP02 | Publicar condiciones | Anfitrión | Tarifa/kWh, duración máx., acceso | Alto | Must | 4 | 2 | US-06 | R1 |
| 5 | [US-08](historias-usuario.md#us-08--gestionar-la-agenda-de-franjas-horarias-por-día) | EP02 | Gestionar agenda de franjas | Anfitrión | Franjas disponibles por día | Alto | Must | 6 | 5 | US-06 | R1 |
| 6 | [US-12](historias-usuario.md#us-12--registrar-mi-vehículo) | EP03 | Registrar vehículo | Conductor | Marca, modelo, batería, conector | Alto | Must | 5 | 3 | US-02 | R1 |
| 7 | [US-14](historias-usuario.md#us-14--buscar-puntos-por-zona-día-franja-y-nivel-de-carga) | EP04 | Buscar por zona, día, franja y nivel | Conductor | Parámetros de búsqueda | Alto | Must | 6 | 5 | US-12, US-08 | R1 |
| 8 | [US-15](historias-usuario.md#us-15--ver-solo-puntos-compatibles-y-disponibles) | EP04 | Solo compatibles y disponibles | Conductor | Filtro por conector y agenda | Alto | Must | 5 | 3 | US-14 | R1 |
| 9 | [US-16](historias-usuario.md#us-16--ver-tiempo-y-costo-estimados-de-la-carga) | EP04 | Tiempo y costo estimados | Conductor | Cálculo por punto y orden | Alto | Must | 5 | 3 | US-15, US-07 | R1 |
| 10 | [US-17](historias-usuario.md#us-17--ver-el-detalle-y-las-condiciones-de-un-punto) | EP04 | Detalle del punto | Conductor | Condiciones, franjas, evaluaciones | Alto | Must | 3 | 2 | US-14, US-07 | R1 |
| 11 | [US-18](historias-usuario.md#us-18--reservar-una-franja-horaria) | EP05 | Reservar franja | Conductor | Resumen y confirmación | Alto | Must | 6 | 3 | US-17, US-08 | R1 |
| 12 | [US-20](historias-usuario.md#us-20--ver-mis-reservas) | EP05 | Ver mis reservas | Conductor | Próximas y pasadas | Alto | Must | 3 | 2 | US-18 | R1 |
| 13 | [US-10](historias-usuario.md#us-10--ver-las-reservas-recibidas-en-mi-punto) | EP02 | Ver reservas recibidas | Anfitrión | Quién viene y cuándo | Medio | Should | 3 | 2 | US-08, US-18 | R2 |
| 14 | [US-19](historias-usuario.md#us-19--cancelar-una-reserva) | EP05 | Cancelar reserva | Conductor | Libera la franja | Alto | Should | 3 | 2 | US-20 | R2 |
| 15 | [US-25](historias-usuario.md#us-25--notificar-al-anfitrión-cuando-un-conductor-cancela) | EP06 | Aviso al anfitrión por cancelación | Anfitrión | Notificación de franja liberada | Medio | Should | 2 | 1 | US-19 | R2 |
| 16 | [US-09](historias-usuario.md#us-09--cancelar-o-modificar-una-franja-agendada) | EP02 | Cancelar/modificar franja agendada | Anfitrión | Con motivo y aviso | Alto | Should | 4 | 3 | US-10, US-18 | R2 |
| 17 | [US-24](historias-usuario.md#us-24--notificar-al-conductor-cuando-el-anfitrión-cancela-o-modifica-su-franja) | EP06 | Aviso al conductor por cambio | Conductor | Notificación de cancelación/modificación | Alto | Should | 3 | 2 | US-09 | R2 |
| 18 | [US-26](historias-usuario.md#us-26--recordatorio-30-minutos-antes-de-la-reserva) | EP06 | Recordatorio 30 min | Conductor | Recordatorio previo | Medio | Should | 3 | 2 | US-18 | R2 |
| 19 | [US-13](historias-usuario.md#us-13--recibir-ayuda-para-identificar-el-tipo-de-conector) | EP03 | Ayuda de conectores | Conductor, Anfitrión | Imágenes y descripción | Medio | Should | 3 | 2 | US-12, US-06 | R2 |
| 20 | [US-03](historias-usuario.md#us-03--recuperar-contraseña) | EP01 | Recuperar contraseña | Todos | Por email | Medio | Should | 3 | 2 | US-01 | R2 |
| 21 | [US-04](historias-usuario.md#us-04--cerrar-sesión) | EP01 | Cerrar sesión | Todos | Logout | Medio | Should | 2 | 1 | US-02 | R2 |
| 22 | [US-05](historias-usuario.md#us-05--editar-mis-datos-de-usuario) | EP01 | Editar usuario (menos email) | Conductor, Anfitrión | Datos de registro | Medio | Should | 5 | 2 | US-01, US-02 | R2 |
| 23 | [US-21](historias-usuario.md#us-21--evaluar-el-punto-de-carga-con-diferentes-criterios) | EP07 | Evaluar punto con criterios | Conductor | Estrellas por criterio | Medio | Should | 5 | 3 | US-20 | R2 |
| 24 | [US-11](historias-usuario.md#us-11--ver-historial-de-sesiones-e-ingreso-acumulado) | EP02 | Historial e ingreso acumulado | Anfitrión | Sesiones e ingreso | Medio | Should | 4 | 3 | US-18 | R2 |
| 25 | [US-22](historias-usuario.md#us-22--evaluar-al-conductor) | EP07 | Evaluar conductor | Anfitrión | Estrellas por criterio | Medio | Could | 4 | 2 | US-10, US-11 | R2 |
| 26 | [US-23](historias-usuario.md#us-23--reportar-un-problema-a-la-administración) | EP07 | Reportar problema | Conductor, Anfitrión | Punto, usuario o evaluación | Medio | Could | 4 | 3 | US-02 | R2 |
| 27 | [US-30](historias-usuario.md#us-30--gestionar-reportes-de-la-comunidad) | EP08 | Gestionar reportes | Administrador | Bandeja con estados | Medio | Could | 4 | 3 | US-23 | R2 |
| 28 | [US-29](historias-usuario.md#us-29--arbitrar-discrepancias-en-evaluaciones) | EP08 | Arbitrar evaluaciones | Administrador | Mantener o anular | Medio | Could | 3 | 3 | US-21, US-22, US-23 | R2 |
| 29 | [US-28](historias-usuario.md#us-28--dar-de-baja-usuarios-por-mala-reputación-o-incumplimientos) | EP08 | Baja de usuarios | Administrador | Con motivo | Medio | Could | 5 | 2 | US-02 | R2 |
| 30 | [US-27](historias-usuario.md#us-27--dar-de-alta-a-otro-administrador) | EP08 | Alta de administrador | Administrador | Solo por otro admin | Bajo | Could | 3 | 2 | US-02 | R2 |

## 4. Resumen

| Prioridad | Historias | Puntos | Release |
|---|:-:|:-:|---|
| Must | 12 | 37 | R1 — Iteración 1 |
| Should | 12 | 25 | R2 — Iteración 2 |
| Could | 6 | 15 | R2 — Iteración 2 (si la capacidad lo permite, al menos a nivel de prototipo) |
| **Total** | **30** | **77** | |

| Épica | Historias | Puntos |
|---|:-:|:-:|
| EP01 Acceder a mi cuenta | 5 | 11 |
| EP02 Gestionar mi punto de carga | 6 | 18 |
| EP03 Registrar mi vehículo | 2 | 5 |
| EP04 Buscar y comparar puntos | 4 | 13 |
| EP05 Reservar una franja | 3 | 7 |
| EP06 Recibir avisos | 3 | 5 |
| EP07 Evaluar y reportar | 3 | 8 |
| EP08 Administrar la plataforma | 4 | 10 |

**Capacidad de referencia (no es una velocidad medida).** La capacidad del equipo se define en las actas (decisión D5 del 30/09, en revisión: la letra indica 5 horas-persona por semana). En la Iteración 1 vamos a medir la velocidad real y, si R2 no entra completa en la Iteración 2, las historias *Could* se van a priorizar a nivel de prototipo (wireframe) antes que de frontend. **No se elimina ninguna funcionalidad de la letra.**

## 5. Backlog fuera del alcance actual (Won't Have por ahora)

Ideas que surgieron del análisis de competidores o de las entrevistas y que **no** están en la letra. Quedan registradas pero no se estiman ni se comprometen:

| ID | Idea | Origen | Motivo para no incluirla ahora |
|---|---|---|---|
| W-01 | Pago dentro de la aplicación | Competidores (UTE Mueve, eOne, EVmatch) y [entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md) | No lo pide la letra; requiere backend y pasarela de pago. |
| W-02 | Disponibilidad en tiempo real / activación remota del cargador | UTE Mueve, eOne, EVmatch | Requiere integración con hardware. |
| W-03 | Mapa con geolocalización y navegación | PlugShare, eOne | La búsqueda por zona de la letra puede validarse sin mapa; se revisará según los resultados de la Iteración 1. |
| W-04 | Varios vehículos por conductor | PlugShare | La letra habla de "su vehículo"; a validar. |
| W-05 | Reservas recurrentes | Co Charger | Interesante para el segmento, pero no está en la letra. |
| W-06 | Aprobación manual de cada reserva por el anfitrión | EVmatch | La letra plantea reserva directa. |
| W-07 | Ayuda para calcular la tarifa del anfitrión | Co Charger | En la [entrevista 3](../entrevistas/transcripciones/entrevista-3-alejandro.md) el anfitrión ya tenía una idea de su tarifa ($10–12/kWh) y en la [entrevista 4](../entrevistas/transcripciones/entrevista-4-silvia.md) la definiría un contador: no es una necesidad clara para el MVP. |
| W-08 | Chat entre conductor y anfitrión | — | No está en la letra; las instrucciones de acceso cubren la necesidad inicial. |
| W-09 | Favoritos | EVmatch, Electromaps | Bajo impacto en la validación. |

## 6. Cobertura de la letra

Cada requisito funcional de la letra está cubierto por al menos una historia.

| Sección de la letra | Requisito | Historia(s) |
|---|---|---|
| Registro y usuarios | Login con usuario y contraseña, acceso seguro y simplificado | US-02 |
| Registro y usuarios | Recuperar contraseña | US-03 |
| Registro y usuarios | Logout | US-04 |
| Registro y usuarios | Registrar usuario (email, usuario, contraseña, perfil) | US-01 |
| Registro y usuarios | Editar usuario (todo menos el email) | US-05 |
| Registro y usuarios | Tres perfiles; el usuario elige anfitrión, conductor o ambos (DP2); elige perfil al hacer login | US-01, US-02, US-05 |
| Registro y usuarios | El alta del administrador la hace otro administrador | US-27 (y US-01 CA 6) |
| Perfil anfitrión | Registrar punto (nombre, dirección, conector, potencia) | US-06 |
| Perfil anfitrión | Publicar condiciones (tarifa/kWh, duración máxima, instrucciones de acceso) | US-07 |
| Perfil anfitrión | Gestionar agenda de franjas por día | US-08 |
| Perfil anfitrión | Evaluar a los conductores | US-22 |
| Perfil anfitrión | Historial de sesiones e ingreso acumulado | US-11 |
| Perfil conductor | Registrar vehículo (marca, modelo, batería, conector) | US-12 |
| Perfil conductor | Buscar por zona, día, franja y nivel de carga | US-14 |
| Perfil conductor | Mostrar solo puntos compatibles y disponibles | US-15 |
| Perfil conductor | Tiempo y costo estimados | US-16 |
| Perfil conductor | Reservar franja | US-18 |
| Perfil conductor | Evaluar el punto con diferentes criterios | US-21 |
| Modo administrador | Dar de baja usuarios | US-28 |
| Modo administrador | Arbitrar discrepancias en evaluaciones | US-29 |
| Modo administrador | Gestionar reportes de la comunidad | US-30 (y US-23 como origen) |
| Notificaciones | Anfitrión cancela o modifica → notificar al conductor | US-09, US-24 |
| Notificaciones | Conductor cancela → notificar al anfitrión | US-19, US-25 |
| Notificaciones | Recordatorio 30 minutos antes | US-26 |
| RNF | Límite de 300 puntos, usabilidad, móvil, guías de plataforma | RNF-01 a RNF-04 ([ver](historias-usuario.md#requerimientos-no-funcionales-restricciones-transversales)) |

## 7. Historias con incertidumbre (spikes)

Siguiendo el criterio de **épicas complejas**, cuando una historia tiene incertidumbre alta sobre *qué* construir o *cómo* presentarlo, se separa una parte de **investigación** (spike, con timebox en horas y sin puntos) de la parte de **desarrollo** (la historia estimada en puntos). Así la historia cumple la DoR (*estimable*) sin inflar su estimación.

| ID | Spike (investigación) | Historia de desarrollo | Qué ya está resuelto | Qué falta resolver | Cómo se resuelve | Timebox |
|---|---|---|---|---|---|---|
| SPK-01 | Presentación de tiempo y costo estimados | US-16 | La fórmula (supuestos S1–S4, ver [§8](#8-supuestos-y-decisiones-de-producto)): 60 kWh al 20 % → 48 kWh; a 7 kW ≈ 7 h; a $8/kWh = $384. | Cómo prefiere verlo el usuario (valores exactos o rangos, orden por defecto, cómo se muestra la *carga parcial* de S5). | Crazy 8s y test del prototipo de búsqueda (Iteración 1). | [COMPLETAR] h |
| SPK-02 | Representación de la "zona" en la búsqueda | US-14 | Los parámetros de búsqueda (zona, día, franja, nivel), definidos por la letra. | Lista de barrios, texto libre o mapa (decisión DP8). | Alternativas en Crazy 8s del prototipo de búsqueda (Iteración 1). | [COMPLETAR] h |
| SPK-03 | Franjas que cruzan la medianoche | US-08, US-14, US-18 | Las franjas se cargan por día (letra). | Si una franja como 22:00–06:00 se permite y cómo se carga en la agenda (decisión DP10). | Entrevistas (en la [entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md) el conductor quiere dejar el auto cargando *toda la noche*) y prototipo de agenda. | [COMPLETAR] h |

Los spikes se planifican en la Sprint Planning de la Iteración 1 como tareas con horas, no como historias.

## 8. Supuestos y decisiones de producto

Las historias se apoyan en estas decisiones y supuestos. Usamos el prefijo **DP** (decisión de producto) para no confundirlas con las decisiones de proceso de las actas (D1, D2…).

> **Estado:** propuesta del equipo, **a confirmar por el Product Owner** y a registrar en un acta. Mientras no se confirmen, los criterios de aceptación que dependen de ellas se consideran provisorios.

| # | Supuesto / decisión | Fundamento | Historias | Estado |
|---|---|---|---|---|
| DP2 | Una cuenta puede tener los perfiles de anfitrión y de conductor; al hacer login se elige con cuál entrar. Nadie puede reservar sus propios puntos. | La letra dice que el usuario elige qué perfil registra y con cuál se loguea; en la [entrevista 3](../entrevistas/transcripciones/entrevista-3-alejandro.md), el anfitrión también tiene un vehículo eléctrico en la familia. | US-01, US-02, US-05, US-18 | A confirmar |
| DP3 | La estimación calcula la carga hasta el 100 % y sin pérdidas. | Ejemplo de la letra: 60 kWh al 20 % → 48 kWh; a 7 kW ≈ 7 h; a $8/kWh = $384. | US-16 | A confirmar |
| DP4 | 300 puntos de carga es el **límite máximo** de la plataforma: no se permite registrar el 301. | RNF de la letra ("contemplar el registro de hasta 300 puntos"). | US-06, US-14, RNF-01 | A confirmar |
| DP8 | Cómo se representa la "zona" en la búsqueda (lista de barrios, texto libre o mapa). | La letra no lo define. | US-14 (SPK-02) | **Pendiente** |
| DP10 | Si se permiten franjas que cruzan la medianoche (ej. 22:00–06:00). | En la [entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md) el conductor quiere dejar el auto cargando *toda la noche*. | US-08, US-14, US-18 (SPK-03) | **Pendiente** |
| S1 | Energía necesaria = capacidad de batería × (100 % − nivel actual). | Ejemplo de la letra. | US-16 | Confirmado por la letra |
| S2 | Tiempo estimado = energía necesaria / potencia del punto. | Ejemplo de la letra (48 / 7 ≈ 6 h 51 min). | US-16 | Confirmado por la letra |
| S3 | Costo estimado = energía necesaria × tarifa por kWh. | Ejemplo de la letra. | US-16 | Confirmado por la letra |
| S4 | No se consideran pérdidas ni la reducción de potencia cerca del 100 %. | Simplificación del ejemplo de la letra. | US-16 | A confirmar |
| S5 | Si la duración máxima por sesión es menor que el tiempo estimado, se avisa que la carga será parcial. | Se deduce de la "duración máxima por sesión" de la letra. | US-16 | A confirmar |
| S6 | El pago no se hace dentro de la aplicación en el MVP. | La letra no lo pide (ver W-01). | — | A confirmar con la docente |
| S7 | Una *sesión realizada* es una reserva no cancelada cuya franja ya terminó; su importe es el costo estimado al reservar. | No hay integración con el cargador (el alcance es frontend). | US-11 | A confirmar con la docente |
| S8 | Compatible = mismo tipo de conector en el vehículo y en el punto (sin adaptadores). | Interpretación literal de la letra. | US-15 | A confirmar |

## 9. Hallazgos de las entrevistas que impactan en el backlog

Resumen de lo que salió en las [entrevistas](../README.md#13-entrevistas) y cómo lo reflejamos en las historias.

| Hallazgo | Entrevista | Impacto en el backlog |
|---|---|---|
| El conductor llega al cargador y está ocupado, fuera de servicio o con un auto a combustión estacionado; las apps actuales no lo reflejan. | [E1](../entrevistas/transcripciones/entrevista-1-martin.md), [E2](../entrevistas/transcripciones/entrevista-2-laura.md) | Refuerza la reserva de franja (US-18) y la búsqueda de solo puntos disponibles (US-15). Justifica poder reportar un punto que no coincide con lo publicado (US-23). |
| Lo que más querrían es "saber seguro que el punto va a estar libre y que el enchufe me va a servir". | [E2](../entrevistas/transcripciones/entrevista-2-laura.md) | Confirma el núcleo del MVP: compatibilidad (US-15) + reserva (US-18). |
| No siempre saben cuánto les va a costar la carga antes de hacerla ("te enterás cuando pasás la tarjeta"). | [E1](../entrevistas/transcripciones/entrevista-1-martin.md) | Confirma el valor de mostrar el costo estimado antes de reservar (US-16). |
| Los conductores actuales conocen su conector (Type 2, CCS2, CHAdeMO), pero admiten que al principio les costó. | [E1](../entrevistas/transcripciones/entrevista-1-martin.md), [E2](../entrevistas/transcripciones/entrevista-2-laura.md) y [resumen §1.3](../README.md#13-entrevistas) | La ayuda de conectores (US-13) queda como *Should*: sirve para usuarios nuevos, no para el usuario actual. |
| Conductores del interior que viajan a Montevideo necesitan cargar cerca de donde se hospedan. | [E2](../entrevistas/transcripciones/entrevista-2-laura.md) | Nuevo segmento a tener en cuenta en la búsqueda por zona (US-14, DP8). |
| El anfitrión quiere saber quién viene: nombre, **matrícula del auto** y reseñas; el edificio pediría además documento. | [E3](../entrevistas/transcripciones/entrevista-3-alejandro.md), [E4](../entrevistas/transcripciones/entrevista-4-silvia.md) | Refuerza evaluar al conductor (US-22) y ver reservas recibidas con datos del conductor (US-10). **Propuesta:** agregar la matrícula como dato opcional del vehículo (US-12), a confirmar por el PO porque la letra no la pide. |
| El anfitrión fija horarios estables (ej. lunes a viernes 9–17) y el edificio exige que el auto se retire a la hora pactada. | [E3](../entrevistas/transcripciones/entrevista-3-alejandro.md), [E4](../entrevistas/transcripciones/entrevista-4-silvia.md) | Confirma la agenda por franjas (US-08) y el respeto de la duración máxima (US-18, CA 5). |
| El edificio tiene dos cargadores y el acceso pasa por portería. | [E4](../entrevistas/transcripciones/entrevista-4-silvia.md) | Confirma registrar varios puntos en la misma dirección (US-06, CA 5) y la importancia de las instrucciones de acceso (US-07). |
| La tarifa que cobraría el anfitrión ronda $10–12/kWh, sobre un costo nocturno de $4–5/kWh. | [E3](../entrevistas/transcripciones/entrevista-3-alejandro.md) | Da un valor de referencia realista para los datos simulados del prototipo (US-07, US-16). |

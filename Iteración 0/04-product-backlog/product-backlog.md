# Product Backlog

> Documento de la Iteración 0 · [Volver al README](../README.md) · [Historias completas con criterios de aceptación](historias-usuario.md)

## 1. Descripción

El Product Backlog es la lista **ordenada** de todo lo que sabemos hoy que necesita el producto. Es un artefacto vivo: se va a refinar en cada iteración (en particular en la Iteración 2, donde el PDF anticipa **cambios de requerimientos**).

- **Responsable:** el Product Owner del equipo.
- **Orden:** por prioridad MoSCoW y, dentro de cada categoría, por dependencias y valor (ver [priorización](../05-priorizacion/priorizacion-prototipos.md)).
- **Estimación:** puntos de historia (Fibonacci), inicial y relativa. Se recalibra en la Sprint Planning de la Iteración 1.
- **Criterios de aceptación:** cada historia los tiene completos en [historias-usuario.md](historias-usuario.md). La columna *CA* de la tabla indica cuántos tiene.

## 2. Jerarquía de épicas

```text
Producto: App de carga compartida para vehículos eléctricos
│
├── EP01 Autenticación y cuenta ................ US-01 · US-02 · US-03 · US-04 · US-05
├── EP02 Gestión del punto de carga (anfitrión)  US-06 · US-07 · US-08 · US-09 · US-10 · US-11
├── EP03 Vehículos ............................. US-12 · US-13
├── EP04 Búsqueda y estimación ................. US-14 · US-15 · US-16 · US-17
├── EP05 Reservas .............................. US-18 · US-19 · US-20
├── EP06 Notificaciones ........................ US-24 · US-25 · US-26
├── EP07 Evaluaciones y reportes ............... US-21 · US-22 · US-23
└── EP08 Administración ........................ US-27 · US-28 · US-29 · US-30
```

**Justificación de las épicas.** Partimos de las secciones del PDF (*Registro y usuarios, Perfil anfitrión, Perfil conductor, Modo administrador, Notificaciones*). Las reorganizamos por **objetivo de negocio**, en lugar de por perfil, para evitar épicas que mezclen objetivos distintos. Por ejemplo, *Perfil conductor* del PDF se reparte en Vehículos, Búsqueda y estimación, Reservas y Evaluaciones. Descartamos crear épicas separadas para "Perfiles" (se resuelve dentro de EP01) y para "Historial e ingresos" (tendría una sola historia, por lo que la incluimos en EP02, que agrupa todo lo que hace el anfitrión con su punto).

## 3. Product Backlog ordenado

Leyenda de release: **R1** = MVP, prototipos de la Iteración 1 · **R2** = completar el PDF, prototipos de la Iteración 2.

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
| EP01 Autenticación y cuenta | 5 | 11 |
| EP02 Gestión del punto de carga | 6 | 18 |
| EP03 Vehículos | 2 | 5 |
| EP04 Búsqueda y estimación | 4 | 13 |
| EP05 Reservas | 3 | 7 |
| EP06 Notificaciones | 3 | 5 |
| EP07 Evaluaciones y reportes | 3 | 8 |
| EP08 Administración | 4 | 10 |

**Capacidad de referencia (no es una velocidad medida).** Según el PDF, el esfuerzo esperado es de 5 horas-persona por semana; con 3 integrantes e iteraciones de 2 semanas, son unas **30 horas-persona por iteración**, que además incluyen los eventos Scrum y la documentación. En la Iteración 1 vamos a medir la velocidad real y, si R2 no entra completa en la Iteración 2, las historias *Could* se van a priorizar a nivel de prototipo (wireframe) antes que de frontend. **No se elimina ninguna funcionalidad del PDF.**

## 5. Backlog fuera del alcance actual (Won't Have por ahora)

Ideas que surgieron del análisis de competidores o de las personas y que **no** están en el PDF. Quedan registradas pero no se estiman ni se comprometen:

| ID | Idea | Origen | Motivo para no incluirla ahora |
|---|---|---|---|
| W-01 | Pago dentro de la aplicación | Competidores (UTE Mueve, eOne, EVmatch) | No lo pide el PDF; requiere backend y pasarela de pago. |
| W-02 | Disponibilidad en tiempo real / activación remota del cargador | UTE Mueve, eOne, EVmatch | Requiere integración con hardware. |
| W-03 | Mapa con geolocalización y navegación | PlugShare, eOne | La búsqueda por zona del PDF puede validarse sin mapa; se revisará según los resultados de la Iteración 1. |
| W-04 | Varios vehículos por conductor | Persona Lucía / PlugShare | El PDF habla de "su vehículo"; a validar. |
| W-05 | Reservas recurrentes | Co Charger | Interesante para el segmento, pero no está en el PDF. |
| W-06 | Aprobación manual de cada reserva por el anfitrión | EVmatch | El PDF plantea reserva directa. |
| W-07 | Ayuda para calcular la tarifa del anfitrión | Co Charger | Depende de validar H5. |
| W-08 | Chat entre conductor y anfitrión | — | No está en el PDF; las instrucciones de acceso cubren la necesidad inicial. |
| W-09 | Favoritos | EVmatch, Electromaps | Bajo impacto en la validación. |

## 6. Cobertura del PDF

Cada requisito funcional del PDF está cubierto por al menos una historia.

| Sección del PDF | Requisito | Historia(s) |
|---|---|---|
| Registro y usuarios | Login con usuario y contraseña, acceso seguro y simplificado | US-02 |
| Registro y usuarios | Recuperar contraseña | US-03 |
| Registro y usuarios | Logout | US-04 |
| Registro y usuarios | Registrar usuario (email, usuario, contraseña, perfil) | US-01 |
| Registro y usuarios | Editar usuario (todo menos el email) | US-05 |
| Registro y usuarios | Tres perfiles; el usuario elige anfitrión, conductor o ambos (D2); elige perfil al hacer login | US-01, US-02, US-05 |
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
| SPK-01 | Presentación de tiempo y costo estimados | US-16 | La fórmula (S1–S4, confirmada en D3): 60 kWh al 20 % → 48 kWh; a 7 kW ≈ 7 h; a $8/kWh = $384. | Cómo prefiere verlo el usuario (valores exactos o rangos, orden por defecto, cómo se muestra la *carga parcial* de S5). | Crazy 8s y test del prototipo P1 (Iteración 1). | [COMPLETAR] h |
| SPK-02 | Representación de la "zona" en la búsqueda | US-14 | Los parámetros de búsqueda (zona, día, franja, nivel), definidos por el PDF. | Lista de barrios, texto libre o mapa (decisión D8). | Alternativas en Crazy 8s del prototipo P1 (Iteración 1). | [COMPLETAR] h |
| SPK-03 | Franjas que cruzan la medianoche | US-08, US-14, US-18 | Las franjas se cargan por día (PDF). | Si una franja como 22:00–06:00 se permite y cómo se carga en la agenda (decisión D10). | Entrevistas (H9) y prototipo P5. | [COMPLETAR] h |

Los spikes se planifican en la Sprint Planning de la Iteración 1 como tareas con horas, no como historias.

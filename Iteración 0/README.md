# Iteración 0 — Identificación y definición del problema

**Proyecto:** [NOMBRE DEL PRODUCTO] — MVP de aplicación de carga compartida para vehículos eléctricos
**Equipo:** [Apellido1] – [Apellido2] – [Apellido3]
**Mini-proyecto ágil · Ingeniería de Software Ágil 1 · Semestre 2, 2026**
**Período de la iteración:** 21/09 – 10/10 (según el roadmap del obligatorio)

> **Nota de uso:** los bloques marcados con `[COMPLETAR]` requieren datos propios del equipo (nombres, acuerdos, horas, resultados de entrevistas).

Este README resume la Iteración 0 y funciona como índice de los artefactos detallados. Cada sección enlaza al documento donde está el análisis completo.

## Índice de artefactos

```text
Iteración 0/
├── README.md                                  ← este documento (resumen, trazabilidad y checklist)
├── 00-marco-de-trabajo/
│   └── marco-de-trabajo.md                    ← roles, adaptación de Scrum, DoR, DoD, políticas, eventos
├── 01-descubrimiento/
│   ├── interesados.md                         ← stakeholders y funcionalidades por interesado
│   ├── problema.md                            ← problema de negocio, visión, propuesta de valor, supuestos
│   ├── personas.md                            ← personas hipotéticas y registro de hipótesis (H1–H10)
│   ├── guion-entrevistas.md                   ← guiones para conductores y anfitriones + registro
│   ├── escenarios.md                          ← 9 escenarios principales
│   └── valor-negocio.md                       ← valor por escenario y épica, indicadores
├── 02-competidores/
│   └── analisis-competidores.md               ← 6 soluciones, tabla comparativa, insights, fuentes
├── 03-story-map/
│   └── story-map.md                           ← backbone, tareas, historias y cortes de release
├── 04-product-backlog/
│   ├── product-backlog.md                     ← backlog ordenado, épicas, estimaciones, cobertura del PDF
│   └── historias-usuario.md                   ← 30 historias con criterios de aceptación + RNF
├── 05-priorizacion/
│   └── priorizacion-prototipos.md             ← MoSCoW, MVP, prototipos priorizados, trazabilidad
└── 06-gestion-del-sprint/
    ├── sprint-planning.md                     ← objetivo, capacidad y Sprint Backlog (tareas T1–T14)
    ├── dailies.md                             ← registro de Daily Scrum
    ├── seguimiento.md                         ← registro de horas y burndown
    ├── sprint-review.md                       ← revisión del incremento y feedback
    └── retrospectiva.md                       ← inspección del proceso y acciones de mejora
```

Agregamos `personas.md` a la estructura sugerida para no mezclar las personas con el análisis de interesados. Las carpetas `00` y `06` cubren la parte de la rúbrica **general del proyecto** (marco de trabajo, planificación, seguimiento, inspección), que se repite en cada iteración.

---

## 1. Objetivo de la Iteración 0

Según la rúbrica del obligatorio, el objetivo es **identificar y definir el problema a resolver**. Tiene dos resultados clave:

| Resultado clave | Artefactos |
|---|---|
| **Identificación del problema a resolver** | Identificación de interesados, lista de funcionalidades por interesado y estudio de competidores; entendimiento del problema de negocio, usuarios, escenarios y valor de negocio. |
| **Definición del problema/solución** | Story Map, Product Backlog con épicas, historias de usuario y criterios de aceptación; priorización de los prototipos a idear, construir y validar. |

**Objetivo del sprint (Sprint Goal):**
> Contar con un entendimiento validado del problema y un Product Backlog priorizado con épicas, historias de usuario y criterios de aceptación, más la definición del marco de trabajo del equipo.

La Iteración 0 **no** incluye prototipos ni frontend: eso corresponde a las Iteraciones 1 y 2. Los artefactos de descubrimiento se redactaron antes de hablar con usuarios, por eso todo lo que requiere evidencia está marcado como **hipótesis a validar**. Las entrevistas planificadas ([guion](01-descubrimiento/guion-entrevistas.md)) son el primer paso para contrastarlas; los tests de prototipos, el segundo.

## 1.1 Marco de trabajo

Scrum adaptado a un equipo de 3 personas con 5 h-persona/semana cada una (**30 h-persona por sprint** de 2 semanas). Los tres integrantes forman el Development Team; PO y SM se ejercen en adición al desarrollo.

| Rol | Integrante |
|---|---|
| Product Owner | [COMPLETAR] |
| Scrum Master | [COMPLETAR] |
| Development Team | Los tres integrantes |

Adaptaciones principales: dailies [COMPLETAR frecuencia/modalidad], PO interno que representa al usuario con evidencia de entrevistas y tests, incremento de la It. 0 = artefactos de descubrimiento. Incluye **Definition of Ready**, **Definition of Done** (con los RNF del PDF), políticas de branching/PR y calendario de eventos.

📄 Detalle: [marco-de-trabajo.md](00-marco-de-trabajo/marco-de-trabajo.md).

## 2. Contexto del producto

El proyecto consiste en descubrir, idear, prototipar e implementar el frontend del MVP de una **aplicación móvil de carga para vehículos eléctricos** que vincula a:

- **Anfitriones:** personas con un punto de carga en su casa, o administradores de edificios con cocheras, que quieren ofrecerlo.
- **Conductores:** personas con vehículo eléctrico que necesitan cargar fuera de su casa.

El MVP está dirigido **principalmente a conductores sin punto de carga propio** (viven en un apartamento sin cochera o su cochera no tiene instalación). Existe además un perfil **Administrador** que modera la plataforma.

## 3. Problema identificado

> Los conductores de vehículos eléctricos que no pueden cargar en su domicilio no tienen una forma de acceder a cargadores privados cercanos, en una franja asegurada, sabiendo antes de ir si el conector es compatible y cuánto les va a llevar y costar la carga. A la vez, quienes tienen un cargador no tienen un canal ordenado para ofrecerlo bajo sus propias condiciones.

- **Contexto con fuentes:** unos 5.950 vehículos eléctricos y unos 460 puntos de carga públicos en Uruguay; el 88 % de los vehículos está al sur del Río Negro. En 2025, uno de cada cinco 0 km vendidos fue eléctrico, y en 2026 la carga en la red pública subió cerca de un 56 % con el fin de los subsidios.
- **Situación actual:** red pública de UTE (disponibilidad en el momento, sin reserva según las fuentes), redes privadas (eOne, EVE), mapas colaborativos y acuerdos informales (hipótesis).
- **Oportunidad:** entre las soluciones que relevamos en Uruguay no encontramos un marketplace de cargadores residenciales con reserva.

**Visión:** para conductores sin carga domiciliaria, una app móvil que muestra solo los cargadores de particulares compatibles con su vehículo y disponibles en la franja elegida, con tiempo y costo estimados, y que permite reservarlos.

📄 Detalle: [problema.md](01-descubrimiento/problema.md) (incluye visión, propuesta de valor y supuestos S1–S8).

## 4. Stakeholders

| Stakeholder | Tipo | Rol en el producto |
|---|---|---|
| Conductor | Primario (PDF) | Usuario principal del MVP: busca, compara y reserva. |
| Anfitrión (propietario / administrador de edificio) | Primario (PDF) | Crea la oferta: publica punto, condiciones y agenda. |
| Administrador | Primario (PDF) | Modera: bajas, arbitraje, reportes, alta de administradores. |
| Comunidad de usuarios | Secundario | Genera evaluaciones y reportes. |
| Copropietarios de edificios | Secundario | Afectados por el acceso de terceros a cocheras. |
| Conductores potenciales | Secundario | Base del RNF de usabilidad para novatos. |

Además, se presenta una **lista de 30 funcionalidades por interesado** (F01–F30), cada una con su origen (PDF o propuesta) y sus historias.

📄 Detalle: [interesados.md](01-descubrimiento/interesados.md).

## 5. Personas

Son **personas hipotéticas iniciales**: no provienen de entrevistas.

| Persona | Perfil | Rasgo clave |
|---|---|---|
| Lucía, 34 | Conductora sin cochera | Planifica y compara precios. |
| Martín, 61 | Conductor novato | No conoce conectores (RNF de usabilidad). |
| Andrés, 45 | Anfitrión propietario | Quiere ingreso extra sin perder el control de su casa. |
| Carolina, 52 | Anfitriona administradora de edificio | Varios puntos; rinde cuentas a la comisión. |
| Sofía, 29 | Administradora | Modera reportes y evaluaciones. |

De las personas se derivan **8 hipótesis (H1–H8)**; al diseñar las entrevistas se sumaron **H9** (la carga es un problema recurrente) y **H10** (la barrera del anfitrión es la desconfianza, no el precio). El registro tiene una columna *Resultado* que se completa con las entrevistas y los tests.

📄 Detalle: [personas.md](01-descubrimiento/personas.md) · Guion de entrevistas: [guion-entrevistas.md](01-descubrimiento/guion-entrevistas.md).

## 6. Escenarios

| # | Escenario | Actor principal |
|---|---|---|
| E1 | Un conductor necesita cargar (alta y vehículo) | Conductor |
| E2 | Busca un punto compatible y disponible | Conductor |
| E3 | Compara tiempo y costo | Conductor |
| E4 | Realiza una reserva | Conductor |
| E5 | El anfitrión publica un punto | Anfitrión |
| E6 | El anfitrión administra su disponibilidad | Anfitrión |
| E7 | Cancelación/modificación con notificaciones | Conductor y anfitrión |
| E8 | El administrador gestiona una incidencia | Administrador |
| E9 | El anfitrión revisa su actividad (complementario) | Anfitrión |

Cada escenario detalla actor, situación, objetivo, flujo principal y alternativo, problema, valor de negocio e historias. El valor de negocio por escenario y por épica está en [valor-negocio.md](01-descubrimiento/valor-negocio.md).

📄 Detalle: [escenarios.md](01-descubrimiento/escenarios.md).

## 7. Análisis de competidores

Analizamos 6 soluciones a partir de fuentes públicas, separando **hecho observado**, **interpretación nuestra** y **oportunidad**:

| Solución | Mercado | Categoría |
|---|---|---|
| UTE Mueve | Uruguay | Red pública de carga |
| eOne | Uruguay | Red privada ultrarrápida |
| PlugShare | Global | Mapa colaborativo |
| Electromaps | Europa | Mapa + pago + cargadores privados |
| EVmatch | EE. UU. | Carga entre particulares con reserva |
| Co Charger | Reino Unido | Carga entre vecinos |

📄 Detalle y tabla comparativa: [analisis-competidores.md](02-competidores/analisis-competidores.md).

## 8. Insights

- **Patrones:** mapa y filtros por conector y potencia; registro del vehículo para personalizar; reseñas de la comunidad; en las plataformas entre particulares, el anfitrión controla precio y horarios.
- **Problemas observados:** ninguna fuente muestra el **costo total estimado antes de reservar** para el vehículo del usuario; las redes locales muestran disponibilidad **del momento**, no de una franja futura; hay críticas por **datos colaborativos no verificados**; fijar la **tarifa** es difícil para un particular.
- **Diferenciación:** combinar compatibilidad automática, estimación de tiempo y costo y reserva de cargadores residenciales, pensado para usuarios novatos y en el mercado uruguayo. No incorporamos funcionalidades solo porque un competidor las tenga.

📄 Detalle: [analisis-competidores.md §6](02-competidores/analisis-competidores.md#6-insights).

## 9. Story Map

Hay un mapa por perfil, con backbone, tareas, historias y cortes de release:

- **Conductor:** Acceder → Preparar vehículo → Buscar carga → Elegir punto → Reservar → Gestionar reserva → Después de cargar.
- **Anfitrión:** Acceder → Publicar punto → Definir disponibilidad → Atender reservas → Revisar actividad.
- **Administrador:** Acceder → Gestionar administradores → Moderar.

📄 Detalle: [story-map.md](03-story-map/story-map.md) (incluye verificación historia por historia contra el backlog).

## 10. Product Backlog

**8 épicas · 30 historias · 77 puntos**, todas con criterios de aceptación en formato *Dado / Cuando / Entonces*, estimación, dependencias y release tentativo.

| Épica | Historias |
|---|---|
| EP01 Autenticación y cuenta | US-01 – US-05 |
| EP02 Gestión del punto de carga (anfitrión) | US-06 – US-11 |
| EP03 Vehículos | US-12, US-13 |
| EP04 Búsqueda y estimación | US-14 – US-17 |
| EP05 Reservas | US-18 – US-20 |
| EP06 Notificaciones | US-24 – US-26 |
| EP07 Evaluaciones y reportes | US-21 – US-23 |
| EP08 Administración | US-27 – US-30 |

Los 4 requerimientos no funcionales del PDF (RNF-01 a RNF-04) se registran como restricciones transversales e integran la Definition of Done. Las historias con incertidumbre alta se acompañan de **spikes** con timebox (SPK-01 presentación de tiempo y costo, SPK-02 zona, SPK-03 franjas nocturnas).

📄 Detalle: [product-backlog.md](04-product-backlog/product-backlog.md) · [historias-usuario.md](04-product-backlog/historias-usuario.md) · [spikes](04-product-backlog/product-backlog.md#7-historias-con-incertidumbre-spikes).

## 11. Priorización

Usamos **MoSCoW**, orientado a validar la propuesta de valor en el primer ciclo:

| Prioridad | Historias | Puntos | Destino |
|---|:-:|:-:|---|
| Must | 12 | 37 | MVP — Iteración 1 |
| Should | 12 | 25 | Iteración 2 |
| Could | 6 | 15 | Iteración 2 |
| Won't (por ahora) | 9 ideas (W-01–W-09) | — | Fuera del PDF |

**Ninguna funcionalidad del PDF está en Won't Have.** *Should* y *Could* indican orden, no exclusión.

📄 Detalle y justificación por historia: [priorizacion-prototipos.md](05-priorizacion/priorizacion-prototipos.md).

## 12. Prototipos priorizados

| Prioridad | Prototipo | Usuario | Iteración |
|:-:|---|---|:-:|
| 1 | P1 — Buscar carga compatible y comparar | Conductor | 1 |
| 2 | P2 — Reservar y ver mis reservas | Conductor | 1 |
| 3 | P3 — Primer ingreso: registro, login y vehículo | Conductor / Anfitrión | 1 |
| 4 | P4 — Publicar un punto de carga | Anfitrión | 1 |
| 5 | P5 — Gestionar la agenda de disponibilidad | Anfitrión | 1 / 2 |
| 6 | P6 — Cancelaciones, cambios y notificaciones | Conductor y anfitrión | 2 |
| 7 | P7 — Evaluaciones e historial | Conductor y anfitrión | 2 |
| 8 | P8 — Moderación | Administrador | 2 |
| 9 | P9 — Gestión de cuenta y ayuda de conectores | Todos | 2 |

📄 Detalle (problema, historias, valor, motivo y plan de validación): [priorizacion-prototipos.md §4](05-priorizacion/priorizacion-prototipos.md#4-priorización-de-prototipos).

## 13. MVP inicial

El **MVP** es la menor versión que permite comprobar si un conductor sin carga domiciliaria encuentra, entiende y reserva un punto de un anfitrión. **No es "todas las funcionalidades del PDF".**

```text
Anfitrión:  registrarse → iniciar sesión → registrar punto → publicar condiciones → cargar agenda
Conductor:  registrarse → iniciar sesión → registrar vehículo → buscar (zona, día, franja, nivel)
            → ver solo compatibles y disponibles con tiempo y costo → ver detalle → reservar → ver mis reservas
```

Historias del MVP: US-01, US-02, US-06, US-07, US-08, US-12, US-14, US-15, US-16, US-17, US-18, US-20. El resto de las funcionalidades del PDF forma el backlog de la Iteración 2.

📄 Detalle: [priorizacion-prototipos.md §3](05-priorizacion/priorizacion-prototipos.md#3-definición-del-mvp).

## 14. Trazabilidad

Resumen **Problema → Usuario → Escenario → Épica → Historia → Prototipo** (matriz completa en [priorizacion-prototipos.md §5](05-priorizacion/priorizacion-prototipos.md#5-matriz-de-trazabilidad)):

| Problema | Usuario | Escenario | Épica | Historia | Prototipo |
|---|---|---|---|---|---|
| PR1 Carga incierta | Conductor | E1 | EP01, EP03 | US-01, US-02, US-12 | P3 |
| PR1 Carga incierta | Conductor | E2, E3 | EP04 | US-14 – US-17 | P1 |
| PR1 Carga incierta | Conductor | E4 | EP05 | US-18, US-20 | P2 |
| PR2 Sin canal de oferta | Anfitrión | E5 | EP02 | US-06, US-07 | P4 |
| PR2 Sin canal de oferta | Anfitrión | E6 | EP02 | US-08, US-10 | P5 |
| PR1 / PR2 | Conductor, Anfitrión | E7 | EP02, EP05, EP06 | US-09, US-19, US-24 – US-26 | P6 |
| PR2 / PR3 | Anfitrión, Conductor | E8, E9 | EP02, EP07 | US-11, US-21, US-22 | P7 |
| PR3 Confianza | Administrador, usuarios | E8 | EP07, EP08 | US-23, US-27 – US-30 | P8 |
| PR1 (novatos) / cuenta | Todos | E1 | EP01, EP03 | US-03 – US-05, US-13 | P9 |

## 14.1 Planificación, seguimiento e inspección del sprint

| Aspecto | Resumen | Detalle |
|---|---|---|
| Planificación | Capacidad de 30 h-persona; velocidad no disponible (primera iteración), se planifica por horas. Sprint Backlog con 14 tareas (T1–T14) vinculadas a cada artefacto. | [sprint-planning.md](06-gestion-del-sprint/sprint-planning.md) |
| Dailies | [COMPLETAR frecuencia]; registro escrito con impedimentos. | [dailies.md](06-gestion-del-sprint/dailies.md) |
| Seguimiento | Registro de horas por integrante y burndown en horas. | [seguimiento.md](06-gestion-del-sprint/seguimiento.md) |
| Sprint Review | ¿Se cumplió el objetivo? [COMPLETAR] | [sprint-review.md](06-gestion-del-sprint/sprint-review.md) |
| Retrospectiva | Acciones de mejora para la Iteración 1: [COMPLETAR] | [retrospectiva.md](06-gestion-del-sprint/retrospectiva.md) |

## 15. Conclusiones de la Iteración 0

1. **El problema está acotado y es comprobable:** no es "mejorar la movilidad eléctrica", sino la incertidumbre de un segmento concreto (conductores sin carga domiciliaria) para asegurar una carga compatible con costo conocido, y la falta de canal para anfitriones.
2. **La diferenciación surge del análisis de mercado:** cada funcionalidad existe en algún competidor, pero no encontramos la combinación *compatibilidad + estimación + reserva de cargadores residenciales* en Uruguay.
3. **El backlog cubre el 100 % de los requisitos del PDF** ([tabla de cobertura](04-product-backlog/product-backlog.md#6-cobertura-del-pdf)) y agrega 4 historias propuestas, necesarias para completarlos (US-10, US-13, US-17, US-20) y una como origen de los reportes (US-23).
4. **El MVP es deliberadamente pequeño** (12 historias) para validar primero las hipótesis más riesgosas (H1, H2, H4, H7).
5. **Toda la evidencia de usuarios está pendiente:** personas, frustraciones y valor son hipótesis. La primera tarea de la Iteración 1 es validarlas con los prototipos P1–P5.

### Decisiones tomadas y pendientes

**Resueltas**

| # | Decisión | Resolución | Dónde impacta |
|---|---|---|---|
| D2 | ¿Un mismo usuario puede tener ambos perfiles (anfitrión y conductor)? | **Sí.** En el registro se elige uno o ambos perfiles, se puede agregar el otro después y en el login se elige con cuál se ingresa. Un usuario no puede reservar sus propios puntos. | US-01, US-02, US-05, US-18 |
| D3 | Estimación de la carga: ¿hasta el 100 % y sin pérdidas? | **Sí**, como en el ejemplo del PDF (supuestos S1–S4 confirmados). | US-16 |
| D4 | ¿"300 puntos de carga" es un límite o una capacidad mínima? | **Límite máximo.** No se permite registrar el punto 301 y se informa al anfitrión. | US-06, RNF-01 |

**Recomendación del equipo (a validar con el profesor)**

| # | Decisión | Recomendación | Alternativas consideradas |
|---|---|---|---|
| D1 | Herramienta de prototipado y de frontend (el PDF indica que es "de herramienta libre a validar con el profesor"). | **Prototipos:** papel para las primeras ideas (Crazy 8s) y **Figma** para wireframes y prototipos navegables, exportados a PNG para el repositorio. **Frontend:** **React Native con Expo (TypeScript)**, con datos simulados en el dispositivo y notificaciones locales para el recordatorio de 30 minutos. | Penpot o Balsamiq (prototipos); Flutter, Kotlin + Jetpack Compose o Ionic (frontend). |

**Pendientes**

| # | Decisión | Propuesta del equipo | Dónde impacta |
|---|---|---|---|
| D5 | Pago dentro de la app. | Fuera del MVP (S6). | Backlog W-01 |
| D6 | Definición de "sesión realizada" para el historial. | Reserva no cancelada cuya franja terminó (S7). | US-11 |
| D7 | ¿La modificación de una franja por el anfitrión requiere aceptación del conductor? | Se aplica y se notifica; el conductor puede cancelar. | US-09, US-24 |
| D8 | Representación de la "zona" en la búsqueda. | Explorar alternativas en P1. | US-14 |
| D9 | Reservas futuras de un usuario dado de baja; recordatorio si se reserva con menos de 30 minutos de anticipación. | A definir. | US-28, US-26 |
| D10 | ¿Se permiten franjas que cruzan la medianoche (ej. 22:00–06:00)? Es el caso típico de carga nocturna para quien no tiene cochera, pero US-08 CA2 hoy lo rechaza. | Explorar en P5 y con las entrevistas (SPK-03). | US-08, US-14, US-18 |

## 16. Fuentes utilizadas

- **Fuente principal:** *Mini-proyecto ágil — ISA1, semestre 2, 2026* (PDF oficial del obligatorio).
- **Mercado y competidores:** UTE (carga de vehículos, UTE Mueve, llamado 2026), MIEM (EVE-APP), autoencuotas.com (datos de Uruguay 2026), La Tribuna y Ámbito (ventas 2025 y tarifas de carga 2026), App Store y Google Play (UTE Mueve, eOne, PlugShare, Electromaps, EVmatch, Co Charger), sitios oficiales de EVmatch, Co Charger y Electromaps, Blink Charging, Charged EVs y Buscatucoche. Enlaces completos en [analisis-competidores.md §7](02-competidores/analisis-competidores.md#7-fuentes).
- **Técnicas:** User Story Mapping (J. Patton), MoSCoW, formato de visión de producto (G. Moore), historias de usuario con criterios *Dado/Cuando/Entonces*, Guía de Scrum.

---

## Checklist de cumplimiento de la rúbrica — Iteración 0

Leyenda: ✅ completo · ⏳ estructura lista, falta completar con datos del equipo

| Criterio | Evidencia | Archivo | Estado |
|---|---|---|:-:|
| Identificación de interesados | 3 interesados primarios y 3 secundarios justificados, con tabla de necesidades, problemas, objetivos, funcionalidades y valor | [interesados.md](01-descubrimiento/interesados.md) | ✅ |
| Funcionalidades por interesado | Matriz F01–F30 × perfil, con origen e historias | [interesados.md §5](01-descubrimiento/interesados.md#5-funcionalidades-por-interesado) | ✅ |
| Estudio de competidores | 6 soluciones con ficha (hecho / interpretación / oportunidad), tabla comparativa, insights y fuentes | [analisis-competidores.md](02-competidores/analisis-competidores.md) | ✅ |
| Problema de negocio | Problema, usuarios afectados, situación actual, consecuencias, oportunidad, visión y propuesta de valor | [problema.md](01-descubrimiento/problema.md) | ✅ |
| Identificación de usuarios | 3 perfiles del PDF + 5 personas hipotéticas + registro de hipótesis | [personas.md](01-descubrimiento/personas.md) | ✅ |
| Escenarios | 8 escenarios pedidos + 1 complementario, con flujo y valor | [escenarios.md](01-descubrimiento/escenarios.md) | ✅ |
| Valor de negocio asociado | Valor por escenario y por épica; indicadores para validar | [valor-negocio.md](01-descubrimiento/valor-negocio.md) | ✅ |
| Story Map | Mapa por perfil: backbone, tareas, historias, cortes R1/R2/Posterior | [story-map.md](03-story-map/story-map.md) | ✅ |
| Product Backlog | 30 historias ordenadas con valor, prioridad, estimación, dependencias y release | [product-backlog.md](04-product-backlog/product-backlog.md) | ✅ |
| Épicas | 8 épicas justificadas, con jerarquía | [product-backlog.md §2](04-product-backlog/product-backlog.md#2-jerarquía-de-épicas) | ✅ |
| Historias de usuario | Formato *Como / quiero / para*, con actor y origen | [historias-usuario.md](04-product-backlog/historias-usuario.md) | ✅ |
| Criterios de aceptación | Entre 2 y 8 criterios verificables por historia (*Dado / Cuando / Entonces*) | [historias-usuario.md](04-product-backlog/historias-usuario.md) | ✅ |
| Priorización | MoSCoW con justificación por historia; MVP definido | [priorizacion-prototipos.md](05-priorizacion/priorizacion-prototipos.md) | ✅ |
| Prototipos priorizados | 9 prototipos con usuario, problema, historias, valor, motivo, iteración y plan de validación | [priorizacion-prototipos.md §4](05-priorizacion/priorizacion-prototipos.md#4-priorización-de-prototipos) | ✅ |
| Trazabilidad | Matriz Problema → Usuario → Escenario → Épica → Historia → Prototipo | [priorizacion-prototipos.md §5](05-priorizacion/priorizacion-prototipos.md#5-matriz-de-trazabilidad) | ✅ |

### Rúbrica general del proyecto (evidencia de esta iteración)

| Criterio | Evidencia | Archivo | Estado |
|---|---|---|:-:|
| Definición del marco de trabajo | Roles por integrante, justificación de la adaptación, DoR, DoD, políticas y eventos | [marco-de-trabajo.md](00-marco-de-trabajo/marco-de-trabajo.md) | ⏳ |
| Planificación de la iteración | Sprint Goal, capacidad, Sprint Backlog con tareas y estimaciones | [sprint-planning.md](06-gestion-del-sprint/sprint-planning.md) | ⏳ |
| Seguimiento de la iteración | Dailies, registro de horas por integrante, burndown | [dailies.md](06-gestion-del-sprint/dailies.md) · [seguimiento.md](06-gestion-del-sprint/seguimiento.md) | ⏳ |
| Inspección y adaptación del proceso | Sprint Review y retrospectiva con acciones de mejora | [sprint-review.md](06-gestion-del-sprint/sprint-review.md) · [retrospectiva.md](06-gestion-del-sprint/retrospectiva.md) | ⏳ |
| Repositorio | Branching, PRs revisados por otro integrante, merge a `main` al cierre | [marco-de-trabajo.md §5](00-marco-de-trabajo/marco-de-trabajo.md#5-políticas-de-trabajo-y-repositorio) | ⏳ |

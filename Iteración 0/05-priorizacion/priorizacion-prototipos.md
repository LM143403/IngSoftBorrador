# Priorización del backlog, MVP y prototipos

> Documento de la Iteración 0 · [Volver al README](../README.md)

## 1. Técnica de priorización: MoSCoW

Priorizamos con **MoSCoW**, aplicado a la pregunta *"¿qué hace falta para validar la propuesta de valor en el primer ciclo de descubrimiento?"*. Las categorías significan:

| Categoría | Significado en este proyecto |
|---|---|
| **Must Have** | Sin esto no se puede validar el recorrido central *publicar punto → buscar → comparar → reservar*. Forma parte del **MVP** y se prototipa en la **Iteración 1**. |
| **Should Have** | Obligatorio según el PDF y de valor alto o medio, pero el recorrido central se puede validar sin él. Se prototipa en la **Iteración 2**. |
| **Could Have** | Obligatorio según el PDF, con valor que crece con la escala (moderación) o complementario. Se prototipa en la **Iteración 2**, primero a nivel de wireframe si la capacidad es limitada. |
| **Won't Have (por ahora)** | Ideas que **no están en el PDF**. Quedan registradas en el backlog, sin comprometer. |

> **Importante:** ninguna funcionalidad del PDF está en *Won't Have*. *Should* y *Could* indican **orden**, no exclusión: todas las funcionalidades del PDF siguen en el Product Backlog y está previsto cubrirlas en la Iteración 2.

Criterios que usamos para decidir, en este orden:

1. **Riesgo de la hipótesis que valida** (H1, H2, H4 primero; ver [personas](../01-descubrimiento/personas.md#registro-de-hipótesis-derivadas-de-las-personas)).
2. **Valor de negocio** ([valor-negocio.md](../01-descubrimiento/valor-negocio.md)).
3. **Dependencias**: una historia no puede ir antes de aquello de lo que depende.
4. **Esfuerzo** estimado, como criterio de desempate.

## 2. Clasificación y justificación

### 2.1 Must Have (MVP — Iteración 1)

| Historia | Por qué es Must |
|---|---|
| US-01 Registrar usuario con perfil | Habilitante: sin cuenta no hay perfiles ni datos propios. |
| US-02 Iniciar sesión eligiendo perfil | Habilitante: separa los recorridos de conductor y anfitrión, que es la base del modelo de dos lados. |
| US-06 Registrar punto de carga | Sin puntos no hay resultados: la búsqueda no tendría qué mostrar. |
| US-07 Publicar condiciones | La tarifa y la potencia son insumos de la estimación (US-16), que es el diferencial. |
| US-08 Gestionar agenda | La disponibilidad que filtra US-15 sale de la agenda. |
| US-12 Registrar vehículo | La compatibilidad y la estimación dependen del conector y la batería. |
| US-14 Buscar por zona, día, franja y nivel | Núcleo de la propuesta de valor (hipótesis H1). |
| US-15 Solo compatibles y disponibles | Responde a la frustración principal del conductor (hipótesis H4). |
| US-16 Tiempo y costo estimados | Diferencial frente a los competidores relevados (hipótesis H2). |
| US-17 Detalle del punto | Sin ver condiciones no se puede decidir ni reservar. |
| US-18 Reservar franja | Es la transacción que cierra el recorrido. |
| US-20 Ver mis reservas | Permite al conductor comprobar que reservó y acceder a las instrucciones; cierra el recorrido del MVP. |

### 2.2 Should Have (Iteración 2)

| Historia | Por qué es Should y no Must |
|---|---|
| US-10 Reservas recibidas | Muy útil para el anfitrión, pero la reserva se puede validar desde el lado del conductor. Es la base de US-09. |
| US-19 Cancelar reserva | Obligatoria (PDF); requiere que existan reservas (R1). |
| US-25 Aviso al anfitrión por cancelación | Obligatoria (PDF); depende de US-19. |
| US-09 Cancelar/modificar franja agendada | Obligatoria (PDF); depende de US-10 y US-18. |
| US-24 Aviso al conductor por cambio | Obligatoria (PDF); depende de US-09. |
| US-26 Recordatorio 30 min | Obligatoria (PDF); no condiciona la validación de la búsqueda y la reserva. |
| US-13 Ayuda de conectores | Aporta al RNF de usabilidad. La dejamos para la Iteración 2 para **medir primero** en la Iteración 1 si los usuarios eligen mal el conector sin ayuda (H4). |
| US-03 Recuperar contraseña | Obligatoria (PDF); no aporta a la validación de la propuesta de valor. |
| US-04 Cerrar sesión | Obligatoria (PDF); esfuerzo mínimo. |
| US-05 Editar usuario | Obligatoria (PDF); no condiciona la validación. |
| US-21 Evaluar punto | Obligatoria (PDF); requiere sesiones realizadas. Primera pieza de la reputación. |
| US-11 Historial e ingreso acumulado | Obligatoria (PDF); motiva al anfitrión (H5, H8), pero requiere sesiones realizadas. |

### 2.3 Could Have (Iteración 2, primero como wireframe si hace falta)

| Historia | Por qué es Could |
|---|---|
| US-22 Evaluar conductor | Obligatoria (PDF). Tiene menor impacto que la evaluación del punto en la decisión del usuario principal (el conductor). |
| US-23 Reportar problema | Propuesta, necesaria como origen de los reportes del PDF. Valor a mayor escala. |
| US-30 Gestionar reportes | Obligatoria (PDF). La moderación es crítica con muchos usuarios, pero no en un prototipo de validación. |
| US-29 Arbitrar evaluaciones | Obligatoria (PDF). Depende de que existan evaluaciones de ambos lados. |
| US-28 Baja de usuarios | Obligatoria (PDF). Mismo razonamiento que US-30. |
| US-27 Alta de administrador | Obligatoria (PDF). Pocos usuarios la usan y tiene bajo riesgo de diseño. |

### 2.4 Won't Have (por ahora)

Ver el listado W-01 a W-09 en el [Product Backlog §5](../04-product-backlog/product-backlog.md#5-backlog-fuera-del-alcance-actual-wont-have-por-ahora). Resumen: pago en la app, disponibilidad en tiempo real, mapa con geolocalización, varios vehículos, reservas recurrentes, aprobación manual de reservas, calculadora de tarifa, chat y favoritos.

## 3. Definición del MVP

En este proyecto, **MVP** no significa "todas las funcionalidades del PDF". Significa **la menor versión del producto que permite comprobar si la propuesta de valor central resuelve el problema**, es decir, si un conductor sin carga en su domicilio encuentra, entiende y reserva un punto de un anfitrión.

### 3.1 MVP / primera experiencia a validar (Release 1 — Iteración 1)

**Recorrido que el MVP tiene que permitir de punta a punta:**

1. Un **anfitrión** se registra, publica su punto con condiciones y carga su agenda. *(US-01, US-02, US-06, US-07, US-08)*
2. Un **conductor** se registra, registra su vehículo y busca indicando zona, día, franja y nivel de batería. *(US-01, US-02, US-12, US-14)*
3. Ve **solo** puntos compatibles y disponibles, con **tiempo y costo estimados**, y consulta el detalle. *(US-15, US-16, US-17)*
4. **Reserva** una franja y la ve en "Mis reservas". *(US-18, US-20)*

**Qué queremos aprender con el MVP:**

| Hipótesis | Pregunta concreta |
|---|---|
| H1 | ¿Los conductores sin cochera usarían la reserva de un cargador particular? |
| H2 | ¿El tiempo y el costo estimados influyen en qué punto eligen? |
| H4 | ¿Pueden registrar su conector correctamente sin ayuda? |
| H7 | ¿Completan buscar → reservar sin asistencia, en distintas edades? |

### 3.2 Product Backlog posterior (Release 2 — Iteración 2)

Todo el resto de las funcionalidades del PDF: gestión de cuenta (US-03, US-04, US-05), ayuda de conectores (US-13), gestión de reservas y notificaciones (US-09, US-10, US-19, US-24, US-25, US-26), evaluaciones, reportes e historial (US-11, US-21, US-22, US-23) y administración (US-27 a US-30). A esto se suman los **cambios de requerimientos** que el PDF anticipa para la Iteración 2.

## 4. Priorización de prototipos

La rúbrica pide *"una priorización de los prototipos principales que se buscarán idear, construir y validar como parte del ciclo de descubrimiento"*. Definimos los prototipos como **flujos completos de pantallas**, no pantallas sueltas, porque lo que queremos validar son recorridos.

Las técnicas (*Crazy 8s, wireframing, paper prototyping*) son las sugeridas por la rúbrica para las Iteraciones 1 y 2. En esta iteración **solo las asignamos**; no hicimos ningún prototipo todavía.

| Prioridad | Prototipo | Usuario | Problema que resuelve | Historias | Valor esperado | Motivo de la prioridad | Iteración | Técnica sugerida |
|:-:|---|---|---|---|---|---|:-:|---|
| **1** | **P1 — Buscar carga compatible y comparar** | Conductor | No saber qué puntos le sirven ni cuánto le van a costar. | US-14, US-15, US-16, US-17 | Alto | Contiene el diferencial del producto y valida las hipótesis más riesgosas (H1, H2). Si falla, hay que replantear el producto. | 1 | Crazy 8s para explorar alternativas de listado (lista vs. tarjetas vs. mapa) → wireframe → test |
| **2** | **P2 — Reservar y ver mis reservas** | Conductor | Falta de certeza de encontrar el punto libre. | US-18, US-20 | Alto | Cierra el recorrido del MVP; sin él no se puede medir "buscar → reservar" (H7). | 1 | Wireframe → prototipo navegable |
| **3** | **P3 — Primer ingreso: registro, login con perfil y vehículo** | Conductor (y anfitrión en registro/login) | Barrera de entrada y desconocimiento técnico. | US-01, US-02, US-12 | Alto | Habilitante del MVP; permite medir si el usuario identifica su conector (H4). | 1 | Paper prototyping (rápido de iterar) |
| **4** | **P4 — Publicar un punto de carga** | Anfitrión | Falta de un canal para ofrecer el cargador con condiciones propias. | US-06, US-07 | Alto | Crea la oferta que alimenta P1; valida si el anfitrión entiende qué se le pide (H3). | 1 | Wireframe |
| **5** | **P5 — Gestionar la agenda de disponibilidad** | Anfitrión | Control sobre cuándo ofrecer el punto. | US-08, US-10 | Alto | Must en R1 (US-08). Cargar franjas por día es la interacción más compleja del anfitrión y conviene probarla temprano. US-10 se agrega en la Iteración 2. | 1 (US-08) / 2 (US-10) | Crazy 8s (calendario vs. lista por día) → wireframe |
| **6** | **P6 — Cancelaciones, cambios y notificaciones** | Conductor y anfitrión | Viajes en vano y franjas perdidas. | US-09, US-19, US-24, US-25, US-26 | Medio-Alto | Obligatorio (PDF), pero requiere reservas existentes (P2). | 2 | Wireframe + storyboard de notificaciones |
| **7** | **P7 — Evaluaciones e historial del anfitrión** | Conductor y anfitrión | Falta de confianza; el anfitrión no ve su beneficio. | US-21, US-22, US-11 | Medio | Requiere sesiones realizadas; aporta confianza y motivación (H5, H8). | 2 | Wireframe |
| **8** | **P8 — Moderación: reportes, arbitraje y bajas** | Administrador (y usuarios al reportar) | Conflictos e incumplimientos. | US-23, US-27, US-28, US-29, US-30 | Medio | Obligatorio (PDF); su valor crece con la escala y tiene menor riesgo de diseño. | 2 | Wireframe |
| **9** | **P9 — Gestión de cuenta y ayuda de conectores** | Todos | Mantener la cuenta y apoyar a usuarios novatos. | US-03, US-04, US-05, US-13 | Medio | Obligatorio (PDF) salvo US-13. US-13 se diseña con lo que se aprenda sobre H4 en P3. | 2 | Wireframe |

**Cobertura:** las 30 historias del backlog están asignadas a algún prototipo.

### 4.1 Cómo se validará cada prototipo (plan, todavía no ejecutado)

| Prototipo | Pregunta de validación | Evidencia que buscamos |
|---|---|---|
| P1 | ¿El usuario entiende por qué ve esos puntos y usa el tiempo y el costo para elegir? | Test de usabilidad con 3–5 personas: tarea "encontrá dónde cargar el martes de noche" + pregunta "¿por qué elegiste ese punto?". |
| P2 | ¿Completa la reserva sin ayuda y sabe dónde verla después? | Tasa de éxito de la tarea; tiempo empleado. |
| P3 | ¿Identifica correctamente su tipo de conector? | % de aciertos (insumo para US-13). |
| P4 / P5 | ¿El anfitrión publica punto y agenda sin dudas sobre tarifa, duración e instrucciones? | Observación + preguntas abiertas. |
| P6 | ¿Los mensajes de notificación son claros y accionables? | Lectura en voz alta de notificaciones de ejemplo. |
| P7 / P8 / P9 | ¿Los criterios de evaluación, estados de reportes y pantallas de cuenta se entienden? | Revisión con usuarios y con el profesor (Sprint Review). |

## 5. Matriz de trazabilidad

Muestra la coherencia **Problema → Usuario → Escenario → Épica → Historia → Prototipo**.

Problemas: **PR1** = el conductor no puede asegurar una carga compatible con costo conocido · **PR2** = el anfitrión no tiene un canal ordenado para ofrecer su cargador · **PR3** = falta de confianza entre desconocidos.

| Problema | Usuario | Escenario | Épica | Historia | Prototipo |
|---|---|---|---|---|---|
| PR1 | Conductor | E1 | EP01 | US-01, US-02 | P3 |
| PR1 | Conductor | E1 | EP03 | US-12 | P3 |
| PR1 | Conductor (novato) | E1 | EP03 | US-13 | P9 |
| PR1 / PR2 | Todos | E1 | EP01 | US-03, US-04, US-05 | P9 |
| PR1 | Conductor | E2 | EP04 | US-14, US-15 | P1 |
| PR1 | Conductor | E3 | EP04 | US-16, US-17 | P1 |
| PR1 | Conductor | E4 | EP05 | US-18, US-20 | P2 |
| PR2 | Anfitrión | E5 | EP02 | US-06, US-07 | P4 |
| PR2 | Anfitrión | E6 | EP02 | US-08, US-10 | P5 |
| PR1 / PR2 | Conductor, Anfitrión | E7 | EP02 | US-09 | P6 |
| PR1 / PR2 | Conductor, Anfitrión | E7 | EP05 | US-19 | P6 |
| PR1 / PR2 | Conductor, Anfitrión | E7 | EP06 | US-24, US-25, US-26 | P6 |
| PR2 | Anfitrión | E9 | EP02 | US-11 | P7 |
| PR3 | Conductor | E8 | EP07 | US-21 | P7 |
| PR3 | Anfitrión | E8 / E9 | EP07 | US-22 | P7 |
| PR3 | Conductor, Anfitrión | E8 | EP07 | US-23 | P8 |
| PR3 | Administrador | E8 | EP08 | US-27, US-28, US-29, US-30 | P8 |

**Verificación:** las 30 historias aparecen en la matriz, todas se asocian a un escenario y a un usuario, y todos los escenarios (E1–E9) y usuarios primarios tienen al menos una historia.

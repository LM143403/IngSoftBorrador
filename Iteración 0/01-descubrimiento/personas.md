# User personas (hipotéticas iniciales)

> Documento de la Iteración 0 · [Volver al README](../README.md)

> ⚠️ **Aclaración metodológica.** Estas personas **no surgen de entrevistas ni encuestas**: se construyeron antes de hacer investigación con usuarios. Son **personas hipotéticas iniciales**. Las entrevistas planificadas ([guion-entrevistas.md](guion-entrevistas.md)) sirven para contrastarlas. Las construimos a partir del PDF del obligatorio, del análisis de competidores y del contexto uruguayo, y sirven para orientar el descubrimiento. Cada rasgo debe validarse (o descartarse) en las Iteraciones 1 y 2. Los nombres son ficticios.

---

## Persona 1 — Conductora sin cochera: "Lucía"

| Atributo | Descripción |
|---|---|
| **Edad aproximada** | 34 años |
| **Contexto** | Vive en un apartamento en Pocitos (Montevideo), sin cochera. Hace 8 meses compró un auto eléctrico usado con batería de unos 40 kWh. Trabaja de forma híbrida. |
| **Objetivos** | Tener el auto cargado para la semana sin depender de la suerte. Saber cuánto gasta en carga. |
| **Frustraciones** | Llegar a un cargador público y encontrarlo ocupado. Cargar en la calle le obliga a quedarse cerca del auto. No sabe bien si "Tipo 2" y "CCS2" son lo mismo. |
| **Necesidades** | Buscar puntos cerca de su casa o de su trabajo, en la noche o en horario laboral. Ver solo los que le sirven. Reservar. |
| **Comportamiento** | Usa el celular para todo. Compara precios. Lee reseñas antes de decidir. Planifica con uno o dos días de anticipación. |
| **Escenario de uso** | El domingo de noche ve que su batería está al 25 %. Abre la app, indica "Pocitos, martes, 19:00–23:00, batería 25 %". Ve tres puntos compatibles con tiempo y costo estimados, elige el más barato que termina antes de las 23:00 y reserva. El martes a las 18:30 recibe el recordatorio. |

**Hipótesis a validar con esta persona:** H1 (reservar le da más tranquilidad que usar la red pública), H2 (valora ver el costo antes de reservar), H4 (no distingue tipos de conector).

---

## Persona 2 — Conductor novato: "Martín"

| Atributo | Descripción |
|---|---|
| **Edad aproximada** | 61 años |
| **Contexto** | Jubilado, vive en un apartamento en Punta del Este. Su hijo le recomendó pasarse a un eléctrico. Todavía está decidiendo. |
| **Objetivos** | Entender si puede tener un auto eléctrico sin cochera propia. |
| **Frustraciones** | La terminología técnica (kW, kWh, CHAdeMO). Las apps con muchas pantallas. |
| **Necesidades** | Una app que le diga claramente "este punto sirve para su auto" y "va a tardar X horas y costar $Y". Letra y botones legibles. |
| **Comportamiento** | Usa WhatsApp y alguna app bancaria. Prefiere pasos guiados. Pide ayuda si algo no es claro. |
| **Escenario de uso** | Registra su vehículo eligiendo marca y modelo. Cuando la app le pide el tipo de conector, usa la ayuda con imágenes para identificarlo. Luego busca y ve que hay dos puntos compatibles en su zona. |

**Hipótesis a validar:** H4 (la ayuda de conectores reduce errores), H7 (el RNF de "rango etario amplio" requiere flujos cortos y guiados).

Esta persona representa directamente el RNF del PDF: *"personas que recién adoptan la movilidad eléctrica y no están familiarizadas con tipos de conectores ni potencias de carga"*.

---

## Persona 3 — Anfitrión propietario: "Andrés"

| Atributo | Descripción |
|---|---|
| **Edad aproximada** | 45 años |
| **Contexto** | Vive en una casa en Carrasco con garaje y cargador de pared de 7 kW. Carga su propio auto de noche. De día el cargador no se usa. |
| **Objetivos** | Recuperar parte de la inversión del cargador con un ingreso extra. |
| **Frustraciones** | Desconfía de que desconocidos entren a su garaje. No quiere estar pendiente del celular. |
| **Necesidades** | Decidir qué franjas ofrece (por ejemplo, días hábiles de 9:00 a 17:00). Fijar su tarifa. Saber quién viene y su reputación. Poder cancelar si surge un imprevisto. |
| **Comportamiento** | Configura una vez y revisa poco. Mira el ingreso acumulado a fin de mes. |
| **Escenario de uso** | Registra su punto (Tipo 2, 7 kW), publica una tarifa de $8/kWh, duración máxima de 4 horas e instrucciones ("tocar timbre, portón lateral"). Carga franjas de lunes a viernes. Un día tiene que viajar y cancela una franja reservada: el conductor recibe la notificación. |

**Hipótesis a validar:** H3 (los anfitriones aceptan recibir desconocidos si ven su reputación), H5 (cubrir el costo de la energía más un margen es suficiente motivación).

---

## Persona 4 — Anfitriona administradora de edificio: "Carolina"

| Atributo | Descripción |
|---|---|
| **Edad aproximada** | 52 años |
| **Contexto** | Administra un edificio en Cordón con cocheras. La comisión instaló dos cargadores compartidos que se usan poco. |
| **Objetivos** | Que los cargadores generen ingresos para gastos comunes, sin conflictos con los vecinos. |
| **Frustraciones** | Coordinar accesos con portería. Reclamos de vecinos. |
| **Necesidades** | Instrucciones de acceso claras. Duración máxima para no bloquear las cocheras. Registro de sesiones para rendir cuentas. |
| **Comportamiento** | Usa la computadora en su trabajo y el celular para lo urgente. Necesita reportes simples. |
| **Escenario de uso** | Registra los dos puntos del edificio con la misma dirección. Publica franjas en horario de portería. A fin de mes revisa el historial de sesiones y el ingreso acumulado para informar a la comisión. |

**Hipótesis a validar:** H6 (los administradores de edificio necesitan gestionar más de un punto), H8 (el historial les sirve para rendir cuentas).

---

## Persona 5 — Administradora de la plataforma: "Sofía"

| Atributo | Descripción |
|---|---|
| **Edad aproximada** | 29 años |
| **Contexto** | Integra el equipo que opera la aplicación. Otra administradora le dio el alta. |
| **Objetivos** | Mantener la confianza entre conductores y anfitriones. |
| **Frustraciones** | Reportes sin contexto. Evaluaciones cruzadas donde cada parte culpa a la otra. |
| **Necesidades** | Una lista de reportes pendientes con su estado. Ver las evaluaciones en disputa con los datos de la reserva. Poder dar de baja a un usuario, dejando registrado el motivo. |
| **Comportamiento** | Revisa la bandeja de reportes a diario. Documenta sus decisiones. |
| **Escenario de uso** | Recibe un reporte de un conductor: el punto de un anfitrión no tenía el conector publicado. Revisa las evaluaciones del punto, contacta al anfitrión y, al ser el tercer reporte, lo da de baja con el motivo "incumplimiento reiterado". |

---

## Registro de hipótesis derivadas de las personas

| ID | Hipótesis | Persona | Cómo se validaría | Resultado |
|---|---|---|---|---|
| H1 | Los conductores sin cochera prefieren reservar un cargador privado antes que depender de la disponibilidad de la red pública. | Lucía | Entrevistas + test del prototipo de búsqueda y reserva. | [COMPLETAR] |
| H2 | Ver el costo y el tiempo estimados **antes** de reservar influye en la elección del punto. | Lucía | Test de usabilidad comparando listados con y sin estimación. | [COMPLETAR] |
| H3 | Los anfitriones aceptan recibir desconocidos si pueden ver su reputación y fijar instrucciones de acceso. | Andrés | Entrevistas con propietarios de cargadores. | [COMPLETAR] |
| H4 | Muchos conductores no saben identificar su tipo de conector. | Martín, Lucía | Test del registro de vehículo, midiendo errores. | [COMPLETAR] |
| H5 | Un ingreso por kWh algo por encima del costo de energía motiva a publicar el cargador. | Andrés | Entrevistas. | [COMPLETAR] |
| H6 | Los administradores de edificio necesitan gestionar varios puntos desde una cuenta. | Carolina | Entrevistas. | [COMPLETAR] |
| H7 | Los usuarios de mayor edad completan los flujos principales si son cortos y guiados. | Martín | Test de usabilidad con participantes de distintas edades. | [COMPLETAR] |
| H8 | El historial e ingreso acumulado es suficiente como reporte para el anfitrión. | Carolina | Revisión del prototipo con anfitriones. | [COMPLETAR] |
| H9 | Un conductor sin punto de carga propio percibe la carga como un problema **recurrente**, no ocasional. | Lucía | Entrevistas a conductores (preguntas 2, 3, 4 y 6 del guion). | [COMPLETAR] |
| H10 | La principal barrera del anfitrión para compartir su cargador es la **desconfianza** (acceso a su casa o edificio), no el precio. | Andrés, Carolina | Entrevistas a anfitriones (preguntas 4 y 7 del guion). | [COMPLETAR] |

H1–H8 surgen de las personas; H9 y H10 se agregaron al diseñar el guion de entrevistas. Las entrevistas (tareas T5–T7 de la [Sprint Planning](../06-gestion-del-sprint/sprint-planning.md)) alimentan la columna *Resultado*; lo que no se valide en la Iteración 0 se valida con los prototipos en las Iteraciones 1 y 2.

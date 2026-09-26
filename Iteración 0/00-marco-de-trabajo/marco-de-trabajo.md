# Definición del marco de trabajo (Scrum adaptado)

> Documento de la Iteración 0 · [Volver al README](../README.md)

Responde al criterio *"Definición del marco de trabajo"* de la rúbrica general del proyecto: marco general de Scrum, roles de cada integrante, políticas de trabajo (DoR y DoD) y justificación de la adaptación al contexto.

> **Nota de uso:** los bloques marcados con `[COMPLETAR]` requieren acuerdos propios del equipo.

## 1. Roles del equipo

| Integrante | Rol Scrum | Responsabilidades asumidas |
| --- | --- | --- |
| [COMPLETAR] | Product Owner | Ordena el Product Backlog, define y comunica el valor, es la voz del usuario, acepta o rechaza las historias contra sus criterios de aceptación. |
| [COMPLETAR] | Scrum Master | Facilita los eventos, cuida los timeboxes, remueve impedimentos, vela por la aplicación del marco y la mejora continua. |
| [COMPLETAR] | Development Team | Construye el incremento, estima, define las tareas y se autoorganiza. |

**Aclaración sobre la adaptación:** los tres integrantes forman parte del Development Team. Los roles de PO y SM se ejercen **en adición** al trabajo de desarrollo, dado el tamaño del equipo y la dedicación disponible (5 h-persona/semana cada uno).

**Rotación de roles:** [COMPLETAR — definir si los roles rotan por iteración o se mantienen fijos, y justificar la decisión.]

## 2. Justificación de la adaptación del marco al contexto

Scrum está pensado para equipos dedicados; este es un equipo universitario de 3 personas con dedicación parcial. Las adaptaciones acordadas:

| Práctica original | Adaptación del equipo | Motivo |
| --- | --- | --- |
| Sprint de 1 a 4 semanas | Sprint de **2 semanas** | Fijado por la letra del obligatorio. |
| Daily Scrum presencial diario de 15 min | **[COMPLETAR: ej. 3 dailies semanales asincrónicos por [herramienta], con registro escrito]** | Con 5 h-persona/semana no hay avance diario significativo; un daily diario sería ceremonia vacía. |
| Equipo dedicado full-time | 5 h-persona/semana por integrante → **30 h-persona por sprint** | Restricción del curso y de la carga académica. |
| PO externo al equipo, representante del negocio | PO interno que **representa** al usuario, apoyado en evidencia de usuarios reales (entrevistas y tests de prototipos) | No hay cliente real; la validación se consigue con usuarios potenciales. |
| Incremento potencialmente entregable en producción | Incremento = artefactos de descubrimiento (It. 0) · prototipo + frontend navegable (It. 1 y 2) | El alcance del proyecto es el frontend de un MVP. |
| Velocidad medida desde el inicio | En la Iteración 0 se planifica por horas; la velocidad de referencia se mide al cierre de la Iteración 1 | No hay historial previo del equipo (ver [Product Backlog §4](../04-product-backlog/product-backlog.md#4-resumen)). |

## 3. Definition of Ready (DoR)

Una historia de usuario está **Ready** para entrar a un sprint cuando:

- [ ] Está escrita en formato narrativo: *Como [rol], quiero [funcionalidad], para [beneficio]*.
- [ ] Tiene criterios de aceptación definidos, claros y testeables (formato *Dado / Cuando / Entonces*, estilo Gherkin).
- [ ] Su valor para el usuario o el negocio está identificado (ver [valor-negocio.md](../01-descubrimiento/valor-negocio.md)).
- [ ] Cumple INVEST: independiente, negociable, valiosa, estimable, pequeña y testeable.
- [ ] Es lo suficientemente chica para completarse dentro de un sprint.
- [ ] Está estimada en story points por el equipo, sin grandes dudas (si hay incertidumbre alta, se separa un *spike*; ver [Product Backlog §7](../04-product-backlog/product-backlog.md#7-historias-con-incertidumbre-spikes)).
- [ ] Sus dependencias con otras historias están identificadas.
- [ ] Las decisiones pendientes que la afectan están resueltas o tienen una propuesta explícita del equipo.
- [ ] Se sabe cómo se va a validar (prototipo, pantalla, flujo; ver [plan de validación](../05-priorizacion/priorizacion-prototipos.md#41-cómo-se-validará-cada-prototipo-plan-todavía-no-ejecutado)).

## 4. Definition of Done (DoD)

Un ítem está **Done** cuando:

- [ ] La funcionalidad está implementada en el frontend o el prototipo, según corresponda.
- [ ] Cumple todos sus criterios de aceptación.
- [ ] Fue revisada por al menos otro integrante del equipo (code review o design review vía Pull Request).
- [ ] El prototipo está exportado en PNG/JPG dentro del repositorio.
- [ ] Respeta los RNF transversales: diseño móvil (RNF-03), guías de interfaz de la plataforma elegida (RNF-04), lenguaje sin jerga técnica no explicada (RNF-02) y funcionamiento con 300 puntos simulados cuando aplica (RNF-01).
- [ ] El código está mergeado a `main` sin conflictos y la aplicación levanta siguiendo el README.
- [ ] La documentación correspondiente (README de la iteración) está actualizada.
- [ ] El PO aceptó la historia en la Sprint Review.

> **Ajuste para la Iteración 0:** como no hay código, un ítem está Done cuando el artefacto documental (análisis, story map, backlog, priorización) está versionado en el repo, revisado por otro integrante vía PR y aceptado por el PO.

## 5. Políticas de trabajo y repositorio

- **Estrategia de branching:** [COMPLETAR — ej. una rama por historia (`feature/US-14-busqueda`) o por artefacto en la It. 0 (`docs/it0-backlog`), PR hacia `develop`, merge a `main` al cierre de cada iteración (la letra exige integrar a `main` al fin de cada iteración).]
- **Pull Requests:** todo PR requiere la aprobación de al menos un integrante distinto del autor.
- **Convención de commits:** [COMPLETAR — ej. `[US-14] descripción breve` o `[IT0] descripción breve`.] Los commits deben reflejar las contribuciones individuales (rúbrica).
- **Canal de comunicación:** [COMPLETAR]
- **Herramienta de gestión del backlog:** [COMPLETAR — ej. GitHub Projects, Trello, Jira.]
- **Registro de horas:** cada integrante registra sus horas en [06-gestion-del-sprint/seguimiento.md](../06-gestion-del-sprint/seguimiento.md), consolidadas en las actas.
- **Herramientas de prototipado y frontend:** recomendación del equipo en la decisión D1 del [README](../README.md#decisiones-tomadas-y-pendientes) (Figma + React Native con Expo), a validar con el profesor.

## 6. Calendario de eventos

| Evento | Frecuencia | Duración | Participantes | Registro |
| --- | --- | --- | --- | --- |
| Sprint Planning | Inicio de cada iteración | [COMPLETAR] | Todo el equipo | [sprint-planning.md](../06-gestion-del-sprint/sprint-planning.md) |
| Daily Scrum | [COMPLETAR] | 15 min | Todo el equipo | [dailies.md](../06-gestion-del-sprint/dailies.md) |
| Backlog Refinement | Mitad del sprint | [COMPLETAR] | Todo el equipo | En el acta del daily correspondiente |
| Sprint Review | Fin de cada iteración | [COMPLETAR] | Equipo + usuarios invitados | [sprint-review.md](../06-gestion-del-sprint/sprint-review.md) |
| Sprint Retrospective | Fin de cada iteración | [COMPLETAR] | Todo el equipo | [retrospectiva.md](../06-gestion-del-sprint/retrospectiva.md) |

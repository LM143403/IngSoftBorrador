# Valor de negocio

> Documento de la Iteración 0 · [Volver al README](../README.md)

## 1. Cómo entendemos el valor en este producto

La aplicación es un **marketplace de dos lados**: vale algo para el conductor solo si hay anfitriones con puntos publicados, y vale algo para el anfitrión solo si hay conductores que reservan. Por eso valoramos cada funcionalidad según tres criterios:

1. **Valor para el conductor** (usuario principal del MVP según el PDF): ¿reduce la incertidumbre de encontrar, elegir y asegurar una carga?
2. **Valor para el anfitrión**: ¿le permite ofrecer su cargador con control y ver el beneficio?
3. **Valor para la plataforma**: ¿sostiene la confianza y el funcionamiento del intercambio?

Usamos una escala cualitativa de **Alto / Medio / Bajo**, que después alimenta la [priorización MoSCoW](../05-priorizacion/priorizacion-prototipos.md).

## 2. Valor por escenario

| Escenario | Conductor | Anfitrión | Plataforma | Valor global | Justificación |
|---|:-:|:-:|:-:|:-:|---|
| [E1](escenarios.md#e1--un-conductor-necesita-cargar-su-vehículo) Alta y vehículo | Medio | — | Alto | **Alto** | Habilitante: sin vehículo registrado no puede calcularse la compatibilidad. |
| [E2](escenarios.md#e2--el-conductor-busca-un-punto-compatible-y-disponible) Búsqueda compatible | Alto | Medio | Alto | **Alto** | Es la propuesta central. Es también lo que genera demanda para el anfitrión. |
| [E3](escenarios.md#e3--el-conductor-compara-tiempo-y-costo) Tiempo y costo | Alto | Bajo | Medio | **Alto** | Diferencial frente a los competidores; ataca las sorpresas de costo. |
| [E4](escenarios.md#e4--el-conductor-realiza-una-reserva) Reserva | Alto | Alto | Alto | **Alto** | Transacción central. |
| [E5](escenarios.md#e5--el-anfitrión-publica-un-punto-de-carga) Publicar punto | Medio | Alto | Alto | **Alto** | Sin oferta no hay resultados. |
| [E6](escenarios.md#e6--el-anfitrión-administra-su-disponibilidad) Disponibilidad | Medio | Alto | Alto | **Alto** | La búsqueda depende de la agenda. |
| [E7](escenarios.md#e7--cancelación-o-modificación-con-notificaciones) Cancelaciones y notificaciones | Alto | Alto | Medio | **Medio-Alto** | Evita viajes inútiles; obligatorio en el PDF, pero presupone reservas existentes. |
| [E8](escenarios.md#e8--el-administrador-gestiona-una-incidencia) Incidencias | Bajo | Bajo | Alto | **Medio** | Crítico a escala; en un prototipo de validación el volumen de conflictos es bajo. |
| [E9](escenarios.md#escenario-complementario-e9--el-anfitrión-revisa-su-actividad) Actividad del anfitrión | — | Medio | Medio | **Medio** | Refuerza la motivación del anfitrión. |

## 3. Valor por épica

| Épica | Valor | Por qué |
|---|:-:|---|
| EP01 Autenticación y cuenta | Alto (habilitante) | Condición para todo lo demás; el PDF exige un acceso "seguro y simplificado para fomentar la retención". |
| EP02 Gestión del punto de carga (anfitrión) | Alto | Crea la oferta; incluye condiciones, agenda, reservas recibidas e historial/ingresos. |
| EP03 Vehículos | Alto (habilitante) | Hace posible la compatibilidad y la estimación. |
| EP04 Búsqueda y estimación | Alto | Núcleo de la propuesta de valor. |
| EP05 Reservas | Alto | Transacción central. |
| EP06 Notificaciones | Medio-Alto | Mantiene a ambas partes sincronizadas. |
| EP07 Evaluaciones y reputación | Medio | Genera confianza a mediano plazo. |
| EP08 Administración | Medio | Moderación; su valor crece con la cantidad de usuarios. |

## 4. Indicadores propuestos para validar valor (Iteraciones 1-2)

> Estos indicadores **todavía no fueron medidos**. Son la forma en que proponemos comprobar las hipótesis durante las pruebas de prototipos. Los umbrales son metas iniciales del equipo, a ajustar.

| Hipótesis | Indicador | Meta inicial |
|---|---|---|
| H2 — La estimación influye en la elección | % de participantes que, en el test, mencionan tiempo o costo como motivo de su elección | ≥ 60 % |
| H4 — Desconocimiento de conectores | % de participantes que eligen correctamente su conector en el registro de vehículo (con ayuda) | ≥ 80 % |
| H7 — Flujos cortos para todas las edades | % que completa "buscar → reservar" sin asistencia | ≥ 80 % |
| H1 — Preferencia por reservar | % de participantes del segmento sin cochera que declara que usaría la reserva | Exploratorio (cualitativo) |
| H3/H5 — Disposición del anfitrión | Cantidad de anfitriones potenciales entrevistados que publicarían su cargador y bajo qué condiciones | Exploratorio (cualitativo) |

## 5. Atributos de calidad (RNF del PDF) y su relación con el valor

| RNF (PDF) | Valor que protege | Cómo se considera en el backlog |
|---|---|---|
| RNF-01 Registro de hasta 300 puntos de carga (límite máximo, D4) | Escalabilidad inicial de la oferta | Restricción aplicada a US-06 (no se permite el punto 301) y US-14 (la búsqueda debe funcionar con 300 puntos). |
| RNF-02 Fácil de usar para un rango etario amplio y usuarios novatos | Adopción | Criterios de aceptación de US-12, US-13, US-14, US-16; hipótesis H4 y H7. |
| RNF-03 Interfaz principalmente móvil (iOS y/o Android) | Uso en movimiento | Todos los prototipos se diseñan para móvil. |
| RNF-04 Seguir las guías de interfaz de cada plataforma | Consistencia y aprendizaje | Parte de la Definition of Done de los prototipos (Iteraciones 1-2). |

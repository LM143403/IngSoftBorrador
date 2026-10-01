# Análisis de competidores y soluciones similares

> Documento de la Iteración 0 · [Volver al README](../README.md#14-estudio-comparativo-de-aplicaciones-similares)

## 1. Objetivo y método

**Objetivo.** Cumplir con el pedido de la letra de que *"la propuesta de valor debe centrarse en analizar ideas, buscar y mejorar aplicaciones ya existentes en el mercado"*, y dejar evidencia de que analizamos y comparamos aplicaciones similares (rúbrica, Iteración 0).

**Método.**

1. Búsqueda web (septiembre de 2026) de soluciones en cuatro categorías: redes de carga en Uruguay, mapas o buscadores de cargadores, reserva de cargadores y plataformas de carga compartida entre particulares.
2. Selección de **6 soluciones**: dos que representan la situación actual en Uruguay, dos mapas colaborativos internacionales y dos plataformas de carga entre particulares, que son el modelo más cercano a nuestro producto.
3. Análisis basado en fuentes públicas: tiendas de aplicaciones, sitios oficiales y notas de prensa. **No instalamos ni usamos las aplicaciones con cuentas reales.** Por eso algunas celdas dicen "no se encontró información", en lugar de suponer.

**Convención de lectura.** Cada ficha separa:

- 🔎 **Hecho observado**: lo que dice una fuente (enlazada en la [sección 7](#7-fuentes)).
- 💭 **Interpretación nuestra**: lo que el equipo deduce. Puede estar equivocado.
- 🎯 **Oportunidad para nuestro producto**: siempre relacionada con el problema de nuestros usuarios, no con "copiar" al competidor.

## 2. Soluciones seleccionadas

| # | Solución | País / mercado | Categoría | Por qué la elegimos |
|---|---|---|---|---|
| C1 | **UTE Mueve** | Uruguay | Red pública de carga | Es la alternativa principal que hoy tiene un conductor uruguayo. |
| C2 | **eOne** | Uruguay | Red privada de carga rápida | Muestra la oferta comercial privada local. |
| C3 | **PlugShare** | Global (fuerte en América del Norte) | Mapa colaborativo | Referente mundial en búsqueda de cargadores y reseñas. |
| C4 | **Electromaps** | Europa (origen España) | Mapa + pago + cargadores privados | App en español con comunidad y opción de compartir cargadores privados con acceso controlado. |
| C5 | **EVmatch** | EE. UU. | Carga entre particulares con reserva | El modelo más parecido al nuestro: anfitriones residenciales y reserva de franja. |
| C6 | **Co Charger** | Reino Unido | Carga entre vecinos | Enfocada exactamente en conductores sin carga domiciliaria, como nuestro MVP. |

También identificamos **EVE-APP** (Uruguay), una red privada que, según el MIEM, ofrece ubicación, precios, estado en tiempo real y **reserva** en los puntos que gestiona. No hacemos una ficha completa porque encontramos solo una fuente, pero la tenemos en cuenta en los insights. En el borrador del equipo también se mencionó **DMC** como operador privado local de carga pública; queda **pendiente de relevar** con fuente antes del informe final. En cualquier caso, estas redes siguen siendo puntos públicos: no resuelven el caso de quien necesita cargar de noche cerca de su casa.

Las [entrevistas](../README.md#13-entrevistas) confirman que la selección representa la situación real: los conductores usan **UTE Mueve** y **PlugShare** ([entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md), [entrevista 2](../entrevistas/transcripciones/entrevista-2-laura.md)) y recurren a las **estaciones de servicio** cuando no tienen dónde cargar, que también consideramos como alternativa en el [análisis de interesados](../README.md#otros-interesados).

## 3. Fichas por competidor

### C1 — UTE Mueve (Uruguay)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 App de UTE para usar la red pública de carga del país. |
| **Público objetivo** | 🔎 Todo conductor de vehículo eléctrico en Uruguay. |
| **Funcionalidades** | 🔎 Ver en tiempo real los puntos de carga de la red, sus características y disponibilidad; ver cuántos cargadores de cada estación están libres u ocupados. 🔎 Iniciar la carga escaneando el código QR del cargador y pagar con una tarjeta de crédito o débito asociada (también existe una tarjeta de carga UTE). |
| **Búsqueda** | 🔎 Mapa de puntos de la red. No encontramos información sobre filtros por compatibilidad con el vehículo del usuario. |
| **Disponibilidad** | 🔎 En tiempo real (libre/ocupado). |
| **Reservas** | No se encontró información sobre reserva de franja en las fuentes consultadas. |
| **Precios** | 🔎 Tarifas publicadas por UTE (distintas para corriente alterna y continua). |
| **Evaluaciones** | No se encontró información. |
| **Ventajas observables** | 🔎 Red de más de 450 puntos en todo el país; operatividad promedio informada del 96,6 %. |
| **Aspectos a mejorar** | 💭 Solo cubre la red pública; no suma cargadores residenciales. 💭 La disponibilidad es del momento, no permite asegurar un horario futuro. |
| **Qué aprendemos** | 🎯 Los conductores uruguayos ya están acostumbrados a ver la disponibilidad en un mapa. Nuestra diferencia está en la **franja futura reservada** y en los cargadores **residenciales**. |

### C2 — eOne (Uruguay)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 Red de carga ultrarrápida (más de 180 kW) que se presenta como la primera de ese tipo en Uruguay. |
| **Público objetivo** | 🔎 Conductores que necesitan carga rápida. |
| **Funcionalidades** | 🔎 Localizar el punto más conveniente, ver información en tiempo real (disponibilidad, estándar de carga, potencia, servicios cercanos), navegar con Google Maps, iniciar sesión de carga, seguir la sesión en curso (costo, energía, potencia, nivel de batería) y pagar con tarjeta. |
| **Búsqueda** | 🔎 Por ubicación, con información del estándar de carga. |
| **Disponibilidad** | 🔎 En tiempo real. |
| **Reservas** | No se encontró información. |
| **Precios** | 🔎 El costo de la sesión se muestra durante la carga. |
| **Evaluaciones** | No se encontró información. |
| **Ventajas observables** | 🔎 Seguimiento detallado de la sesión en curso. |
| **Aspectos a mejorar** | 💭 La carga ultrarrápida está pensada para recargas cortas y no para quien necesita cargar varias horas cerca de casa. 💭 El costo se ve durante la sesión; no encontramos un cálculo **antes** de ir. |
| **Qué aprendemos** | 🎯 Mostrar costo y energía es valorado por los operadores. Nosotros proponemos mostrarlo **antes de reservar**, calculado para el vehículo y nivel de carga del conductor. |

### C3 — PlugShare (global)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 App y web gratuita para encontrar, reseñar y compartir información de cargadores en todo el mundo; se presenta como la mayor comunidad de conductores de vehículos eléctricos. |
| **Público objetivo** | 🔎 Conductores de vehículos eléctricos, incluidos quienes hacen viajes largos. |
| **Funcionalidades** | 🔎 Mapa de cargadores de muchas redes; filtros por tipo de conector, velocidad de carga, red y servicios cercanos; registrar el propio vehículo para ver solo cargadores compatibles; planificador de viajes; pago en ubicaciones participantes; agregar cargadores al mapa; notificaciones de nuevos cargadores cercanos; integración con Apple CarPlay. |
| **Búsqueda** | 🔎 Por mapa, con filtros por conector, velocidad y red. |
| **Disponibilidad** | 🔎 Indica estado y disponibilidad actual donde hay datos. |
| **Reservas** | No se encontró información sobre reserva de franjas. |
| **Precios** | 🔎 App gratuita con compras dentro de la app. |
| **Evaluaciones** | 🔎 Reseñas, fotos y un puntaje propio (*PlugScore*) basado en opiniones de conductores. |
| **Ventajas observables** | 🔎 Cobertura muy amplia y comunidad activa. 🔎 El filtro por vehículo registrado ya existe. |
| **Aspectos a mejorar** | 🔎 Una reseña en App Store critica que la información depende de datos cargados por usuarios y no siempre está verificada. 💭 Es un buscador: no gestiona la relación con un anfitrión particular. |
| **Qué aprendemos** | 🎯 Registrar el vehículo para filtrar por compatibilidad es un patrón probado; lo adoptamos (US-12, US-15). 🎯 La calidad de la información colaborativa necesita moderación, lo que refuerza la necesidad del rol administrador (US-30). |

### C4 — Electromaps (Europa)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 App colaborativa con más de 400.000 cargadores de muchos operadores en Europa, que permite iniciar y pagar cargas en los puntos gestionados. |
| **Público objetivo** | 🔎 Conductores de vehículos eléctricos en Europa; también ofrece soluciones para empresas. |
| **Funcionalidades** | 🔎 Mapa con disponibilidad en tiempo real; filtros por potencia, tipo de enchufe, cercanía, favoritos y puntos privados; iniciar la carga desde la app o con un llavero RFID; historial de cargas y pagos; comentarios y fotos de usuarios; los usuarios pueden proponer nuevos puntos. 🔎 Mediante su herramienta eManager, un propietario puede conectar cargadores privados o semipúblicos y decidir quién puede usarlos. |
| **Búsqueda** | 🔎 Mapa con filtros por potencia y conector. |
| **Disponibilidad** | 🔎 En tiempo real cuando la estación envía datos. |
| **Reservas** | 🔎 Una nota de 2023 indica que no permitía reservar puntos de carga. No encontramos una fuente más reciente que lo desmienta. |
| **Precios** | 🔎 Saldo prepago en la app, válido solo en los cargadores que gestiona. |
| **Evaluaciones** | 🔎 Comentarios y fotos. |
| **Ventajas observables** | 🔎 En español; historial de cargas; posibilidad de compartir cargadores privados con acceso controlado. |
| **Aspectos a mejorar** | 🔎 Una reseña en Google Play se queja de no poder usar el saldo en cargadores que figuraban como no disponibles o no compatibles con el pago. 💭 Compartir cargadores privados parece orientado a organizaciones o comunidades cerradas, no a vecinos desconocidos. |
| **Qué aprendemos** | 🎯 Lo que el usuario ve en la búsqueda tiene que coincidir con lo que puede usar realmente; por eso la búsqueda debe mostrar **solo** puntos compatibles y disponibles (como pide la letra). 🎯 El historial de sesiones es una funcionalidad esperada. |

### C5 — EVmatch (EE. UU.)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 Red de carga entre particulares: conecta a quienes tienen cargador con quienes lo necesitan y permite reservar, pagar y compartir cargadores privados. |
| **Público objetivo** | 🔎 Conductores (en especial inquilinos y residentes de apartamentos) y anfitriones residenciales, comerciales y de edificios. |
| **Funcionalidades** | 🔎 Anfitrión: publicar su cargador con marca, modelo, voltaje y amperaje; fijar precio y disponibilidad; elegir entre *reserva instantánea* o *aprobación de cada solicitud*; bloquear fechas; cobrar un recargo porcentual sobre el costo de la electricidad. 🔎 Conductor: registrar su vehículo, buscar en el mapa, filtrar por conector, velocidad, disponibilidad y precio, reservar con anticipación, activar el cargador desde el celular; favoritos. 🔎 La dirección exacta se comparte recién después de que el anfitrión aprueba la reserva. |
| **Búsqueda** | 🔎 Mapa con filtros por conector, velocidad, disponibilidad y precio. |
| **Disponibilidad** | 🔎 Definida por el anfitrión (horarios y bloqueos). |
| **Reservas** | 🔎 Sí, por horario. Se reserva con anticipación. |
| **Precios** | 🔎 Anfitrión: recargo sobre la electricidad (0 % para solo cubrir el costo). Conductor: paga una tarifa de servicio de la plataforma. Sin costo de registro para anfitriones residenciales. |
| **Evaluaciones** | No se encontró información detallada en las fuentes consultadas. |
| **Ventajas observables** | 🔎 Control fino del anfitrión sobre precio y horarios. 🔎 Protección de la privacidad: dirección oculta hasta aprobar. |
| **Aspectos a mejorar** | 💭 El precio se expresa como recargo sobre la electricidad; no encontramos que muestre un costo total estimado para el vehículo del conductor antes de reservar. |
| **Qué aprendemos** | 🎯 Confirma que el modelo "anfitrión fija condiciones + agenda + reserva" es viable en otro mercado. 🎯 Ocultar la dirección exacta hasta confirmar es una buena práctica ante el riesgo de seguridad del anfitrión (lo registramos como hipótesis a validar, no como requisito). |

### C6 — Co Charger (Reino Unido)

| Aspecto | Contenido |
|---|---|
| **Propuesta** | 🔎 Plataforma para que vecinos compartan cargadores domiciliarios con quienes no pueden instalar uno. Su misión declarada es "permitir que todos conduzcan un eléctrico". |
| **Público objetivo** | 🔎 Conductores sin carga domiciliaria (sin garaje o sin entrada para el auto) y dueños de cargadores domiciliarios. |
| **Funcionalidades** | 🔎 Mapa de anfitriones cercanos; reservas puntuales o **recurrentes**; la app gestiona comunicación, reservas y pagos; aviso cuando se registra un nuevo anfitrión en la zona; calculadora de tarifa para ayudar al anfitrión a fijar el precio. |
| **Búsqueda** | 🔎 Por cercanía en el mapa. |
| **Disponibilidad** | 🔎 Pensada para arreglos regulares con pocos vecinos. |
| **Reservas** | 🔎 Sí, puntuales y recurrentes. |
| **Precios** | 🔎 Precio por kWh transparente, sin suscripción; la plataforma se queda con el 12 % de cada sesión, descontado del precio del anfitrión. |
| **Evaluaciones** | No se encontró información. |
| **Ventajas observables** | 🔎 Foco muy claro en el mismo segmento que nuestro MVP. 🔎 Dice tener más de 5.000 anfitriones registrados. |
| **Aspectos a mejorar** | 🔎 Un anfitrión reseña en App Store que la app es "algo básica y anticuada" y que le resultaba confuso ajustar la tarifa cuando cambiaba su precio de electricidad. 🔎 Según esa misma reseña, no se puede ser anfitrión y conductor a la vez. |
| **Qué aprendemos** | 🎯 Fijar la tarifa por kWh es difícil para el anfitrión: una ayuda para calcularla podría ser útil (queda como *Could*, US-07 sin ampliar el alcance). 🎯 En nuestro producto una misma cuenta puede tener ambos perfiles y elegir con cuál entra (decisión de producto DP2, ver el Product Backlog). Esto evita la limitación que señala esa reseña. |

## 4. Tabla comparativa

Leyenda: ✔ presente según las fuentes · ✖ no encontrado en las fuentes · ◐ parcial

| Característica | UTE Mueve | eOne | PlugShare | Electromaps | EVmatch | Co Charger | **Nuestro MVP (propuesta)** |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| Mercado | UY | UY | Global | Europa | EE. UU. | Reino Unido | UY |
| Cargadores de particulares | ✖ | ✖ | ◐ (usuarios agregan puntos) | ◐ (acceso controlado) | ✔ | ✔ | ✔ |
| Búsqueda por ubicación/zona | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| Filtro por compatibilidad con el vehículo | ✖ | ✖ | ✔ | ◐ (por enchufe) | ◐ (por conector) | ✖ | ✔ (automático) |
| Búsqueda por día y franja futura | ✖ | ✖ | ✖ | ✖ | ✔ | ◐ | ✔ |
| Disponibilidad en tiempo real | ✔ | ✔ | ◐ | ✔ | ✖ | ✖ | ✖ (agenda) |
| Reserva de franja | ✖ | ✖ | ✖ | ✖ | ✔ | ✔ | ✔ |
| Tiempo y costo estimados antes de ir | ✖ | ✖ | ✖ | ✖ | ✖ | ✖ | ✔ |
| El anfitrión fija tarifa y condiciones | — | — | — | ◐ | ✔ | ✔ | ✔ |
| Agenda gestionada por el anfitrión | — | — | — | ✖ | ✔ | ✔ | ✔ |
| Evaluaciones / reseñas | ✖ | ✖ | ✔ | ✔ | ✖ | ✖ | ✔ (bidireccional) |
| Pago en la app | ✔ | ✔ | ◐ | ✔ | ✔ | ✔ | ✖ (fuera del MVP) |
| Historial de sesiones | ✖ | ◐ | ✖ | ✔ | ◐ | ✖ | ✔ (anfitrión) |
| Notificaciones de cambios en la reserva | ✖ | ✖ | ◐ (nuevos cargadores) | ✖ | ✖ | ◐ (nuevos anfitriones) | ✔ |

> "✖" significa **"no encontrado en las fuentes consultadas"**, no necesariamente que la aplicación no lo tenga. Esta limitación del análisis se debe revisar si en las iteraciones siguientes probamos las aplicaciones directamente.

## 5. Síntesis: hecho, interpretación y oportunidad

| Tema | 🔎 Hecho observado | 💭 Interpretación nuestra | 🎯 Oportunidad |
|---|---|---|---|
| Oferta en Uruguay | Las apps locales relevadas (UTE Mueve, eOne, EVE-APP) corresponden a redes operadas por una empresa. | No hay en Uruguay, entre lo que encontramos, una plataforma de cargadores residenciales entre particulares. | Ocupar ese espacio con foco en conductores sin cochera. |
| Compatibilidad | PlugShare filtra por vehículo registrado; EVmatch y Electromaps filtran por conector. | Filtrar por vehículo es un patrón conocido y útil, pero no aparece en las apps locales. | Compatibilidad automática según el vehículo registrado (letra). |
| Estimación | Ninguna de las fuentes muestra un costo total estimado **antes de reservar** para el vehículo del usuario. eOne muestra el costo durante la sesión. | Hay un vacío entre "precio por kWh" y "cuánto voy a pagar yo". | Tiempo y costo estimados por punto (letra), como diferencial. |
| Reserva | EVmatch y Co Charger permiten reservar; las redes locales no (según las fuentes). | En cargadores residenciales la reserva es necesaria porque el anfitrión tiene que saber quién viene. | Reserva de franja con notificaciones a ambas partes. |
| Confianza | PlugShare y Electromaps reciben críticas por datos no verificados; EVmatch oculta la dirección hasta aprobar. | La confianza es un problema recurrente en plataformas colaborativas. | Evaluaciones bidireccionales + moderación del administrador (letra). |
| Tarifa del anfitrión | Co Charger agregó una calculadora de tarifa ante las quejas de un anfitrión. | Fijar la tarifa no es trivial para un particular. | Posible ayuda para fijar la tarifa (*Could*, hipótesis a validar). |

## 6. Insights

### 6.1 Patrones encontrados

1. **Mapa + filtros por conector y potencia** es el patrón de búsqueda dominante en las seis soluciones.
2. **Registrar el vehículo** aparece en PlugShare y EVmatch como forma de personalizar resultados.
3. **Evaluaciones y comentarios** de la comunidad aparecen en los mapas colaborativos (PlugShare, Electromaps).
4. En las plataformas entre particulares (EVmatch, Co Charger), el **anfitrión controla precio y horarios** y la plataforma gestiona las reservas.
5. **Pago integrado** es casi universal en las soluciones comerciales.

### 6.2 Problemas observados (oportunidades)

1. **Brecha entre precio publicado y costo real:** el conductor ve "$/kWh" o el costo mientras carga, pero no cuánto le va a costar la carga que necesita. → En la [entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md) el conductor contó que con algunos operadores privados *"te enterás cuando pasás la tarjeta"*.
2. **Disponibilidad solo en el momento:** las redes locales muestran si un cargador está libre ahora, no si lo estará mañana a las 19:00. → En las entrevistas apareció lo mismo: *"te tira que está libre, llegás y está fuera de servicio"* ([entrevista 1](../entrevistas/transcripciones/entrevista-1-martin.md)) y *"saber seguro que cuando llegue va a estar libre"* ([entrevista 2](../entrevistas/transcripciones/entrevista-2-laura.md)).
3. **Calidad de la información colaborativa:** reseñas que critican datos no verificados. → Refuerza el rol del administrador para gestionar reportes (letra).
4. **Complejidad para el anfitrión particular** al fijar su tarifa. → Las entrevistas lo matizan: el dueño de casa ya tiene una tarifa en mente ($10–12/kWh sobre un costo nocturno de $4–5, [entrevista 3](../entrevistas/transcripciones/entrevista-3-alejandro.md)), mientras que el edificio la definiría con un contador ([entrevista 4](../entrevistas/transcripciones/entrevista-4-silvia.md)).

### 6.3 Diferenciación posible

La diferenciación no está en una funcionalidad aislada, porque cada una existe en algún competidor. Está en **combinarlas para el segmento concreto de la letra en Uruguay**:

1. **Resultado de búsqueda "listo para decidir":** solo puntos compatibles y libres en la franja elegida, con tiempo y costo calculados para el vehículo y el nivel de batería del conductor.
2. **Cargadores residenciales y de edificios** con reserva de franja, algo que no encontramos en el mercado uruguayo.
3. **Pensada para usuarios novatos** (RNF de la letra): el conductor no necesita entender de conectores ni potencias.
4. **Notificaciones de cambios en la reserva** para ambas partes, que ninguna de las fuentes describe explícitamente.

**Lo que decidimos no copiar (por ahora):** pago integrado, disponibilidad en tiempo real conectada al cargador, planificador de viajes y activación remota del cargador. La letra no los pide y exceden un prototipo de frontend. Quedan como **Won't Have (por ahora)** en el Product Backlog (ideas W-01 a W-09).

> Aclaración: no consideramos necesaria una funcionalidad solo porque la tenga un competidor. Cada elemento que incorporamos está en la letra o responde a un problema de nuestros usuarios.

### 6.4 Pendiente: prueba directa de las aplicaciones

Este análisis se basa en fuentes públicas. Como tarea de refinamiento, cada integrante instala y prueba al menos una app (prioridad: UTE Mueve, por ser la referencia local que los usuarios uruguayos ya tienen instalada) y actualiza las celdas marcadas con ✖. Conclusión a contrastar con esa prueba: **en Uruguay existe la app de la red pública y en el exterior existen apps de carga entre particulares, pero no encontramos una que combine ambos mundos para el caso local.**

[COMPLETAR con lo observado al probar las apps.]

## 7. Fuentes

Consultadas el 24/09/2026.

**Contexto Uruguay**
- UTE — Carga de vehículos: <https://www.ute.com.uy/clientes/movilidad-electrica/carga-de-vehiculos>
- UTE — UTE Mueve: <https://www.ute.com.uy/ute-mueve>
- UTE — Llamado a interesados en sumarse a la red de carga (jun-2026): <https://www.ute.com.uy/noticias/ute-convoca-interesados-en-sumarse-la-red-de-carga-para-vehiculos-electricos>
- UTE Mueve en Google Play: <https://play.google.com/store/apps/details?id=movilidad.ute.com.ute_movilidad_app&hl=es_UY>
- autoencuotas.com — "Dónde cargar tu auto eléctrico en Uruguay" (jun-2026): <https://autoencuotas.com/donde-cargar-tu-auto-electrico-en-uruguay-mapa-app-y-costos-2026/>
- MIEM — Precios y red de carga (EVE-APP): <https://www.gub.uy/ministerio-industria-energia-mineria/politicas-y-gestion/precios-red-carga>
- La Tribuna — "Uno de cada cinco vehículos 0 km vendidos en el 2025 en Uruguay fue eléctrico" (feb-2026): <https://www.latribuna.com.py/lifestyle/ciencia-y-tecnologia/2026/02/19/uno-de-cada-cinco-vehiculos-0-km-vendidos-en-el-2025-en-uruguay-fue-electrico/>
- Ámbito — "Las ventas de autos eléctricos cerraron el año con una suba del 146,7%": <https://www.ambito.com/uruguay/las-ventas-autos-electricos-cerraron-el-ano-una-suba-del-1467-y-marcaron-un-nuevo-record-n6233318>
- Ámbito — "La carga de vehículos eléctricos en la red pública sube 56% tras nuevos aumentos y el fin de los subsidios": <https://www.ambito.com/uruguay/la-carga-vehiculos-electricos-la-red-publica-sube-56-nuevos-aumentos-y-el-fin-los-subsidios-n6233071>
- eOne en App Store: <https://apps.apple.com/mx/app/eone/id6504017827>

**PlugShare**
- App Store: <https://apps.apple.com/us/app/plugshare/id421788217>
- Reseñas en App Store: <https://apps.apple.com/us/app/plugshare-charging-stations/id421788217?see-all=reviews>
- Blink Charging — "What is PlugShare?" (jun-2026): <https://blinkcharging.com/blog/what-is-plugshare>

**Electromaps**
- Google Play: <https://play.google.com/store/apps/details?id=com.enredats.electromaps&hl=es>
- Sitio oficial (app): <https://www.electromaps.com/es/app>
- Blog — cargadores privados con acceso controlado: <https://www.electromaps.com/es/blog/conecta-tus-cargadores-privados-a-electromaps-y-controla-quien-los-puede-usar>
- Buscatucoche — Consejos para usar Electromaps (2023): <https://www.buscatucoche.com/noticias/electromaps/>

**EVmatch**
- Solución residencial: <https://evmatch.com/solutions/residential/>
- App Store: <https://apps.apple.com/us/app/evmatch/id1269797035>
- Charged EVs — entrevista (2022): <https://chargedevs.com/features/evmatch-a-simple-low-cost-way-to-monetize-your-charging-stations/>

**Co Charger**
- FAQ: <https://co-charger.com/faq/>
- Community Charging: <https://co-charger.com/collaborate/community-charging/>
- App Store (incluye reseña de anfitrión): <https://apps.apple.com/gb/app/cocharger-shared-ev-charging/id1509473563>

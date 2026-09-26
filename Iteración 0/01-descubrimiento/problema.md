# Problema de negocio, visión y propuesta de valor

> Documento de la Iteración 0 · [Volver al README](../README.md)

## 1. Contexto (hechos con fuente)

- En Uruguay circulan cerca de **5.950 vehículos eléctricos** y hay aproximadamente **460 puntos de carga públicos**. El **88 %** de los autos eléctricos circula al sur del Río Negro (Montevideo, Canelones y Maldonado). *Fuente secundaria: autoencuotas.com, jun-2026, que cita datos de UTE.*
- UTE informa que su red pública supera los **450 puntos de carga**. En 2026 abrió un llamado para que particulares ofrezcan espacio en sus predios para instalar nuevas estaciones públicas. *Fuente: ute.com.uy, jun-2026.*
- UTE recomienda la carga en el domicilio como primera opción, por ser la más económica. *Fuente: autoencuotas.com y sitio de movilidad eléctrica de UTE.*
- El PDF del obligatorio define el segmento objetivo: personas con vehículo eléctrico que **no tienen punto de carga propio**, porque viven en un apartamento sin cochera o porque su cochera no tiene instalación.

Las fuentes completas están en el [análisis de competidores](../02-competidores/analisis-competidores.md#7-fuentes).

## 2. Problema principal

> **Los conductores de vehículos eléctricos que no pueden cargar en su domicilio no tienen una forma de acceder a cargadores privados cercanos, en una franja horaria asegurada, sabiendo antes de ir si el conector es compatible y cuánto les va a llevar y costar la carga.**

Al mismo tiempo, y como otra cara del mismo problema:

> **Las personas que tienen un cargador instalado en su casa o en su edificio no tienen un canal ordenado para ofrecerlo a otros conductores bajo sus propias condiciones (tarifa, duración, horarios y acceso).**

Planteado así, el problema se puede comprobar en las iteraciones siguientes: si es real, los conductores del segmento deberían reportar dificultades concretas para planificar la carga, y los anfitriones potenciales deberían mostrar disposición a publicar su cargador bajo condiciones controladas.

## 3. Usuarios afectados

| Usuario | Cómo le afecta el problema |
|---|---|
| Conductor sin carga en su domicilio | Depende de la red pública y no puede asegurar la carga ni anticipar el costo. |
| Anfitrión (propietario o administrador de edificio) | Tiene un equipo ocioso que podría generar ingresos y no tiene cómo ofrecerlo con control. |
| Conductor novato en movilidad eléctrica | Además de lo anterior, no sabe qué conector usa ni cómo la potencia afecta el tiempo de carga (RNF del PDF). |

## 4. Situación actual (cómo se resuelve hoy)

| Alternativa actual | Qué resuelve | Qué no resuelve | Tipo de afirmación |
|---|---|---|---|
| **Red pública de UTE (app UTE Mueve)** | Muestra los puntos públicos con disponibilidad en tiempo real y permite iniciar y pagar la carga. | No incluye cargadores de particulares ni ofrece reserva de franja según las fuentes consultadas. | Hecho observado (fuentes UTE) |
| **Redes privadas (p. ej. eOne, EVE)** | Carga rápida o gestionada con información en tiempo real. EVE-APP ofrece reserva en los puntos que gestiona. | Son redes comerciales. No abren cargadores residenciales a terceros. | Hecho observado (App Store, MIEM) |
| **Mapas colaborativos (p. ej. PlugShare, Electromaps)** | Ubicación de puntos, filtros por conector y opiniones. | En general no gestionan reservas entre particulares ni estiman costo según el vehículo. | Hecho observado + interpretación |
| **Acuerdos informales** (vecino, familiar, trabajo) | Acceso a un cargador privado. | Sin agenda, sin reglas claras de precio ni reputación. Dependen de conocer a alguien. | **Hipótesis a validar** |
| **Cargar en un enchufe común con alargue desde un apartamento** | Carga lenta en algunos casos. | Frecuentemente inviable sin cochera. Puede ser inseguro. | **Hipótesis a validar** |

## 5. Consecuencias de no resolverlo

- El conductor planifica peor sus traslados, gasta tiempo buscando puntos o esperando que se liberen y puede pagar más de lo que esperaba (**hipótesis a validar**).
- La falta de carga en el domicilio puede ser una barrera para que más personas que viven en apartamentos adopten un vehículo eléctrico (**hipótesis a validar**; en el Reino Unido, Co Charger sostiene que los conductores sin carga domiciliaria son varias veces menos propensos a tener un eléctrico, pero ese dato es de otro mercado).
- Los cargadores residenciales siguen ociosos la mayor parte del día y no generan ningún retorno a quien los instaló.

## 6. Oportunidad

- En otros mercados ya existen plataformas de carga entre particulares (EVmatch en EE. UU., Co Charger en el Reino Unido; ver [competidores](../02-competidores/analisis-competidores.md)). En Uruguay, las soluciones que relevamos son redes operadas por una empresa (UTE, eOne, EVE) y no marketplaces de cargadores particulares. Esto sugiere un espacio no cubierto localmente (**interpretación nuestra, a validar**).
- La concentración de vehículos eléctricos en el área metropolitana y Maldonado hace que la densidad de anfitriones y conductores sea mayor en una zona acotada. Eso favorece un modelo de cercanía.
- El PDF pide *"analizar ideas, buscar y mejorar aplicaciones ya existentes en el mercado"*. La mejora que proponemos es combinar tres cosas que en las apps relevadas aparecen por separado: **compatibilidad automática con el vehículo**, **estimación de tiempo y costo para esa carga concreta** y **reserva de franja en un cargador particular**.

## 7. Visión del producto

Formato de visión de Geoffrey Moore:

> **Para** conductores de vehículos eléctricos que no pueden cargar en su domicilio,
> **que** necesitan cargar fuera de casa en un horario que les sirva,
> **la aplicación** es una plataforma móvil de reserva de cargadores de particulares
> **que** les muestra solo los puntos compatibles con su vehículo y disponibles en la franja que eligen, con el tiempo y el costo estimados de su carga.
> **A diferencia de** la red pública y de los mapas de cargadores, que no permiten reservar un cargador residencial,
> **nuestro producto** conecta a esos conductores con anfitriones que ofrecen su cargador bajo sus propias condiciones de tarifa, horario y acceso.

| Pregunta | Respuesta |
|---|---|
| ¿Para quién? | Conductores de vehículos eléctricos sin carga en su domicilio (usuario principal) y anfitriones con cargador en su casa o edificio. |
| ¿Qué problema? | No pueden asegurar una carga cercana, compatible y con costo conocido. Los anfitriones no pueden ofrecer su cargador de forma ordenada. |
| ¿Qué solución? | App móvil que permite buscar por zona, día, franja y nivel de batería, filtrar por compatibilidad, estimar tiempo y costo, y reservar. Los anfitriones publican punto, condiciones y agenda. |
| ¿Qué beneficio? | El conductor planifica la carga con certeza y el anfitrión obtiene ingresos con un equipo que ya tiene. |

## 8. Propuesta de valor inicial

| Para el conductor | Para el anfitrión |
|---|---|
| Ve **solo** los puntos que le sirven (conector compatible y franja libre). | Publica su cargador con **sus** reglas: tarifa por kWh, duración máxima e instrucciones de acceso. |
| Sabe **antes de ir** cuánto va a tardar y cuánto le va a costar. | Decide **qué días y franjas** ofrece y puede modificarlos. |
| Tiene la **franja reservada** y recibe un recordatorio 30 minutos antes. | Recibe aviso si un conductor cancela y **libera su agenda**. |
| No necesita saber de conectores: la app compara por él. | Ve su **historial e ingreso acumulado**. |
| Puede leer evaluaciones de otros conductores. | Puede evaluar a los conductores. |

Todas las afirmaciones de valor de esta sección son **hipótesis a validar** con usuarios en las Iteraciones 1 y 2.

## 9. Supuestos de dominio que usamos

| # | Supuesto | Fundamento | Estado |
|---|---|---|---|
| S1 | Energía necesaria = capacidad de batería × (100 % − nivel actual). | Ejemplo del PDF: 60 kWh al 20 % → 48 kWh. | Confirmado (D3) |
| S2 | Tiempo estimado = energía necesaria / potencia del punto. | Ejemplo del PDF: 48 kWh / 7 kW ≈ 7 h (6,86 h). | Confirmado (D3) |
| S3 | Costo estimado = energía necesaria × tarifa por kWh. | Ejemplo del PDF: 48 kWh × $8 = $384. | Confirmado (D3) |
| S4 | La estimación no considera pérdidas ni la reducción de potencia cerca del 100 %. | Simplificación del ejemplo del PDF. | Confirmado (D3) |
| S5 | Si la duración máxima por sesión es menor que el tiempo estimado, se informa que la carga será parcial. | Deducción a partir de "duración máxima por sesión" del PDF. | Propuesta del equipo |
| S6 | El pago no se realiza dentro de la aplicación en el MVP. | El PDF no lo pide. | Decisión a validar con el profesor |
| S7 | Una *sesión realizada* es una reserva no cancelada cuya franja ya terminó; su importe es el costo estimado al reservar. | No hay integración con el cargador (el alcance es solo frontend). | Decisión a validar con el profesor |
| S8 | Compatibilidad = mismo tipo de conector en vehículo y punto (sin adaptadores). | Interpretación literal del PDF. | Hipótesis a validar |

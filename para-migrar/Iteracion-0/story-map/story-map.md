# Story Map

> Documento de la Iteración 0 · [Volver al README](../README.md) · [Product Backlog](../backlog/product-backlog.md)

<!-- Pendiente: exportar el mapa (Miro, FigJam o foto de post-its) como story-map.png en esta carpeta y descomentar la línea siguiente. -->
<!-- ![Story map](story-map.png) -->

## 1. Cómo leer este Story Map

Seguimos la técnica de *User Story Mapping* de Jeff Patton:

- **Backbone (actividades):** los grandes pasos del recorrido del usuario, de izquierda a derecha en orden narrativo. Siguiendo la convención acordada en la reunión del 30/09 (D2), **cada actividad es una épica del [Product Backlog](../backlog/product-backlog.md)** y lleva el mismo nombre.
- **Tareas:** lo que el usuario hace dentro de cada actividad.
- **Historias:** las historias del backlog (US-xx) que implementan cada tarea. Cada US-xx corresponde a la funcionalidad F-xx con el mismo número del [README](../README.md#12-funcionalidades-por-interesado).
- **Cortes de release (filas):**
  - **R1 — MVP / primera experiencia a validar** (prototipos de la Iteración 1).
  - **R2 — completar la letra** (prototipos de la Iteración 2).
  - **Posterior:** ideas fuera del alcance del obligatorio (*Won't Have por ahora*).
- **Perfil:** cada historia indica quién la usa: **(C)** conductor, **(A)** anfitrión, **(M)** administrador.

El recorrido empieza por el **anfitrión**, que crea la oferta, y sigue con el **conductor**, que es el usuario principal del MVP según la letra. Termina con la moderación del **administrador**.

## 2. Backbone y tareas

```text
 EP01               EP02                  EP03              EP04                 EP05               EP06              EP07              EP08
 ACCEDER A          GESTIONAR MI          REGISTRAR MI      BUSCAR Y             RESERVAR UNA       RECIBIR           EVALUAR Y         ADMINISTRAR LA
 MI CUENTA          PUNTO DE CARGA        VEHÍCULO          COMPARAR PUNTOS      FRANJA             AVISOS            REPORTAR          PLATAFORMA
 ──────────         ──────────────        ────────────      ───────────────      ────────────       ──────────        ──────────        ──────────────
 Crear cuenta       Registrar punto       Cargar datos      Indicar zona, día,   Elegir franja      Enterarme de      Evaluar el punto  Dar de alta
 Iniciar sesión     Publicar condiciones  del vehículo      franja y batería     Confirmar reserva  cambios del       Evaluar al        administradores
 Recuperar clave    Cargar agenda         Identificar el    Ver solo puntos      Ver mis reservas   anfitrión         conductor         Revisar reportes
 Cerrar sesión      Ver reservas          conector          compatibles          Cancelar reserva   Enterarme de      Reportar un       Arbitrar
 Editar mis datos   recibidas                               Ver tiempo y costo                      cancelaciones     problema          evaluaciones
                    Cancelar/modificar                      Ver detalle del                         Recordatorio                        Dar de baja
                    una franja                              punto                                   30 min antes                        usuarios
                    Ver historial e
                    ingresos
```

## 3. Historias por actividad y release

| Release | EP01 Acceder a mi cuenta | EP02 Gestionar mi punto de carga | EP03 Registrar mi vehículo | EP04 Buscar y comparar puntos | EP05 Reservar una franja | EP06 Recibir avisos | EP07 Evaluar y reportar | EP08 Administrar la plataforma |
|---|---|---|---|---|---|---|---|---|
| **R1 — MVP (It. 1)** | US-01 Registrarse con perfil (C, A) · US-02 Iniciar sesión eligiendo perfil (C, A, M) | US-06 Registrar punto (A) · US-07 Publicar condiciones (A) · US-08 Gestionar agenda de franjas (A) | US-12 Registrar vehículo (C) | US-14 Buscar por zona, día, franja y nivel (C) · US-15 Solo compatibles y disponibles (C) · US-16 Tiempo y costo estimados (C) · US-17 Detalle y condiciones del punto (C) | US-18 Reservar franja (C) · US-20 Ver mis reservas (C) | — | — | — |
| **R2 — Letra completa (It. 2)** | US-03 Recuperar contraseña · US-04 Cerrar sesión · US-05 Editar usuario (C, A, M) | US-10 Ver reservas recibidas (A) · US-09 Cancelar/modificar franja agendada (A) · US-11 Historial e ingreso acumulado (A) | US-13 Ayuda para identificar el conector (C, A) | — | US-19 Cancelar reserva (C) | US-24 Aviso de cambio/cancelación del anfitrión (C) · US-25 Aviso de cancelación del conductor (A) · US-26 Recordatorio 30 min (C) | US-21 Evaluar punto (C) · US-22 Evaluar conductor (A) · US-23 Reportar un problema (C, A) | US-27 Alta de administrador · US-28 Baja de usuarios · US-29 Arbitrar evaluaciones · US-30 Gestionar reportes (M) |
| **Posterior** | — | Ayuda para calcular la tarifa (W-07) · Fotos del punto · Plantillas de agenda semanal · Aprobar/rechazar cada reserva (W-06) · Exportar reportes | Varios vehículos por conductor (W-04) | Mapa con geolocalización (W-03) · Favoritos (W-09) | Pago en la app (W-01) · Reserva recurrente (W-05) · Chat con el anfitrión (W-08) | — | — | Roles de administrador con distintos permisos · Tablero de métricas |

Los códigos W-xx remiten al [backlog fuera del alcance](../backlog/product-backlog.md#5-backlog-fuera-del-alcance-actual-wont-have-por-ahora).

## 4. Corte del MVP (Release 1)

La línea del MVP cruza el recorrido **mínimo de punta a punta** que permite validar la propuesta de valor central:

```text
 ANFITRIÓN:  Crear cuenta → Iniciar sesión → Registrar punto → Publicar condiciones → Cargar agenda
                                                                                          │
                                                                                          ▼ (la oferta existe)
 CONDUCTOR:  Crear cuenta → Iniciar sesión → Registrar vehículo → Buscar (zona, día, franja, batería)
             → Ver solo compatibles y disponibles → Ver tiempo y costo → Ver detalle → Reservar → Ver mis reservas
```

**Por qué este corte.** Es lo mínimo que responde lo que más nos interesa comprobar: si el conductor sin cochera encuentra valor en *buscar → comparar → reservar*. Las [entrevistas](../README.md#13-entrevistas) lo respaldan: lo que más pidieron los conductores fue *"saber seguro que cuando llegue va a estar libre y me va a servir el enchufe"* y *"poder reservar un lugar seguro para dejarlo"*. Las actividades **EP06 a EP08** son **obligatorias según la letra** y se completan en la Iteración 2: quedan fuera del primer ciclo de validación, **no del producto**.

## 5. Verificación Story Map ↔ Product Backlog

| Historia | Actividad (= épica) | Perfil | Release |
|---|---|---|---|
| US-01 | EP01 Acceder a mi cuenta | C, A | R1 |
| US-02 | EP01 Acceder a mi cuenta | C, A, M | R1 |
| US-03 | EP01 Acceder a mi cuenta | C, A, M | R2 |
| US-04 | EP01 Acceder a mi cuenta | C, A, M | R2 |
| US-05 | EP01 Acceder a mi cuenta | C, A | R2 |
| US-06 | EP02 Gestionar mi punto de carga | A | R1 |
| US-07 | EP02 Gestionar mi punto de carga | A | R1 |
| US-08 | EP02 Gestionar mi punto de carga | A | R1 |
| US-09 | EP02 Gestionar mi punto de carga | A | R2 |
| US-10 | EP02 Gestionar mi punto de carga | A | R2 |
| US-11 | EP02 Gestionar mi punto de carga | A | R2 |
| US-12 | EP03 Registrar mi vehículo | C | R1 |
| US-13 | EP03 Registrar mi vehículo | C, A | R2 |
| US-14 | EP04 Buscar y comparar puntos | C | R1 |
| US-15 | EP04 Buscar y comparar puntos | C | R1 |
| US-16 | EP04 Buscar y comparar puntos | C | R1 |
| US-17 | EP04 Buscar y comparar puntos | C | R1 |
| US-18 | EP05 Reservar una franja | C | R1 |
| US-19 | EP05 Reservar una franja | C | R2 |
| US-20 | EP05 Reservar una franja | C | R1 |
| US-21 | EP07 Evaluar y reportar | C | R2 |
| US-22 | EP07 Evaluar y reportar | A | R2 |
| US-23 | EP07 Evaluar y reportar | C, A | R2 |
| US-24 | EP06 Recibir avisos | C | R2 |
| US-25 | EP06 Recibir avisos | A | R2 |
| US-26 | EP06 Recibir avisos | C | R2 |
| US-27 | EP08 Administrar la plataforma | M | R2 |
| US-28 | EP08 Administrar la plataforma | M | R2 |
| US-29 | EP08 Administrar la plataforma | M | R2 |
| US-30 | EP08 Administrar la plataforma | M | R2 |

Las 30 historias del backlog aparecen en el mapa, cada una en la actividad con el mismo nombre que su épica, y todas las tareas del mapa tienen al menos una historia (salvo las marcadas como *Posterior*, que no forman parte del backlog comprometido).

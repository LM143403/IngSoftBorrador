# Story Map

> Documento de la Iteración 0 · [Volver al README](../README.md)

## 1. Cómo leer este Story Map

Seguimos la técnica de *User Story Mapping* (Jeff Patton):

- **Backbone (actividades):** los grandes pasos del recorrido del usuario, de izquierda a derecha en orden temporal.
- **Tareas:** lo que el usuario hace dentro de cada actividad.
- **Historias:** las historias del [Product Backlog](../04-product-backlog/product-backlog.md) que implementan cada tarea (US-xx).
- **Cortes de release (horizontales):** qué entra en cada entrega.
  - **Release 1 — MVP / primera experiencia a validar** (prototipos de la Iteración 1).
  - **Release 2 — completar funcionalidades del PDF** (prototipos de la Iteración 2).
  - **Posterior:** ideas fuera del alcance del obligatorio (*Won't Have por ahora*).

> **Pendiente:** exportar el story map del equipo (físico o digital, por ejemplo en Miro o FigJam) como `story-map.png` en esta carpeta y enlazarlo acá. Las tablas de este documento son la versión de texto, versionable, del mismo mapa.

Como el producto tiene tres perfiles con recorridos distintos, armamos **un mapa por perfil**, ordenados según su prioridad para el MVP: conductor (usuario principal), anfitrión (oferta) y administrador (moderación).

## 2. Recorrido del conductor (usuario principal del MVP)

### 2.1 Backbone y tareas

```text
 C1 ACCEDER          C2 PREPARAR VEHÍCULO    C3 BUSCAR CARGA          C4 ELEGIR PUNTO           C5 RESERVAR            C6 GESTIONAR RESERVA      C7 DESPUÉS DE CARGAR
 ─────────────       ────────────────────    ───────────────          ───────────────           ────────────           ───────────────────       ────────────────────
 Crear cuenta        Registrar vehículo      Indicar zona             Ver tiempo estimado       Elegir franja          Ver mis reservas          Evaluar el punto
 Iniciar sesión      Identificar conector    Indicar día y franja     Ver costo estimado        Confirmar reserva      Cancelar reserva          Reportar un problema
 Recuperar clave                             Indicar nivel de carga   Comparar / ordenar                               Recibir recordatorio
 Editar mis datos                            Ver solo compatibles     Ver condiciones y                                Enterarme de cambios
 Cerrar sesión                               y disponibles            evaluaciones                                     del anfitrión
```

### 2.2 Historias por actividad y release

| Release | C1 Acceder | C2 Preparar vehículo | C3 Buscar carga | C4 Elegir punto | C5 Reservar | C6 Gestionar reserva | C7 Después de cargar |
|---|---|---|---|---|---|---|---|
| **R1 — MVP (It. 1)** | US-01 Registrarse con perfil · US-02 Iniciar sesión eligiendo perfil | US-12 Registrar vehículo | US-14 Buscar por zona, día, franja y nivel · US-15 Solo compatibles y disponibles | US-16 Tiempo y costo estimados · US-17 Detalle y condiciones del punto | US-18 Reservar franja | US-20 Ver mis reservas | — |
| **R2 — PDF completo (It. 2)** | US-03 Recuperar contraseña · US-04 Logout · US-05 Editar usuario | US-13 Ayuda para identificar conector | — | — | — | US-19 Cancelar reserva · US-24 Aviso de cambio/cancelación del anfitrión · US-26 Recordatorio 30 min | US-21 Evaluar punto · US-23 Reportar |
| **Posterior** | — | Varios vehículos por conductor *(a validar)* | Mapa con geolocalización | Favoritos | Pago en la app | Reserva recurrente | — |

## 3. Recorrido del anfitrión

### 3.1 Backbone y tareas

```text
 A1 ACCEDER          A2 PUBLICAR PUNTO            A3 DEFINIR DISPONIBILIDAD     A4 ATENDER RESERVAS           A5 REVISAR ACTIVIDAD
 ─────────────       ─────────────────            ────────────────────────      ───────────────────           ────────────────────
 Crear cuenta        Registrar punto de carga     Agregar franjas por día       Ver reservas recibidas        Ver historial de sesiones
 Iniciar sesión      Publicar condiciones         Quitar franjas libres         Cancelar/modificar franja     Ver ingreso acumulado
 Recuperar clave     (tarifa, duración,                                         agendada                      Evaluar conductores
 Editar mis datos    instrucciones)                                             Enterarme de cancelaciones    Reportar un problema
 Cerrar sesión
```

### 3.2 Historias por actividad y release

| Release | A1 Acceder | A2 Publicar punto | A3 Definir disponibilidad | A4 Atender reservas | A5 Revisar actividad |
|---|---|---|---|---|---|
| **R1 — MVP (It. 1)** | US-01 · US-02 *(compartidas con el conductor)* | US-06 Registrar punto · US-07 Publicar condiciones | US-08 Gestionar agenda de franjas | — | — |
| **R2 — PDF completo (It. 2)** | US-03 · US-04 · US-05 | US-13 Ayuda de conectores *(compartida)* | — | US-10 Ver reservas recibidas · US-09 Cancelar/modificar franja agendada · US-25 Aviso de cancelación del conductor | US-11 Historial e ingreso acumulado · US-22 Evaluar conductor · US-23 Reportar *(compartida)* |
| **Posterior** | — | Ayuda para calcular la tarifa · Fotos del punto | Plantillas de agenda semanal | Aprobar/rechazar cada reserva | Exportar reportes |

## 4. Recorrido del administrador

### 4.1 Backbone y tareas

```text
 M1 ACCEDER            M2 GESTIONAR ADMINISTRADORES      M3 MODERAR LA COMUNIDAD
 ─────────────         ────────────────────────────      ───────────────────────
 Iniciar sesión        Dar de alta otro administrador    Revisar reportes de la comunidad
 Recuperar clave                                         Arbitrar discrepancias en evaluaciones
 Cerrar sesión                                           Dar de baja usuarios
```

### 4.2 Historias por actividad y release

| Release | M1 Acceder | M2 Gestionar administradores | M3 Moderar |
|---|---|---|---|
| **R1 — MVP (It. 1)** | — | — | — |
| **R2 — PDF completo (It. 2)** | US-02 · US-03 · US-04 *(compartidas)* | US-27 Alta de administrador | US-30 Gestionar reportes · US-29 Arbitrar evaluaciones · US-28 Baja de usuarios |
| **Posterior** | — | Roles de administrador con distintos permisos | Tablero de métricas |

## 5. Corte del MVP (Release 1)

La línea del MVP cruza el recorrido **mínimo de punta a punta** que permite validar la propuesta de valor central:

```text
 ANFITRIÓN:  Registrarse → Iniciar sesión → Registrar punto → Publicar condiciones → Cargar agenda
                                                                                         │
                                                                                         ▼ (la oferta existe)
 CONDUCTOR:  Registrarse → Iniciar sesión → Registrar vehículo → Buscar (zona, día, franja, nivel)
             → Ver solo compatibles y disponibles → Ver tiempo y costo → Ver detalle → Reservar → Ver mis reservas
```

**Por qué este corte.** Es el mínimo que responde a las hipótesis más riesgosas (H1, H2 y H4, ver [personas](../01-descubrimiento/personas.md#registro-de-hipótesis-derivadas-de-las-personas)): si el conductor no encuentra valor en *buscar → comparar → reservar*, el resto de las funcionalidades pierde sentido. Las funcionalidades de R2 son **obligatorias según el PDF** y se completan en la Iteración 2. Quedan fuera del primer ciclo de validación, **no del producto**.

## 6. Verificación Story Map ↔ Product Backlog

| Historia | Actividad del mapa | Release |
|---|---|---|
| US-01 | C1 / A1 | R1 |
| US-02 | C1 / A1 / M1 | R1 |
| US-03 | C1 / A1 / M1 | R2 |
| US-04 | C1 / A1 / M1 | R2 |
| US-05 | C1 / A1 | R2 |
| US-06 | A2 | R1 |
| US-07 | A2 | R1 |
| US-08 | A3 | R1 |
| US-09 | A4 | R2 |
| US-10 | A4 | R2 |
| US-11 | A5 | R2 |
| US-12 | C2 | R1 |
| US-13 | C2 / A2 | R2 |
| US-14 | C3 | R1 |
| US-15 | C3 | R1 |
| US-16 | C4 | R1 |
| US-17 | C4 | R1 |
| US-18 | C5 | R1 |
| US-19 | C6 | R2 |
| US-20 | C6 | R1 |
| US-21 | C7 | R2 |
| US-22 | A5 | R2 |
| US-23 | C7 / A5 | R2 |
| US-24 | C6 | R2 |
| US-25 | A4 | R2 |
| US-26 | C6 | R2 |
| US-27 | M2 | R2 |
| US-28 | M3 | R2 |
| US-29 | M3 | R2 |
| US-30 | M3 | R2 |

Las 30 historias del backlog aparecen en el mapa y todas las tareas del mapa tienen al menos una historia (excepto las marcadas como *Posterior*, que no forman parte del backlog comprometido).

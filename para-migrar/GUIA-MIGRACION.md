# Guía paso a paso (Pablo): migrar Estudio de competidores y Story Map al repo de la cátedra

**Desde:** `IngSoftBorrador/para-migrar/` (archivos ya adaptados)
**Hacia:** `143403_342426_297252/Iteracion-0/` (repo de la cátedra, con gitflow)

| Bloque | Archivo que se migra | Sección del README | Issue del tablero |
|---|---|---|---|
| 3. Estudio de competidores | `Iteracion-0/competidores/analisis-competidores.md` | 1.4 | #3 |
| 4. Story map | `Iteracion-0/story-map/story-map.md` (+ `story-map.png`) | 2.1 | #4 |

> Los números de issue salen del orden en que se crearon las tarjetas. **Confirmalos en el [tablero](https://github.com/orgs/IngSoft-ISA1-2026-2/projects/12)** antes de usarlos en el PR.

**Qué ya está hecho en los archivos adaptados (no hace falta tocarlos):**

- Los links apuntan al README de la iteración y a las entrevistas que integró Sebastián.
- Dice "la letra" en vez de "el PDF", con el mismo estilo que el README.
- El story map tiene como backbone las **8 épicas**, con los mismos nombres que en el backlog (convención D2 del acta 30/09).
- El estudio de competidores cita las entrevistas donde aportan evidencia.

Se usa **una sola rama y un solo PR** para los dos bloques. Así el README se toca una sola vez y no hay conflictos.

Todos los comandos son para **Git Bash** en Windows. Donde dice `<...>`, se reemplaza por el valor que corresponda.

---

## Parte A — Bajar los archivos adaptados

```bash
cd "/d/ORT/3 año/2 semestre/Ingeniería de software ágil 1/Obligatorio/IngSoftBorrador"
git pull
ls para-migrar/Iteracion-0/competidores para-migrar/Iteracion-0/story-map
```

✅ Tienen que verse `analisis-competidores.md` y `story-map.md`.

> **Si no tenés el Borrador clonado:** `cd ".../Obligatorio"` y después `git clone https://github.com/LM143403/IngSoftBorrador.git`.
> **Si no aparece `para-migrar/`:** Facundo todavía no lo subió; pedile que haga el push.

---

## Parte B — Preparar el repo de la cátedra

```bash
cd "/d/ORT/3 año/2 semestre/Ingeniería de software ágil 1/Obligatorio/143403_342426_297252"
git status
```

- Si dice **"nothing to commit, working tree clean"**, seguí.
- Si aparecen archivos modificados que no querés perder, **pará acá** y avisá por WhatsApp.

```bash
git checkout develop
git pull origin develop
git log --oneline -5
```

Con `git log` controlás que tenés lo último: tienen que aparecer, entre otros, los commits de Sebastián con los interesados y las entrevistas.

```bash
git checkout -b feature/it0-competidores-story-map
```

✅ **Verificación:** `git branch` muestra el asterisco en `feature/it0-competidores-story-map`.

> **Si `git pull` falla** con "There is no tracking information": `git branch --set-upstream-to=origin/develop develop` y repetí el `git pull`.

---

## Parte C — Copiar los archivos

```bash
mkdir -p Iteracion-0/competidores Iteracion-0/story-map
cp ../IngSoftBorrador/para-migrar/Iteracion-0/competidores/analisis-competidores.md Iteracion-0/competidores/
cp ../IngSoftBorrador/para-migrar/Iteracion-0/story-map/story-map.md Iteracion-0/story-map/
```

> **Alternativa sin comandos:** desde el Explorador de Windows, copiar las carpetas `IngSoftBorrador\para-migrar\Iteracion-0\competidores` y `...\story-map` y pegarlas dentro de `143403_342426_297252\Iteracion-0\`.

✅ **Verificación:**

```bash
git status
```

Tienen que aparecer **solo** `Iteracion-0/competidores/` e `Iteracion-0/story-map/` como nuevos.

Un commit por bloque, así el historial muestra cada entrega por separado:

```bash
git add Iteracion-0/competidores/
git commit -m "[IT0] Estudio de competidores"

git add Iteracion-0/story-map/
git commit -m "[IT0] Story map"
```

---

## Parte D — Completar el README de la iteración

Abrí `Iteracion-0/README.md` (por ejemplo, con `code Iteracion-0/README.md` en VS Code). Del Borrador vas a usar dos fragmentos:

- `../IngSoftBorrador/para-migrar/README-seccion-1.4.md`
- `../IngSoftBorrador/para-migrar/README-seccion-2.1.md`

### D.1 Sección 1.4 — Estudio de competidores

1. En `README.md` buscá la línea:
   ```markdown
   ### 1.4 Estudio comparativo de aplicaciones similares
   ```
   Hoy está vacía: debajo viene directamente `## 2. Definición del problema / solución`.
2. **Reemplazá esa línea** por todo el contenido de `README-seccion-1.4.md`. El fragmento ya trae el título, así que no lo dupliques.

### D.2 Sección 2 — Story map

1. En `README.md` buscá el bloque:
   ```markdown
   ## 2. Definición del problema / solución
   - Story map
   - Product Backlog: épicas → historias de usuario → criterios de aceptación
   - Priorización de los prototipos a idear, construir y validar
   ```
2. **Reemplazalo completo** por el contenido de `README-seccion-2.1.md`. Ese fragmento ya deja los títulos **2.2** (Facundo) y **2.3** (Sebastián) con un comentario de pendiente.

### D.3 Revisar y commitear

- **No toques** las secciones 1.1 a 1.3, Seguimiento ni Retrospectiva.
- Guardá el archivo.

```bash
git diff Iteracion-0/README.md
```

Solo tienen que aparecer cambios en la 1.4 y en la sección 2.

```bash
git add Iteracion-0/README.md
git commit -m "[IT0] README: secciones 1.4 (competidores) y 2.1 (story map)"
```

---

## Parte E — Imagen del story map

La rúbrica valora que los artefactos se puedan ver dentro del repo. El story map tiene que tener una imagen.

1. Armá el mapa en **Miro** o **FigJam**, o con post-its y una foto, siguiendo `Iteracion-0/story-map/story-map.md`:
   - **Columnas (backbone), en este orden:** Acceder a mi cuenta · Gestionar mi punto de carga · Registrar mi vehículo · Buscar y comparar puntos · Reservar una franja · Recibir avisos · Evaluar y reportar · Administrar la plataforma.
   - **Debajo de cada columna:** las tareas del usuario (sección 2 del archivo).
   - **Filas:** los cortes **R1 (MVP)**, **R2** y **Posterior**, con las historias US-xx (sección 3 del archivo).
   - Opcional: un color por perfil (conductor, anfitrión, administrador).
2. Exportalo como **PNG** con el nombre `story-map.png` y guardalo en `Iteracion-0/story-map/`.
3. Activá las líneas de la imagen sacando los `<!--` y `-->`:
   - en `Iteracion-0/story-map/story-map.md`: `![Story map](story-map.png)`;
   - en `Iteracion-0/README.md`, sección 2.1: `![Story map](story-map/story-map.png)`.

```bash
git add Iteracion-0/story-map/story-map.png Iteracion-0/story-map/story-map.md Iteracion-0/README.md
git commit -m "[IT0] Imagen del story map"
```

> Si la imagen todavía no está, no bloquea el PR: se puede subir después en un commit de la misma rama, antes del merge.

---

## Parte F (opcional, suma puntos) — Probar las apps

La sección **6.4** de `analisis-competidores.md` quedó pendiente: el análisis se hizo con fuentes públicas, sin usar las apps. Si podés, instalá **UTE Mueve** (y, si querés, PlugShare), probá buscar un cargador y completá el `[COMPLETAR]` de la 6.4 con lo que observaste. Por ejemplo: ¿permite reservar? ¿muestra el costo antes de ir? ¿filtra por conector? Corregí también en la tabla comparativa (sección 4) las celdas ✖ que resulten no ser ciertas.

```bash
git add Iteracion-0/competidores/analisis-competidores.md
git commit -m "[IT0] Competidores: prueba directa de UTE Mueve"
```

Si no llegás, dejalo como está: la 6.4 ya explica que es una tarea pendiente.

---

## Parte G — Push y Pull Request contra `develop`

```bash
git push -u origin feature/it0-competidores-story-map
```

**Con la CLI (recomendado, porque fija la base):**

```bash
gh pr create --base develop --title "[IT0] Estudio de competidores y Story map" --body "Estudio comparativo de 6 soluciones (README 1.4) y story map con las 8 épicas como backbone (README 2.1). Closes #3, closes #4"
```

**Desde la web:** en GitHub, tocá **Compare & pull request**. ⚠️ Cambiá **base: `main`** por **base: `develop`**. En la descripción poné `Closes #3, closes #4`.

### Antes de pedir revisión: revisar cómo se ve

En el PR, pestaña **Files changed** → en cada `.md`, los tres puntos (**⋯**) → **View file**. Revisá:

- [ ] Las tablas se ven como tablas, no como texto con `|`.
- [ ] Desde el README, los links *"Detalle: ..."* abren `analisis-competidores.md` y `story-map.md`.
- [ ] Desde `analisis-competidores.md`, los links a las entrevistas abren las transcripciones.
- [ ] La imagen del story map se ve, si ya la subiste.

> **Normal por ahora:** en `story-map.md`, los links al *Product Backlog* (`../backlog/...`) dan 404 hasta que Facundo integre su parte. No es un error tuyo.

### Revisión y merge

1. Asigná como **Reviewer** a Facundo o a Sebastián y avisá por WhatsApp.
2. Si piden cambios: se hacen en la misma rama, con commit y push, y el PR se actualiza solo.
3. Para integrar, elegí **"Create a merge commit"**, no *Squash*: así se conservan los commits individuales, que la rúbrica mira.
4. Después del merge, tocá **Delete branch** en GitHub.

---

## Parte H — Después del merge

```bash
git checkout develop
git pull origin develop
git branch -d feature/it0-competidores-story-map
```

**Tablero:** con `Closes #3, closes #4`, las tarjetas pasan solas a **Done**. Si no pasan, movelas a mano y poné **Restante (h) = 0**.

**Registro de horas:** cargá tus horas en el registro de horas de la iteración, con el PR como evidencia. Por ejemplo:

| Fecha | Integrante | Ítem | Tipo | Descripción | Horas | Evidencia |
|---|---|---|---|---|---|---|
| AAAA-MM-DD | Pablo Facundo Acuña | #3 Competidores | Documentación | Migración del estudio de competidores y sección 1.4 del README | X,X | PR #N |
| AAAA-MM-DD | Pablo Facundo Acuña | #4 Story map | Diseño | Armado del story map en Miro, exportación e integración (sección 2.1) | X,X | PR #N |

**Avisá por WhatsApp** que está integrado: Facundo necesita tu merge para completar la sección 2.2 del README sin conflictos.

---

## Problemas frecuentes

| Síntoma | Causa | Solución |
|---|---|---|
| `error: pathspec 'develop' did not match` | No tenés `develop` local. | `git fetch origin` y después `git checkout develop`. |
| `rejected ... non-fast-forward` al hacer push | Hay cambios remotos en tu rama. | `git pull --rebase` y repetí el `git push`. |
| El PR muestra archivos que no tocaste | La rama se creó desde `main` o desde una rama vieja. | Creá la rama de nuevo desde `develop` actualizado y copiá otra vez los archivos. |
| El PR apunta a `main` | La base por defecto de la organización es `main`. | En el PR: **Edit** (al lado del título) → base `develop`. |
| `cp: cannot stat ...` | La ruta al Borrador es distinta. | Revisá que `IngSoftBorrador` esté en la misma carpeta `Obligatorio` que el repo de la cátedra, o usá la ruta completa. |
| Conflicto en `README.md` al hacer pull o merge | Alguien más tocó el README mientras tanto. | Abrí el archivo, quedate con **las dos** versiones de las secciones (la tuya y la del otro), borrá las marcas `<<<<<<<`, `=======` y `>>>>>>>`, y después `git add` + `git commit`. Si dudás, avisá antes de commitear. |

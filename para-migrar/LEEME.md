# Archivos listos para migrar al repo de la cátedra

Esta carpeta replica la estructura de `143403_342426_297252/Iteracion-0/`. Los archivos ya están adaptados: links al README de la iteración y a las entrevistas, "la letra" en lugar de "el PDF", épicas con el mismo nombre que las actividades del story map (D2 del acta 30/09), supuestos marcados como DP-xx y hallazgos de las entrevistas.

| Archivo | Destino en el repo de la cátedra | Responsable |
|---|---|---|
| `Iteracion-0/story-map/story-map.md` | `Iteracion-0/story-map/story-map.md` | Pablo |
| `Iteracion-0/backlog/product-backlog.md` | `Iteracion-0/backlog/product-backlog.md` | Facundo |
| `Iteracion-0/backlog/historias-usuario.md` | `Iteracion-0/backlog/historias-usuario.md` | Facundo |
| `README-seccion-2.md` | Pegar en `Iteracion-0/README.md`, sección 2 | Pablo (2.1) → Facundo (2.2) |

## Pasos (Git Bash)

```bash
# 1. Traer lo último del borrador
cd "/d/ORT/3 año/2 semestre/Ingeniería de software ágil 1/Obligatorio/IngSoftBorrador"
git pull

# 2. Ir al repo de la cátedra y crear la rama desde develop
cd ../143403_342426_297252
git checkout develop
git pull
git checkout -b feature/it0-story-map          # Facundo: feature/it0-backlog

# 3. Copiar SOLO lo que te toca
mkdir -p Iteracion-0/story-map
cp ../IngSoftBorrador/para-migrar/Iteracion-0/story-map/story-map.md Iteracion-0/story-map/
#   Facundo:
#   mkdir -p Iteracion-0/backlog
#   cp ../IngSoftBorrador/para-migrar/Iteracion-0/backlog/*.md Iteracion-0/backlog/

# 4. Pegar tu parte de README-seccion-2.md en Iteracion-0/README.md (sección 2)

# 5. Commit, push y PR contra develop
git add Iteracion-0/
git commit -m "[IT0] Story map"                 # Facundo: "[IT0] Product Backlog, épicas, HU y criterios"
git push -u origin feature/it0-story-map
gh pr create --base develop --title "[IT0] Story map" --body "Closes #4"
```

**Orden sugerido:** primero se integra el PR de Pablo, que crea los títulos 2.1–2.3 del README. Después Facundo hace `git merge develop` en su rama y completa solo la 2.2. Así no hay conflictos.

## Pendientes antes de dar por terminado

- [ ] **Pablo:** exportar el story map como imagen (`story-map.png`) y descomentar la línea `![Story map](story-map.png)` en `story-map.md` y en el README.
- [ ] **PO:** confirmar las decisiones de producto DP2–DP10 y los supuestos S4–S8 (backlog §8) y registrarlo en un acta.
- [ ] **PO:** decidir si se agrega la matrícula del vehículo (propuesta que surgió de las entrevistas 3 y 4).
- [ ] Probar los links en la web de GitHub después del push.

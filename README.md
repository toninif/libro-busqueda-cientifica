# Buscar antecedentes: guía para estudiantes

**De la búsqueda por términos a la inteligencia artificial**

Libro en [Quarto](https://quarto.org/) para orientar a estudiantes en la búsqueda bibliográfica de antecedentes. Va desde las herramientas y aproximaciones clásicas (bases de datos, vocabularios controlados, operadores booleanos, cadenas de búsqueda) hasta las revisiones sistemáticas (pregunta PICO, PRISMA) y las herramientas con inteligencia artificial. Presta especial atención a la búsqueda en español y en inglés.

## Estructura del proyecto

```text
libro-busqueda-cientifica.Rproj   Proyecto de RStudio
_quarto.yml                       Configuración del libro (capítulos, partes, formatos)
index.qmd                         Presentación y sugerencia de uso en clase
capitulos/                        Capítulos 1 a 12 (.qmd)
anexos/                           Anexos A a D: plantillas, glosario, recursos, bibliografía
_book/                            Salida generada (no se versiona)
```

| Parte | Capítulos |
|---|---|
| I. Fundamentos | 1. Qué son los antecedentes · 2. Planificar la búsqueda · 3. Dónde buscar |
| II. Técnicas de búsqueda | 4. Búsqueda por términos · 5. Operadores y cadenas · 6. Buscar en español y en inglés |
| III. Búsqueda sistemática | 7. Pregunta PICO y variantes · 8. Revisiones sistemáticas y PRISMA · 9. Búsqueda por citas |
| IV. IA, evaluación y escritura | 10. Inteligencia artificial · 11. Evaluar fuentes · 12. Gestionar referencias y escribir |

## Cómo generar el libro

Hace falta tener [Quarto](https://quarto.org/docs/get-started/) instalado (RStudio ya lo trae incluido). No se necesita R: los capítulos no tienen código ejecutable.

**Desde RStudio:** abrí `libro-busqueda-cientifica.Rproj` y, en el panel *Build*, usá **Render Book**. Para ver los cambios en vivo mientras editás, usá el botón *Render* sobre cualquier `.qmd`.

**Desde la terminal:**

```bash
quarto preview            # vista previa en el navegador, se actualiza al guardar
quarto render             # genera HTML y Word en _book/
quarto render --to html   # solo la versión web
```

Formatos configurados en `_quarto.yml`:

- **HTML:** sitio web del libro, con buscador, modo claro y oscuro, y botón para copiar las cadenas de búsqueda.
- **Word (.docx):** para imprimir o editar.

Los diagramas usan [Mermaid](https://quarto.org/docs/authoring/diagrams.html), que Quarto dibuja sin herramientas adicionales. En Word se insertan como imágenes, para lo cual Quarto usa un navegador Chrome o Edge instalado.

Para agregar PDF, sumá `pdf:` en la sección `format` de `_quarto.yml` y ejecutá una vez `quarto install tinytex`. Antes, conviene reemplazar los emojis de acceso (🟢 🟡 🔴) del Anexo C, que LaTeX no dibuja con las fuentes por defecto.

## Estilo

El libro tiene una estética de "expediente de detective" definida en `theme/`:

- `detective.scss`: paleta de papel, tinta, lacre y latón; tipografías (Libre Baskerville, Source Serif 4, Special Elite y Courier Prime, de Google Fonts); recuadros como fichas, tablas como registros y la lupa como ícono de las pistas.
- `detective-dark.scss`: la misma estética en modo oscuro ("noche en Baker Street"); solo redefine los colores.
- `images/portada.svg` e `images/favicon.svg`: portada e ícono de la pestaña.

Los títulos por defecto de los recuadros ("Pista", "Nota al margen", "Clave del caso", "Cuidado") se definen en `_quarto.yml`, en la sección `language`.

## Publicar

El libro se publica solo en **https://toninif.github.io/libro-busqueda-cientifica/**. Cada push a `main` dispara la GitHub Action `.github/workflows/publicar-libro.yml`, que renderiza el libro con Quarto y sube el resultado a la rama `gh-pages`. También se puede ejecutar a mano desde la pestaña *Actions*.

En *Settings → Pages*, la fuente tiene que ser **Deploy from a branch → `gh-pages` / `(root)`**.

## Estado

Primera versión completa, septiembre de 2026. El capítulo 10 (inteligencia artificial) y el Anexo C (recursos) son los que envejecen más rápido y conviene revisarlos cada cuatrimestre.

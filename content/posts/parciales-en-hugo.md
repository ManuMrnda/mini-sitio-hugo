---
title: "Parciales en Hugo: reutiliza tu código"
date: 2026-10-29T14:00:00+01:00
draft: false
---

Uno de los conceptos clave que hemos aprendido en las lecciones de [Hugo Codex](https://hugocodex.org/es/empezando/) es el uso de **plantillas parciales** (*partials*) dentro del directorio `layouts/partials/`.

## ¿Por qué usar parciales?

En lugar de repetir la estructura de la cabecera (`<head>`, barra de navegación `<nav>`, hoja de estilos) y el pie de página (`<footer>`) en cada una de las plantillas (`home.html`, `single.html`, `list.html`), extraemos esos fragmentos a archivos independientes:

- `layouts/partials/header.html`: contiene los metadatos, el enlace a la hoja de estilos mediante `relURL` y el menú de navegación principal.
- `layouts/partials/footer.html`: incluye la información de autoría de **Manuel Miranda Fernández**, enlaces rápidos y cierre del documento HTML.

Para incluirlos en cualquier plantilla de Hugo simplemente utilizamos:

```go-html-template
{{ partial "header.html" . }}
  <!-- Contenido específico de la plantilla -->
{{ partial "footer.html" . }}
```

De este modo mantenemos el principio **DRY** (*Don't Repeat Yourself*) y la filosofía **KISS** en todo nuestro proyecto web.

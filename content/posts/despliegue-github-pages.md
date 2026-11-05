---
title: "Desplegando nuestro sitio Hugo en GitHub Pages (P1.3)"
date: 2026-11-05T16:15:00+01:00
draft: false
---

En esta práctica (**P1.3 / PrácticaX2**) damos el salto desde el entorno de desarrollo local (`hugo server -D`) a la publicación real en Internet utilizando el servicio gratuito **GitHub Pages**.

## Pasos clave del despliegue estático

1. **Configuración en `hugo.toml`**:
   - Definimos `baseURL = "https://ManuMrnda.github.io/mini-sitio-hugo/"` incluyendo la subruta del repositorio.
   - Configuramos `publishDir = "html"` para que Hugo genere el HTML estático directamente en la carpeta `/html` que servirá GitHub Pages.
2. **Desactivar Jekyll con `.nojekyll`**:
   - Creamos `static/.nojekyll` para que Hugo lo copie a `html/.nojekyll` y GitHub sirva los archivos estáticos tal cual, sin procesarlos con Jekyll.
3. **Rutas relativas seguras con `relURL`**:
   - Todas las referencias a hojas de estilos (`{{ "css/estilo.css" | relURL }}`) y enlaces de navegación usan las funciones nativas de Hugo para funcionar tanto en local como bajo la subruta `/mini-sitio-hugo/`.
4. **Flujo de publicación con Git**:
   - Ejecutamos `hugo` para compilar los cambios en `html/`, realizamos `git add .`, `git commit` y `git push` hacia la rama `main`.

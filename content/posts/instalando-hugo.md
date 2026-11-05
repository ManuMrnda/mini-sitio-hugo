---
title: "Instalando Hugo en mi VM"
date: 2026-10-29T12:00:00+01:00
draft: false
---

Durante la práctica **P1.2 de IAW**, el primer paso consistió en instalar la versión *extended* de **Hugo** en nuestro entorno GNU/Linux y verificar su correcto funcionamiento desde la terminal.

## Proceso de instalación paso a paso

Para disponer de una versión actualizada de Hugo que soporte todas las características modernas de plantillas, descargamos el paquete oficial desde el repositorio de lanzamientos en GitHub:

```bash
# Comprobar la versión instalada de Hugo
hugo version

# Crear la estructura base de nuestro nuevo sitio web
hugo new site mi-sitio

# Levantar el servidor de desarrollo local incluyendo borradores
cd mi-sitio
hugo server -D --watch
```

Con el flag `--watch` activado, Hugo detecta en tiempo real cualquier cambio en `content/`, `layouts/` o `hugo.toml` y refresca automáticamente el navegador en `http://localhost:1313/`.

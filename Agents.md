# Agent Context: Blog Infrastructure & Maintenance

Este archivo es la fuente de verdad para el mantenimiento del sitio. Priorizar estabilidad y minimalismo técnico.

## 1. Stack Tecnológico
- **Engine:** Jekyll (Ruby).
- **Template Base:** Minimal (Overridden).
- **Estilos:** Sass (SCSS) modularizado en `assets/css/style.scss`.
- **Deployment:** GitHub Pages.

## 2. Reglas de Mantenimiento (Pipeline)
- **CSS Overrides:** Nunca editar los archivos del "theme" gema. Cualquier cambio de estilo debe ir al final de `style.scss` usando selectores específicos para ganar especificidad.
- **Invisibilidad del "by":** El elemento `<p class="view">` debe permanecer oculto (`display: none !important`) para mantener el look de CEO Tech.
- **Liquid Logic:** Para la página de inicio, mantener siempre el filtro `offset: 1 limit: 10` para proteger el rendimiento del renderizado.

## 3. Protocolo de Nuevos Posts
Al detectar un nuevo archivo en `_posts/`:
1. **Validación de Front Matter:** Verificar que contenga `layout: post`, `title` y `date`.
2. **Optimización de Código:** Los bloques de código deben estar indentados con 2 espacios y especificar el lenguaje (ej: ```java) para el resaltado sintáctico de JetBrains Mono.
3. **Limpieza de Residuos:** Eliminar automáticamente cualquier rastro de texto basura como "Borrar4" o placeholders de edición.

## 4. Estándares de Diseño (UI/UX)
- **Ancho de lectura:** Mantener el `max-width: 800px` para legibilidad técnica.
- **Footer:** No añadir más iconos de los 2 acordados (LinkedIn, GitHub) para evitar ruido visual a menos que te lo pida explícitamente.
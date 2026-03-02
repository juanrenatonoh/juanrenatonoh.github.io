# Blog de Ingeniería Minimalista

Este repositorio contiene el código fuente de un blog de ingeniería enfocado en el minimalismo técnico y la alta legibilidad (diseño "CEO Tech"). La infraestructura está diseñada priorizando la estabilidad y evitando el ruido visual innecesario.

## Tecnologías

- **Engine:** Jekyll (Ruby)
- **Tema Base:** Minimal
- **Estilos:** Sass (SCSS)
- **Deployment:** GitHub Pages

## Cómo levantarlo localmente

Para ejecutar el blog en tu entorno local, asegúrate de tener Ruby y Bundler instalados. Luego, ejecuta los siguientes comandos en la raíz del proyecto:

1. Instala las dependencias necesarias:
   ```bash
   bundle install
   ```

2. Levanta el servidor local de Jekyll:
   ```bash
   bundle exec jekyll serve
   ```
El sitio estará disponible por defecto en `http://localhost:4000`.

## Estructura del Proyecto

La arquitectura del proyecto sigue los estándares de Jekyll. A continuación, se explican los directorios clave:

- `_posts/`: Directorio donde se almacenan las publicaciones (artículos) del blog. Cada post es un archivo Markdown (`.md`) que debe incluir el Front Matter básico (`layout`, `title`, `date`).
- `_includes/`: Contiene fragmentos de código y componentes reutilizables (como head, footer de iconos limitados, o scripts) que se inyectan dentro de los layouts. Permite mantener el código modular.
- `_layouts/`: Contiene las plantillas base que definen la estructura principal de las páginas y de los artículos. En este proyecto se utiliza para hacer el override del tema Minimal sin alterar la gema original.

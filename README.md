# Senado Web

Base de tema WordPress clasico para el rediseño institucional de la Honorable Camara de Senadores del Paraguay.

## Estructura principal

```text
senado-web/
|-- AGENTS.md
|-- README.md
|-- .gitignore
|-- docs/
`-- wp-content/
   `-- themes/
      `-- senado-institucional-base/
```

## Tema

El tema `senado-institucional-base` esta pensado para:

- mantener WordPress como CMS;
- implementarse primero en staging;
- usar APIs nativas de WordPress;
- permitir evolucion progresiva sin tocar produccion.

## Portada

La portada se monta desde `front-page.php` usando parciales en `template-parts/sections/`:

- `hero.php`
- `quick-links.php`
- `news.php`
- `agenda.php`
- `institutional.php`
- `transparency.php`

## Estructura del tema

El nucleo activo del tema vive en:

- `assets/`
- `inc/`
- `template-parts/content/`
- `template-parts/sections/`

Los archivos de iteraciones anteriores que no forman parte de la base minima activa fueron archivados en:

- `wp-content/themes/senado-institucional-base/legacy/`

Esto permite mantener el repo claro para staging sin perder referencias tecnicas utiles.

## Documentacion

La propuesta base y la documentacion de validacion para staging se encuentran en:

- `docs/propuesta-tema-senado.md`
- `docs/arquitectura-contenido-staging.md`
- `docs/guia-editorial-staging.md`
- `docs/checklist-validacion-staging.md`

## Demo estatica para GitHub Pages

La demo visual navegable del Senado quedo preparada para publicacion directa desde `docs/`.

Archivos de entrada:

- `docs/index.html`
- `docs/noticias.html`
- `docs/noticia.html`
- `docs/comision.html`
- `docs/senador.html`
- `docs/transparencia.html`
- `docs/styles.css`
- `docs/assets/img/`

Configuracion recomendada de GitHub Pages:

1. Ir a `Settings > Pages`.
2. Elegir `Deploy from a branch`.
3. Seleccionar la rama principal del repositorio.
4. Seleccionar la carpeta `/docs`.
5. Guardar la configuracion.

La carpeta `docs/` incluye `.nojekyll` para asegurar una publicacion estatica simple, sin procesamiento adicional.

## Uso local

1. Copiar `wp-content/themes/senado-institucional-base` dentro de una instalacion WordPress local o de staging.
2. Activar el tema desde `Apariencia > Temas`.
3. Configurar una portada estatica para que WordPress use `front-page.php`.
4. Asignar menus a `primary` y `footer`.
5. Publicar paginas y entradas para probar portada, internos y listados.

## Nota

La carpeta `legacy/` no forma parte del flujo activo del tema. Se conserva solo como respaldo de trabajo previo y referencia para futuras iteraciones.

# Propuesta base para la web institucional del Senado

## 1. Contexto de partida

El workspace actual no contiene un tema WordPress existente para analizar. Por ese motivo, la propuesta se construye como una base compatible con WordPress que puede instalarse como tema nuevo en un entorno de staging y, luego, adaptarse a child theme del tema productivo cuando se confirme el parent real.

## 2. Criterios de la propuesta

- Mantener WordPress como CMS y respetar el loop, plantillas nativas y menús/widgets.
- No romper contenido dinámico: la base usa APIs estándar de WordPress y evita acoplarse a plugins específicos.
- Diseñar una home institucional sobria, con bloques editoriales claros y jerarquía similar a sitios de gobierno.
- Preservar identidad visual del Senado con variables CSS dedicadas a color, tipografía y espaciado.
- Separar estructura, lógica y presentación para facilitar mantenimiento.
- Dejar el trabajo listo para staging sin tocar producción.

## 3. Estrategia recomendada de implementación

### Opción prioritaria para producción

Usar esta base en un entorno de staging y, una vez identificado el tema activo en producción, convertirla en child theme si el parent:

- ya resuelve cabecera, pie, CPTs o integraciones críticas;
- concentra lógica de plugins o shortcodes heredados;
- tiene dependencias que hoy no conviene mover.

### Opción segura para rediseño controlado

Usar esta base como tema nuevo si se busca:

- mayor limpieza estructural;
- menor deuda técnica;
- independencia del tema legado.

## 4. Estructura propuesta

```text
wp-content/
  themes/
    senado-institucional-base/
      assets/
        css/main.css
        js/theme.js
      inc/
        customizer.php
        enqueue.php
        helpers.php
        setup.php
      template-parts/
        content/
          content-excerpt.php
          content-page.php
          content-single.php
        sections/
          hero-institucional.php
          institutional-block.php
          latest-news.php
          public-agenda.php
          quick-links.php
          transparency-block.php
      404.php
      archive.php
      footer.php
      front-page.php
      functions.php
      header.php
      home.php
      index.php
      page.php
      search.php
      single.php
      style.css
      template-autoridad.php
      template-comision.php
      template-documentos.php
```

## 5. Decisiones técnicas

### WordPress nativo primero

Se usan funciones estándar como `get_header()`, `get_footer()`, `get_template_part()`, `wp_nav_menu()`, `WP_Query`, `the_title()`, `the_content()` y `dynamic_sidebar()` para mantener compatibilidad con contenido dinámico, taxonomías, entradas y páginas.

### Home desacoplada de plugins

La portada institucional usa consultas estandar a posts por categoria y contenido de pagina para evitar dependencia directa de ACF u otros plugins. Si despues se define ACF, la estructura admite enriquecer bloques sin rehacer la plantilla.

### Parciales reutilizables

Los componentes de contenido se separan en `template-parts/` para reutilizar patrones en home, listados y páginas internas.

### Lógica modular

La lógica de inicialización se mueve a `inc/` para evitar un `functions.php` monolítico.

### Identidad visual centralizada

Las variables CSS definen colores institucionales, sombras, radios y anchos máximos. Esto permite iterar diseño sin tocar las plantillas.

## 6. Archivo por archivo

### style.css

Declara el tema ante WordPress y funciona como punto de entrada mínimo del theme.

### functions.php

Carga módulos de `inc/` y mantiene el archivo principal liviano.

### inc/setup.php

Registra soportes de tema, menús y áreas de widgets.

### inc/enqueue.php

Encola CSS y JS del tema con versionado basado en fecha de modificación.

### inc/customizer.php

Expone ajustes simples en el personalizador para textos institucionales y un CTA principal.

### inc/helpers.php

Agrupa helpers reutilizables para lectura de opciones y renderizado seguro de metadatos.

### header.php

Define la cabecera institucional con branding, menú principal y acceso a utilidades.

### footer.php

Define el pie institucional con navegación secundaria y datos editoriales.

### front-page.php

Nueva home sobria. Prioriza mensaje institucional, accesos directos, noticias y agenda pública.

### home.php

Resuelve el listado de noticias del blog si WordPress usa una página de entradas separada.

### page.php

Plantilla base para páginas internas.

### template-comision.php

Base especifica para paginas institucionales de comision.

### template-autoridad.php

Base especifica para perfiles de senador o autoridad.

### template-documentos.php

Base especifica para transparencia, normativa y documentos.

### single.php

Plantilla para noticias o entradas individuales.

### archive.php

Plantilla para categorías, etiquetas y archivos cronológicos.

### search.php

Resultados de búsqueda institucionales.

### 404.php

Página de error sobria con rutas de regreso.

### index.php

Fallback final del tema según la jerarquía de WordPress.

### template-parts/content/*.php

Parciales de contenido reutilizable para páginas, listados y detalle.

### template-parts/sections/*.php

Bloques especificos de la home institucional: hero, accesos, noticias, agenda publica, bloque institucional y transparencia.

### assets/css/main.css

Contiene el sistema visual base del tema.

### assets/js/theme.js

Comportamiento mínimo del menú móvil y utilidades de interacción.

## 7. Compatibilidad con contenidos dinámicos

- Compatible con editor clásico y bloque porque `the_content()` sigue intacto.
- Compatible con menús de WordPress mediante `register_nav_menus()`.
- Compatible con widgets institucionales vía `register_sidebar()`.
- Compatible con CPTs y taxonomías existentes porque `archive.php` e `index.php` no asumen tipos cerrados.
- Compatible con plugins SEO, caché y formularios al no alterar hooks críticos.

## 8. Recomendaciones para la siguiente etapa

1. Identificar el tema activo y los plugins críticos del sitio actual.
2. Levantar staging y activar esta base solo en ese entorno.
3. Mapear tipos de contenido reales del Senado: noticias, sesiones, agenda, comisiones, autoridades, documentos.
4. Ajustar la home con datos reales y confirmar equivalencias visuales con la referencia de Presidencia.
5. Si el legado lo amerita, convertir esta base en child theme del tema productivo.

## 9. Estado de esta primera entrega

- Base de tema clasico lista para staging.
- Portada implementada en `front-page.php`.
- Header y footer institucionales definidos.
- Estilos base alineados a una identidad sobria, con dorado solo como acento.
- Plantillas `page.php`, `single.php`, `archive.php`, `index.php`, `search.php` y `404.php` listas como base.
- Templates adicionales listos para comision, autoridad y transparencia/documentos.
- Preparado para evolucion progresiva sobre WordPress nativo.

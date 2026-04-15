# Checklist de validacion para staging

## Portada

- La pagina `Inicio` esta configurada como portada estatica.
- Se ve el hero institucional.
- El bloque `Accesos principales` enlaza a paginas reales.
- El bloque `Ultimas noticias` muestra entradas publicadas o un fallback claro.
- El bloque `Agenda publica` muestra entradas con categoria `agenda` o un fallback claro.
- El bloque `Transparencia institucional` enlaza a la seccion correspondiente.
- El bloque `Institucion` muestra el contenido real de la pagina Inicio.

## Noticias

- Hay al menos 3 noticias publicadas.
- Cada noticia muestra titulo, fecha y resumen correctamente.
- Las noticias con imagen destacada se ven bien en portada y listados.
- El detalle individual abre sin errores y muestra contenido completo.
- La navegacion entre noticias funciona.

## Agenda

- Hay al menos 2 entradas en categoria `agenda`.
- El bloque de agenda en portada muestra esas entradas.
- El enlace `Ver agenda` no rompe.
- El contenido de cada actividad incluye fecha, hora o lugar dentro del cuerpo.

## Paginas institucionales

- Las paginas institucionales normales cargan con el layout interno.
- El contenido no se corta ni rompe la grilla.
- La navegacion contextual muestra paginas hermanas o hijas cuando corresponde.

## Plantillas especiales

### Comision institucional

- La plantilla se puede asignar desde atributos de pagina.
- La pagina de comision muestra titulo, contenido y sidebar.
- Si hay varias paginas hijas dentro de `Comisiones`, aparecen en el lateral.

### Senador o autoridad

- La plantilla se puede asignar correctamente.
- Si hay imagen destacada, se muestra bien.
- Si no hay imagen, aparece el placeholder sin romper la interfaz.

### Transparencia y documentos

- La plantilla se puede asignar correctamente.
- La pagina madre y las subpaginas cargan sin errores.
- El lateral contextual ayuda a navegar entre subpaginas si estan jerarquizadas.

## Navegacion

- El menu principal aparece en desktop.
- El footer se muestra correctamente.
- Los enlaces de menu apuntan a paginas existentes.
- No hay enlaces evidentes que lleven a 404 en la carga de prueba.

## Sidebar contextual

- Si no hay widgets, aparecen bloques de apoyo por defecto.
- Si hay widgets, el area lateral no queda saturada ni rota.
- Las paginas hijas o hermanas de una misma seccion se ven en `En esta seccion`.

## Responsive basico

- La portada se ve correctamente en ancho movil.
- Las tarjetas de noticias y agenda no desbordan.
- Las paginas internas colapsan a una sola columna.
- El perfil de senador o autoridad se adapta sin romper imagen ni texto.
- La navegacion entre noticias no se pisa en movil.

## Validacion final

- No hay pantallas en blanco.
- No hay secciones vacias que rompan visualmente.
- Los fallbacks son comprensibles.
- El tema sigue siendo activable y estable en staging.

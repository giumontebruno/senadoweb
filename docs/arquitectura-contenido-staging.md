# Arquitectura de contenido para staging

## Objetivo

Definir un modelo de contenido WordPress conservador para la web institucional del Senado, aprovechando primero las capacidades nativas del CMS y dejando identificado lo que mas adelante podria necesitar modelado especifico.

## Estado actual del tema

La base activa del tema ya consume correctamente:

- `page` para paginas institucionales.
- `post` para noticias y contenidos cronologicos.
- categorias para separar bloques editoriales en portada.
- menus para navegacion institucional.
- widgets para apoyo lateral en internas.

La home actual ya puede trabajar con:

- noticias desde entradas;
- agenda desde entradas en la categoria `agenda`;
- accesos principales resueltos por paginas o slugs;
- bloque institucional desde el contenido de la portada estatica;
- transparencia como acceso editorial a una pagina institucional.

## Modelo recomendado para staging

### Resolver con WordPress nativo ahora

#### Noticias

Usar `post` nativo.

Convenciones sugeridas:

- categoria `noticias` para distinguir noticias institucionales si el sitio comparte entradas con otras piezas editoriales;
- imagen destacada;
- extracto manual cuando haga falta resumen editorial;
- categorias secundarias para temas legislativos o areas institucionales.

Motivo:

- ya funciona con `home.php`, `single.php`, `archive.php` y la portada;
- evita modelado prematuro;
- mantiene compatibilidad total con RSS, busqueda, archivo y editor nativo.

#### Agenda publica

Usar `post` nativo en una categoria dedicada `agenda`.

Convenciones sugeridas:

- categoria principal `agenda`;
- fecha de publicacion como fallback inicial;
- en staging, el detalle de fecha y lugar puede escribirse dentro del contenido si aun no existe un modelo mejor.

Motivo:

- la portada ya puede consultar esta categoria;
- permite probar flujo editorial real sin depender de CPTs ni campos extra.

#### Paginas institucionales

Usar `page` nativa para:

- quienes somos;
- historia;
- funciones;
- legislacion;
- sesiones;
- contacto;
- portada estatica;
- secciones institucionales generales.

Motivo:

- encaja con el arbol jerarquico de WordPress;
- permite menus, padres/hijas y URLs institucionales estables.

#### Transparencia y documentos

Resolver inicialmente con `page` y subpaginas.

Ejemplo:

- pagina madre `Transparencia`;
- hijas `Informes`, `Presupuesto`, `Declaraciones`, `Contrataciones`, `Marco normativo`.

Motivo:

- es robusto para staging;
- ya convive con la plantilla `template-documentos.php`;
- permite probar navegacion y arquitectura sin decidir todavia un repositorio documental mas complejo.

#### Comisiones

Resolver inicialmente con `page` y plantilla asignable.

Ejemplo:

- pagina indice `Comisiones`;
- una pagina por comision usando `Comision institucional`.

Motivo:

- no asume estructura compleja;
- permite montar contenido real rapido;
- evita crear un CPT antes de conocer volumen, campos y relaciones necesarias.

#### Autoridades o senadores

Resolver inicialmente con `page` y plantilla asignable.

Ejemplo:

- pagina indice `Senadores`;
- una pagina por senador o autoridad usando `Senador o autoridad`.

Motivo:

- sirve para staging si el volumen es acotado;
- aprovecha imagen destacada, contenido y jerarquia nativa;
- no obliga a decidir todavia biografias, mandatos, partidos o comisiones asociadas como campos estructurados.

### Conviene modelar despues con CPTs o campos extra

#### Agenda estructurada

Conviene evaluar un CPT o campos extra cuando haga falta:

- fecha y hora de inicio;
- fecha y hora de fin;
- lugar;
- estado del evento;
- tipo de actividad;
- filtros por comision o area.

Senal de que ya no alcanza `post + categoria`:

- cuando haya muchas actividades con necesidad de ordenar por fecha del evento en vez de fecha de publicacion.

#### Comisiones

Conviene evaluar CPT o taxonomias cuando haga falta:

- listado automatico de integrantes;
- relacion entre comisiones y senadores;
- dictamenes o documentos vinculados;
- filtros o archivos por tipo de comision.

Senal de evolucion:

- cuando mantener una pagina manual por comision se vuelva costoso o inconsistente.

#### Senadores o autoridades

Conviene evaluar CPT o campos extra cuando haga falta:

- cargo;
- periodo;
- bancada;
- contacto;
- fotografia oficial;
- comisiones vinculadas;
- orden o agrupamiento por mesa directiva, bancadas o departamentos.

Senal de evolucion:

- cuando se necesite un directorio filtrable o relaciones entre perfiles.

#### Transparencia documental

Conviene evaluar un modelo mas estructurado cuando haga falta:

- fichas de documentos con fecha, tipo, anio y organismo;
- archivo descargable;
- filtros por categoria documental;
- buscador especifico documental.

Senal de evolucion:

- cuando el volumen documental haga inviable mantenerlo solo con paginas y enlaces manuales.

## Recomendacion de arquitectura para staging

### Fase segura inmediata

- `post` para noticias;
- categoria `agenda` para actividades;
- `page` para institucional, comisiones, senadores y transparencia;
- menus nativos para navegacion principal y footer;
- widgets para laterales institucionales;
- portada estatica con contenido editorial y bloques dinamicos.

### Convenciones editoriales sugeridas

- crear la pagina `Inicio` como portada estatica;
- crear paginas madre: `Comisiones`, `Senadores`, `Transparencia`, `Legislacion`, `Sesiones`;
- crear categoria `agenda`;
- opcionalmente crear categoria `noticias`;
- asignar plantillas especiales solo donde aporten estructura.

## Ajustes aplicados al tema para validacion

Para que staging se pueda poblar con contenido real sin CPTs:

- la portada de noticias prioriza la categoria `noticias` cuando exista;
- la portada de agenda solo toma la categoria `agenda`;
- los accesos principales resuelven paginas reales por slug;
- el sidebar contextual ahora puede mostrar paginas hijas o hermanas dentro de una misma seccion;
- el listado de noticias usa el mismo lenguaje visual que archivos y listados internos.

## Impacto en el tema actual

Con este modelo no hace falta romper el tema:

- la portada ya puede convivir con contenido real;
- las internas ya funcionan con paginas y entradas nativas;
- las plantillas especiales quedan listas como base editorial para staging.

Los futuros CPTs o campos extra, si se confirman, deberian incorporarse sin reemplazar primero el flujo nativo, sino como evolucion controlada una vez validado el portal en staging.

## Checklist para carga de contenido real en staging

1. Crear la pagina `Inicio` y definirla como portada estatica.
2. Crear paginas base: `Comisiones`, `Senadores`, `Transparencia`, `Legislacion`, `Sesiones`.
3. Crear una pagina institucional adicional, por ejemplo `Historia` o `Funciones`.
4. Crear 3 noticias como entradas normales.
5. Crear 2 actividades dentro de la categoria `agenda`.
6. Crear opcionalmente la categoria `noticias` y asignarla a esas entradas si quieren separar mejor el bloque principal.
7. Crear 1 pagina de comision con la plantilla `Comision institucional`.
8. Crear 1 pagina de senador o autoridad con la plantilla `Senador o autoridad`.
9. Crear 1 pagina de transparencia y al menos 2 subpaginas documentales con la plantilla `Transparencia y documentos`.
10. Cargar imagen destacada y extracto en noticias y perfiles cuando exista material oficial.
11. Configurar menus `primary` y `footer`.
12. Configurar widgets en `Sidebar institucional`.
13. Revisar portada, noticia individual, archivo de noticias, paginas especiales, sidebar contextual y navegacion movil.

## Candidatas para segunda fase de modelado

Funcionan bien con WordPress nativo:

- noticias institucionales;
- agenda inicial con volumen acotado;
- paginas institucionales;
- transparencia por paginas y subpaginas;
- perfiles y comisiones mientras el volumen sea manejable.

Quedan candidatas para una segunda fase:

- agenda cuando necesite fecha de evento estructurada;
- comisiones cuando necesiten relaciones y listados automaticos;
- senadores o autoridades cuando requieran directorio filtrable;
- transparencia cuando el volumen documental exija fichas, filtros o buscador especifico.

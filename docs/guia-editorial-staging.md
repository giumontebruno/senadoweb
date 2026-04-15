# Guia editorial para cargar contenido en staging

## Antes de empezar

Ingrese al panel de WordPress del entorno de staging con un usuario con permisos de edicion o administracion.

Antes de cargar contenido, confirme que el tema activo sea `Senado Institucional Base`.

## Paso 1: crear la estructura principal de paginas

En el menu lateral vaya a `Paginas > Anadir nueva` y cree estas paginas:

1. `Inicio`
2. `Comisiones`
3. `Senadores`
4. `Transparencia`
5. `Legislacion`
6. `Sesiones`
7. `Historia` o `Funciones`

Recomendaciones:

- use titulos cortos y claros;
- revise el enlace permanente antes de publicar;
- mantenga una jerarquia institucional simple.

## Paso 2: definir la portada

Vaya a `Ajustes > Lectura`.

1. Active `Una pagina estatica`.
2. En `Portada`, elija la pagina `Inicio`.
3. Guarde cambios.

La portada del tema usa `front-page.php`, por lo que esa pagina sera la base del home institucional.

## Paso 3: cargar contenido en la pagina Inicio

Edite la pagina `Inicio`.

Use el contenido principal de la pagina para escribir:

- un mensaje institucional breve;
- una introduccion al rol del Senado;
- uno o dos accesos editoriales relevantes;
- un cierre corto con enfoque ciudadano o institucional.

Ese contenido se mostrara en el bloque `Institucion` de la portada.

## Paso 4: crear categorias necesarias

Vaya a `Entradas > Categorias`.

Cree estas categorias:

1. `agenda`
2. `noticias` opcional, pero recomendada si quieren separar noticias institucionales del resto de las entradas

Use los slugs:

- `agenda`
- `noticias`

## Paso 5: cargar noticias

Vaya a `Entradas > Anadir nueva` y cree al menos 3 noticias.

Para cada noticia:

1. cargue un titulo claro;
2. escriba el contenido completo;
3. si la categoria `noticias` existe, asignela;
4. cargue una imagen destacada;
5. complete el extracto manual si quiere controlar el resumen en listados;
6. publique.

Buenas practicas:

- usar imagen destacada horizontal;
- completar el extracto cuando el primer parrafo sea demasiado largo;
- evitar titulos excesivamente extensos.

## Paso 6: cargar agenda

Vaya a `Entradas > Anadir nueva` y cree al menos 2 actividades.

Para cada actividad:

1. cargue un titulo descriptivo;
2. asigne la categoria `agenda`;
3. escriba en el contenido la fecha, hora, lugar y detalle de la actividad;
4. cargue imagen destacada solo si existe una imagen institucional adecuada;
5. publique.

Importante:

- en esta fase la agenda usa WordPress nativo, por eso la fecha del evento puede ir dentro del contenido;
- mas adelante podria modelarse de forma mas estructurada si hiciera falta.

## Paso 7: crear una pagina de comision

Vaya a `Paginas > Anadir nueva`.

1. cree una pagina hija dentro de `Comisiones`;
2. asigne la plantilla `Comision institucional`;
3. cargue nombre de la comision como titulo;
4. agregue contenido base: funciones, integrantes, contacto o actividad;
5. publique.

Sugerencia:

- si van a crear varias comisiones, ordénenlas con `Atributos de pagina > Orden`.

## Paso 8: crear una pagina de senador o autoridad

Vaya a `Paginas > Anadir nueva`.

1. cree una pagina hija dentro de `Senadores`;
2. asigne la plantilla `Senador o autoridad`;
3. use el nombre completo como titulo;
4. cargue una imagen destacada oficial si esta disponible;
5. escriba una ficha breve: cargo, periodo, trayectoria o funciones;
6. publique.

Si no hay imagen, la plantilla mostrara un placeholder institucional.

## Paso 9: crear transparencia y documentos

Vaya a `Paginas > Anadir nueva`.

1. edite o cree la pagina `Transparencia`;
2. asigne la plantilla `Transparencia y documentos` cuando corresponda;
3. cree subpaginas como:
   - `Informes`
   - `Presupuesto`
   - `Declaraciones`
4. en cada una cargue texto, enlaces o listados de documentos;
5. publique.

Sugerencia:

- mantenga una pagina madre clara y use subpaginas para ordenar la informacion.

## Paso 10: configurar menus

Vaya a `Apariencia > Menus`.

Cree o edite:

1. `Menu principal`
2. `Menu footer`

En `Menu principal`, agregue:

- Inicio
- Sesiones
- Legislacion
- Comisiones
- Senadores
- Transparencia

En `Menu footer`, agregue accesos institucionales complementarios.

Despues, asigne cada menu a su ubicacion correspondiente:

- `primary`
- `footer`

## Paso 11: configurar widgets

Vaya a `Apariencia > Widgets`.

Busque el area `Sidebar institucional`.

Agregue widgets simples, por ejemplo:

- navegacion personalizada;
- texto con informacion de contacto;
- enlaces rapidos;
- listado de paginas de una seccion.

Si no se agregan widgets, el tema mostrara bloques de apoyo por defecto.

## Paso 12: revisar resultado

Revise:

- portada;
- noticias;
- agenda;
- paginas institucionales;
- comisiones;
- perfiles;
- transparencia;
- menus;
- lateral contextual.

## Contenido minimo recomendado para una validacion realista

- 1 pagina `Inicio`
- 5 paginas institucionales base
- 3 noticias
- 2 entradas de agenda
- 1 pagina de comision
- 1 pagina de senador o autoridad
- 1 pagina madre de transparencia
- 2 subpaginas documentales

## Errores comunes a evitar

- no cargar imagen destacada en noticias importantes;
- olvidar asignar la categoria `agenda` a actividades;
- publicar perfiles o comisiones fuera de su pagina madre;
- no asignar plantilla especial cuando corresponde;
- dejar menus sin asignar;
- cargar textos demasiado extensos sin subtitulos o separacion.

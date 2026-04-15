# Inventario del sitio actual del Senado de Paraguay

## Alcance y metodo

Este documento releva la estructura observable de la web publica actual del Senado de Paraguay a partir de:

- la home publica `https://www.senado.gov.py/`;
- el mapa del sitio;
- paginas de primer y segundo nivel del menu principal;
- listados y fichas representativas de noticias, agenda, senadores, comisiones y secciones institucionales;
- enlaces visibles a micrositios y sistemas externos.

El enfoque fue:

1. partir desde la home;
2. seguir enlaces internos visibles y relevantes;
3. profundizar en subniveles representativos;
4. identificar patrones de contenido y layout;
5. proponer un mapeo de migracion a WordPress.

## Limitaciones

- No se hizo un crawl automatizado exhaustivo de todas las URLs publicas del dominio.
- Algunas secciones visibles enlazan a sistemas externos o a contenidos que dependen de otras plataformas.
- Algunas paginas existen como contenedores o indices, pero el contenido profundo completo no fue reconstruido item por item.
- Cuando una estructura no pudo verificarse completamente, se indica de forma explicita y no se infiere contenido no observado.

## Lectura ejecutiva

La web actual combina al menos cuatro capas:

1. sitio institucional principal en `senado.gov.py`;
2. sistema legislativo externo `silpy.congreso.gov.py`;
3. micrositios o plataformas auxiliares para digesto, audios, orden del dia, documentos y datos;
4. paginas de contenido editorial y documental montadas sobre rutas heterogeneas dentro del mismo dominio.

La conclusion principal para migracion es:

- el sitio principal puede reordenarse sobre WordPress;
- los sistemas legislativos y documentales especializados conviene tratarlos como integraciones externas o de segunda fase;
- hay mezcla de navegacion institucional, noticias, agenda, documentos, formularios y accesos rapidos en la home, lo que incrementa complejidad y confusion.

## Mapa jerarquico del sitio

### 1. Home

- `https://www.senado.gov.py/`
  - cabecera con datos de contacto
  - logo e identidad institucional
  - menu principal multinivel
  - slider o bloque visual destacado
  - accesos rapidos a sistemas
  - agenda legislativa
  - destacados
  - bloque de sesiones parlamentarias
  - bloques de noticias
  - accesos a comisiones especiales
  - bloque de transparencia y recursos especiales
  - redes sociales
  - footer
  - mapa del sitio

### 2. Menu principal

- Senado
  - La Camara
    - Mesa Directiva
    - Expresidentes
    - Aspectos Legales
  - Senadores
    - Nomina Alfabetica
    - Nomina por Partido/Movimiento
    - Bancadas
    - Sentencia del TSJE
  - Comisiones
    - Asesoras
      - Permanentes
      - Bicamerales, Nacionales y Especiales
    - Especiales
      - de Amistad
      - Bicamerales, Nacionales y Especiales
    - Informes de Gestion de las Comisiones
  - Institucional
    - La Institucion
      - El Poder Legislativo
      - Mision y Vision
      - Plan Estrategico PEI
      - Autoridades Administrativas
      - Estructura Organica y Funciones
    - Dependencias Generales
    - Llamados y Licitaciones
    - Documentos e Informes
      - MECIP
      - Regimen Interno de RRHH
      - Auditoria CGR
      - Memorias
      - Informes Generales

- Actividad Legislativa
  - Secretaria General
  - SILpy - Sistema de Informacion Legislativa
  - Digesto Legislativo
  - Diario de Sesiones
    - Boletines
    - Audios
  - Guias y Materiales

- Contactos

### 3. Navegacion secundaria y accesos rapidos

- Home:
  - Webmail
  - SenadoTV / sesion en vivo
  - Normas de Requisitos Minimos
  - Constitucion de la Republica del Paraguay
  - Comision Bicameral de Presupuesto
  - Informes s/ Ley 5189/14
  - Datos Abiertos Legislativos
  - Tablero de Control del Congreso Nacional
  - Convenio - Proyecto

- Footer:
  - MECIP
  - Centro de Bienestar Infantil del Congreso Nacional
  - Historico de Eventos
  - Enlaces de Interes
  - BACN
  - Camara de Diputados
  - Comision Permanente de la Camara de Senadores
  - CONADERNA
  - Comision Bicameral de Presupuesto
  - Comision Nacional de Reforma Penal
  - Mapa del Sitio
  - Consultas y Contactos

## Inventario de URLs observadas

## Home y base

| Seccion | URL | Tipo observado |
|---|---|---|
| Home | `https://www.senado.gov.py/` | portada institucional y editorial |
| Mapa del sitio | `https://www.senado.gov.py/index.php/mapa-del-sitio?id=1&view=html` | arbol de navegacion |
| Contactos | `https://www.senado.gov.py/index.php/contactos` | pagina informativa |

## Senado > La Camara

| Seccion | URL | Tipo observado |
|---|---|---|
| Mesa Directiva | `https://www.senado.gov.py/index.php/senado/autoridades/mesa-directiva` | ficha institucional / autoridades |
| Expresidentes | `https://www.senado.gov.py/index.php/senado/autoridades/expresidentes` | listado historico |
| Aspectos Legales | `https://www.senado.gov.py/index.php/senado/autoridades/aspectos-legales` | pagina institucional, contenido no visible en la captura consultada |

## Senado > Senadores

| Seccion | URL | Tipo observado |
|---|---|---|
| Nomina alfabetica | `https://www.senado.gov.py/index.php/senado/senadores/nomina-alfabetica` | listado de fichas |
| Nomina por partido | `https://www.senado.gov.py/index.php/senado/senadores/nomina-por-partido` | listado agrupado |
| Bancadas | `https://www.senado.gov.py/index.php/senado/senadores/bancadas` | indice o pagina de agrupacion |
| Sentencia del TSJE | `https://www.senado.gov.py/index.php/senado/senadores/sentencia-del-tsje` | pagina documental |

## Senado > Comisiones

| Seccion | URL | Tipo observado |
|---|---|---|
| Permanentes | `https://www.senado.gov.py/index.php/senado/comisiones/asesoras/permanentes` | listado de comisiones |
| Bicamerales, nacionales y especiales | `https://www.senado.gov.py/index.php/senado/comisiones/asesoras/bicamerales-nacionales-y-especiales` | listado de comisiones |
| de Amistad | `https://www.senado.gov.py/index.php/senado/comisiones/especiales/de-amistad` | listado |
| Informes de gestion | `https://www.senado.gov.py/index.php/senado/comisiones/informes-de-gestion` | listado filtrable |

## Senado > Institucional

| Seccion | URL | Tipo observado |
|---|---|---|
| El Poder Legislativo | `https://www.senado.gov.py/index.php/senado/institucional/la-institucion/el-poder-legislativo` | pagina informativa |
| Mision y Vision | `https://www.senado.gov.py/index.php/senado/institucional/la-institucion/mision-y-vision` | pagina visual / imagen |
| Plan Estrategico PEI | `https://www.senado.gov.py/index.php/senado/institucional/la-institucion/plan-estrategico-pei` | pagina documental |
| Autoridades Administrativas | `https://www.senado.gov.py/index.php/senado/institucional/la-institucion/autoridades-administrativas` | ficha institucional |
| Estructura Organica y Funciones | `https://www.senado.gov.py/index.php/senado/institucional/la-institucion/estructura-organica-y-funciones` | pagina documental |
| Dependencias Generales | `https://www.senado.gov.py/index.php/senado/institucional/direcciones-generales` | listado institucional |
| Llamados y Licitaciones | `https://www.senado.gov.py/index.php/senado/institucional/llamados-y-licitaciones` | pagina de derivacion a sistema externo |
| MECIP | `https://www.senado.gov.py/index.php/senado/institucional/documentos-e-informes/mecip` | pagina explicativa |
| Regimen Interno de RRHH | `https://www.senado.gov.py/index.php/senado/institucional/documentos-e-informes/regimen-interno-de-rrhh` | pagina con enlace documental |
| Auditoria CGR | `https://www.senado.gov.py/index.php/senado/institucional/documentos-e-informes/auditoria-cgr` | pagina documental |
| Memorias | `https://www.senado.gov.py/index.php/senado/institucional/documentos-e-informes/memorias` | contenedor documental |
| Informes Generales | `https://www.senado.gov.py/index.php/senado/institucional/documentos-e-informes/informes-generales` | contenedor documental |

## Actividad Legislativa

| Seccion | URL | Tipo observado |
|---|---|---|
| Secretaria General | `https://www.senado.gov.py/index.php/actividad-legislativa/secretaria-general` | listado de sesiones |
| Guias y Materiales | `https://www.senado.gov.py/index.php/actividad-legislativa/materiales` | repositorio de guias |
| SILpy | `https://silpy.congreso.gov.py/` | sistema externo legislativo |
| Digesto | `https://digesto.senado.gov.py/` | sistema externo documental |
| Audios | `https://audio.senado.gov.py/` | sistema externo / micrositio |
| Orden del dia digital | `https://odd.senado.gov.py/` | sistema externo |

## Prensa y agenda

| Seccion | URL | Tipo observado |
|---|---|---|
| Agenda Legislativa | `https://www.senado.gov.py/index.php/noticias/agenda-legislativa` | listado filtrable |
| Noticias Presidencia | `https://www.senado.gov.py/index.php/noticias/noticias-presidencia` | listado filtrable |
| Noticias Comisiones | `https://www.senado.gov.py/index.php/noticias/noticias-comisiones` | listado filtrable |
| Noticias Generales | `https://www.senado.gov.py/index.php/noticias/noticias-generales` | listado filtrable |
| Ficha agenda ejemplo | `https://www.senado.gov.py/index.php/noticias/agenda-legislativa/16455-presidencia-68-2026-03-30-10-12-55` | ficha individual de agenda |
| Noticia presidencia ejemplo | `https://www.senado.gov.py/index.php/noticias/noticias-presidencia/16501-senado-estudiara-proyecto-sobre-caja-parlamentaria-2026-04-13-16-36-42` | noticia individual |
| Noticia comisiones ejemplo | `https://www.senado.gov.py/index.php/noticias/noticias-comisiones/16478-recomiendan-aprobar-acuerdos-para-fortalecer-el-comercio-internacional-2026-04-08-13-31-49` | noticia individual |

## Accesos y paginas especiales visibles desde la home

| Seccion | URL | Tipo observado |
|---|---|---|
| SenadoTV | `https://www.senado.gov.py/index.php/menu-contenido/listado-de-categoria-contenido/198-sesion-en-vivo` | pagina de acceso a streaming |
| Normas de Requisitos Minimos | `https://www.senado.gov.py/index.php/menu-contenido/listado-de-categoria-contenido/16-informacion-institucional/8378-normas-requisitos-minimos` | pagina informativa-documental |
| Constitucion de la Republica del Paraguay | `https://www.senado.gov.py/index.php/menu-contenido/listado-de-categoria-contenido/16-informacion-institucional/11470-constitucion-republica-paraguay-junio-2023` | pagina documental |
| Informes s/ Ley 5189/14 | `https://www.senado.gov.py/index.php/ley-5189-14/106-informe-ley-5189` | portal de transparencia / indice |
| Tablero de Control del Congreso Nacional | `https://www.senado.gov.py/index.php/menu-contenido/listado-de-categoria-contenido/222-categoria-tablero-control` | micrositio informativo |
| Convenio - Proyecto | `https://www.senado.gov.py/index.php/menu-contenido/listado-de-categoria-contenido/16-informacion-institucional/15702-convenio-proyecto-27082025` | pagina de contenido |

## Sistemas externos y micrositios detectados

| Nombre | URL | Relacion con el sitio principal |
|---|---|---|
| SILpy | `https://silpy.congreso.gov.py/` | sistema legislativo principal externo |
| Digesto Legislativo | `https://digesto.senado.gov.py/` | sistema normativo/documental |
| Orden del dia digital | `https://odd.senado.gov.py/` | sistema de sesiones |
| Audios | `https://audio.senado.gov.py/` | sistema de diarios de sesiones / audios |
| Webmail | `https://correo.senado.gov.py/` | acceso administrativo |
| Nube Senado | `https://nube.senado.gov.py/` | repositorio documental |
| Datos Abiertos Legislativos | `https://datos.congreso.gov.py/` | sistema externo de datos |
| Comision Bicameral de Presupuesto | `https://bicameral.congreso.gov.py/` | micrositio externo |
| BACN | `https://www.bacn.gov.py/` | sitio externo relacionado |
| Camara de Diputados | `https://www.diputados.gov.py/` | sitio externo institucional |
| CONADERNA | `https://www.conaderna.gov.py/` | sitio externo |
| YouTube | `https://www.youtube.com/` | streaming y video |
| Google Forms | `https://forms.gle/` | formularios externos |
| DNCP | `https://www.contrataciones.gov.py/` | contrataciones y licitaciones |
| Sesiones / materiales | `https://sesiones.senado.gov.py/` | recursos legislativos |
| FlipHTML5 | `https://online.fliphtml5.com/` | ebooks embebidos o enlazados |

## Clasificacion de contenido

| Tipo de seccion | Secciones observadas | Clasificacion |
|---|---|---|
| Institucional | Mesa Directiva, Expresidentes, El Poder Legislativo, Mision y Vision, Dependencias, Autoridades, Contactos | institucional |
| Legislativo | Secretaria General, SILpy, Digesto, Orden del dia, Diario de Sesiones, Guias y Materiales | legislativo |
| Noticias | Noticias Presidencia, Noticias Comisiones, Noticias Generales, Destacados | noticias |
| Agenda | Agenda Legislativa, agenda destacada en home | agenda |
| Comisiones | Permanentes, Bicamerales, de Amistad, Informes de Gestion | comisiones |
| Senadores / autoridades | Nomina alfabetica, nomina por partido, bancada, perfiles SILpy, mesa directiva | senadores / autoridades |
| Transparencia / documentos | MECIP, Regimen RRHH, Auditoria CGR, Memorias, Informes Generales, Ley 5189/14, Tablero de Control, licitaciones | transparencia / documentos |
| Servicios y externos | Webmail, formularios, redes, streaming, datos abiertos, BACN, Diputados | servicios / externos |

## Tipos de contenido detectados

## 1. Paginas informativas

Ejemplos:

- El Poder Legislativo
- Mision y Vision
- Contactos
- Aspectos Legales
- Dependencias Generales

Patron:

- breadcrumb;
- titulo H2 principal;
- acciones de imprimir y correo;
- texto o imagen principal;
- pie de pagina estandar.

## 2. Listados simples

Ejemplos:

- Expresidentes;
- Dependencias Generales;
- Permanentes;
- Nomina por Partido;
- Guias y Materiales.

Patron:

- titulo de seccion;
- listado vertical o grilla simple;
- a veces con imagen, a veces solo enlaces;
- sin filtros avanzados.

## 3. Listados filtrables de articulos

Ejemplos:

- Agenda Legislativa;
- Noticias Presidencia;
- Noticias Comisiones;
- Noticias Generales;
- Informes de Gestion de las Comisiones.

Patron:

- formulario de filtro por titulo;
- selector de cantidad a mostrar;
- tabla o lista con titulo y fecha;
- acceso a ficha individual.

Esto indica un motor de categorias o articulos reutilizado.

## 4. Fichas individuales

Ejemplos:

- noticia individual;
- item de agenda;
- perfil de senador en SILpy;
- ficha de comision en SILpy.

Patron de noticia/agenda en sitio principal:

- breadcrumb;
- categoria visible;
- fecha;
- titulo;
- bloque de texto principal;
- ocasional imagen;
- iconos de compartir.

Patron de perfil/ficha en SILpy:

- datos estructurados;
- periodos;
- comisiones;
- trayectoria;
- contactos;
- pestañas o submodulos.

## 5. Paginas hibridas o portales de acceso

Ejemplos:

- Llamados y Licitaciones;
- SenadoTV;
- Ley 5189/14;
- Tablero de Control;
- Constitucion de la Republica del Paraguay.

Patron:

- breve texto introductorio;
- multiples enlaces o botones a recursos externos o PDFs;
- mezcla de contenido editorial y acceso documental.

## Patrones de layout observados

## Layout 1: home institucional compleja

Bloques observados:

- header superior con contacto;
- menu principal multinivel;
- slider o carrusel;
- agenda legislativa;
- destacados;
- sesiones parlamentarias;
- noticias por categoria;
- accesos a comisiones especiales;
- recursos institucionales, transparencia y redes;
- footer cargado de enlaces.

Problema:

- demasiados tipos de contenido compiten en una sola portada.

## Layout 2: pagina de contenido simple

Bloques:

- breadcrumb;
- titulo;
- acciones de imprimir / correo;
- contenido;
- redes;
- footer.

Se usa en paginas institucionales, documentales y de agenda.

## Layout 3: listado tabular o filtrable

Bloques:

- breadcrumb;
- titulo;
- bloque de filtros;
- tabla/lista;
- paginacion implícita o selector de cantidad.

Se usa en:

- noticias por categoria;
- agenda;
- informes de comision.

## Layout 4: ficha estructurada externa

Bloques:

- cabecera de sistema externo;
- datos estructurados;
- pestañas o modulos;
- relaciones con comisiones, periodos o expedientes.

Se usa en SILpy para:

- perfil de senador;
- ficha de comision.

## Deteccion de relaciones entre secciones

- El sitio principal deriva a SILpy para datos mas estructurados de legisladores y comisiones.
- La home mezcla noticias del sitio principal con accesos a sistemas externos.
- La seccion Secretaria General se apoya fuertemente en enlaces a SILpy para sesiones.
- Llamados y Licitaciones no se gestiona dentro del sitio, sino que deriva a DNCP.
- Transparencia esta fragmentada entre:
  - paginas del sitio;
  - nube / repositorios;
  - Ley 5189/14;
  - tablero de control;
  - datos abiertos;
  - formularios externos.

## Deteccion de micrositios y sistemas externos

## Confirmados

- SILpy
- Digesto Legislativo
- Audios
- Orden del dia digital
- SenadoTV / YouTube
- Nube Senado
- Datos abiertos
- Bicameral de presupuesto
- BACN
- DNCP

## Implicancia para migracion

No todo debe migrarse a WordPress.

Conviene separar:

- contenido editorial e institucional migrable;
- sistemas transaccionales o legislativos que deben integrarse;
- repositorios documentales que pueden mantenerse externos o migrarse en fase posterior.

## Problemas de arquitectura de informacion detectados

## 1. Mezcla de dominios y plataformas

El usuario salta entre:

- `senado.gov.py`
- `silpy.congreso.gov.py`
- `digesto.senado.gov.py`
- `audio.senado.gov.py`
- `odd.senado.gov.py`
- `nube.senado.gov.py`
- otros dominios externos

Impacto:

- experiencia fragmentada;
- lenguaje visual inconsistente;
- dificultad para mantener una navegacion clara.

## 2. Home excesivamente cargada

La portada mezcla:

- agenda;
- slider;
- noticias;
- sesiones;
- comisiones;
- transparencia;
- accesos administrativos;
- enlaces externos.

Impacto:

- baja jerarquia editorial;
- ruido visual;
- menor claridad para usuarios ciudadanos.

## 3. Duplicacion de navegacion

El menu principal aparece repetido en footer y en mapa del sitio, y varias rutas se repiten desde bloques diferentes.

Impacto:

- percepcion de redundancia;
- mayor costo de mantenimiento.

## 4. Heterogeneidad de patrones URL

Se observan al menos estos patrones:

- `/index.php/senado/...`
- `/index.php/noticias/...`
- `/index.php/actividad-legislativa/...`
- `/index.php/menu-contenido/listado-de-categoria-contenido/...`
- `/index.php/ley-5189-14/...`
- sistemas externos completos

Impacto:

- estructura poco intuitiva;
- baja legibilidad de taxonomia;
- mas dificil de mapear y redireccionar.

## 5. Transparencia atomizada

La informacion de transparencia aparece distribuida en varias secciones y plataformas.

Impacto:

- dificil acceso para el ciudadano;
- duplicacion de puertas de entrada;
- mayor dificultad de gobernanza editorial.

## 6. Datos estructurados fuera del sitio principal

Las fichas ricas de senadores y comisiones estan principalmente en SILpy, no en el sitio principal.

Impacto:

- sitio principal queda como capa de navegacion y contenidos ligeros;
- la migracion completa requiere estrategia de integracion.

## Oportunidades de simplificacion

## 1. Reorganizar la navegacion en macrosecciones

Propuesta:

- Senado
- Actividad Legislativa
- Noticias y Agenda
- Comisiones
- Senadores
- Transparencia
- Contacto

## 2. Separar claramente tres universos

- contenido institucional;
- contenido periodistico/editorial;
- sistemas y servicios externos.

## 3. Unificar transparencia

Reunir en un unico hub:

- licitaciones;
- informes institucionales;
- ley 5189/14;
- tablero de control;
- datos abiertos;
- declaraciones y rendiciones.

## 4. Simplificar la home

Home propuesta a futuro:

- hero institucional;
- accesos principales;
- noticias destacadas;
- agenda;
- sesiones y actividad legislativa;
- transparencia;
- footer.

## 5. Reducir dependencia visible de rutas tecnicas

Las rutas tipo `menu-contenido/listado-de-categoria-contenido` o `index.php/...` deberian ocultarse detras de slugs claros en la migracion.

## Propuesta de mapeo a WordPress

## Contenido resoluble con WordPress nativo

| Tipo de contenido | WordPress nativo sugerido | Comentario |
|---|---|---|
| Paginas institucionales | `page` | ideal para estructura jerarquica |
| Noticias | `post` + categorias | presidencia, comisiones, generales |
| Agenda legislativa inicial | `post` + categoria `agenda` | valido en fase 1 |
| Hub de transparencia | `page` + subpaginas | valido en staging |
| Guias y materiales | `page` o `post` segun frecuencia | si son pocas, puede ser pagina |
| Menus principales | menus nativos | sin problema |
| Footer y accesos | menus + widgets | suficiente |

## Contenido que probablemente requiere modelado posterior

| Tipo de contenido | Candidato futuro | Motivo |
|---|---|---|
| Senadores / autoridades | CPT + campos | cargo, bancada, contacto, periodos, relaciones |
| Comisiones | CPT + taxonomias o relaciones | integrantes, documentos, dictamenes, tipo de comision |
| Agenda estructurada | CPT o campos personalizados | fecha/hora/lugar del evento |
| Transparencia documental | CPT o repositorio documental | tipo de documento, periodo, organismo, descarga |
| Sesiones parlamentarias | integracion o CPT especializado | orden del dia, actas, audios, videos, resultados |
| Expedientes y leyes | integracion con SILpy / Digesto | alta complejidad, no conviene rehacer de entrada |

## Mapeo detallado por seccion

### Senado > La Camara

- `page` para:
  - Mesa Directiva
  - Expresidentes
  - Aspectos Legales

Comentario:

- si Mesa Directiva y Expresidentes requieren fichas mas ricas, se puede resolver en fase 1 con bloques o subpaginas;
- solo si necesitan historicos complejos convendria CPT.

### Senado > Senadores

- fase 1:
  - pagina indice `Senadores`
  - una pagina por senador o autoridad con plantilla especifica

- fase 2:
  - CPT `senador`
  - taxonomia `bancada` o `partido`
  - campos: periodo, telefono, correo, foto, cargo, bio

### Senado > Comisiones

- fase 1:
  - pagina indice `Comisiones`
  - una pagina por comision
  - subpaginas o menus auxiliares

- fase 2:
  - CPT `comision`
  - taxonomia `tipo de comision`
  - relaciones con senadores y documentos

### Institucional

- `page` y subpaginas.

No requiere CPT en una primera migracion.

### Noticias

- `post`
- categorias:
  - `presidencia`
  - `comisiones`
  - `generales`

### Agenda

- fase 1:
  - `post` en categoria `agenda`

- fase 2:
  - CPT `agenda`
  - campos: fecha, hora, lugar, tipo, organizador

### Transparencia y documentos

- fase 1:
  - pagina `Transparencia`
  - subpaginas:
    - Informes
    - Licitaciones
    - Ley 5189/14
    - MECIP
    - Datos abiertos
    - Tablero de control

- fase 2:
  - CPT `documento`
  - taxonomia `tipo_documental`
  - campos: fecha, periodo, dependencia, archivo, enlace externo

### Actividad Legislativa

- fase 1:
  - pagina hub con enlaces claros a sistemas existentes

- fase 2:
  - evaluar integraciones selectivas con SILpy, Digesto, audios y orden del dia

## Recomendacion de migracion por fases

## Fase 1: migracion del front institucional y editorial

Migrar a WordPress:

- home;
- paginas institucionales;
- noticias;
- agenda basica;
- comisiones y perfiles en forma simplificada;
- hub de transparencia;
- hubs de enlaces a sistemas externos.

## Fase 2: modelado estructurado

Modelar con CPTs o integraciones:

- senadores;
- comisiones;
- agenda avanzada;
- documentos;
- sesiones;
- integracion de datos legislativos.

## Fase 3: integracion profunda

Evaluar:

- sincronizacion con SILpy;
- unificacion de autenticacion o navegacion;
- consolidacion de repositorios documentales.

## Conclusion

El sitio actual del Senado muestra una arquitectura de informacion amplia pero fragmentada, con una capa institucional visible en `senado.gov.py` y una fuerte dependencia de sistemas externos para la informacion legislativa estructurada.

Para una futura migracion y rediseño sobre WordPress, lo mas razonable es:

1. migrar primero la capa institucional, editorial y de navegacion;
2. consolidar noticias, agenda, transparencia y paginas institucionales;
3. mantener integrados, pero separados, los sistemas complejos como SILpy, Digesto, audios y orden del dia;
4. decidir en una segunda fase que areas merecen CPTs, taxonomias y campos estructurados.

El resultado esperado no deberia ser una copia literal del sitio actual, sino una version simplificada, jerarquica y coherente, que preserve el contenido esencial y reduzca la complejidad de uso y mantenimiento.

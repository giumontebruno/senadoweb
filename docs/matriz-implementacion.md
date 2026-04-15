# Matriz de implementacion para WordPress

## Objetivo

Traducir el sitemap objetivo del nuevo sitio del Senado a una hoja de trabajo operativa para su construccion en staging sobre WordPress, usando el tema actual como base y sin introducir complejidad innecesaria en esta fase.

## Criterios de implementacion

- usar WordPress nativo siempre que sea razonable;
- aprovechar el tema actual y sus templates existentes;
- reservar para fase 2 solo lo que requiera modelado estructurado;
- mantener una arquitectura clara, sobria e institucional;
- no introducir plugins ni dependencias no confirmadas.

## Matriz de implementacion

| Seccion | Nivel sitemap | Accion | Tipo WP recomendado | Nativo o fase 2 | Template del tema | Estado del template | Observaciones |
|---|---|---|---|---|---|---|---|
| Inicio | 1 | MIGRAR | `page` | nativo | `front-page.php` | existe | usar pagina estatica `Inicio` |
| Senado | 1 | MIGRAR | `page` padre | nativo | `page.php` | existe | hub institucional |
| La Camara | 2 | MIGRAR | `page` | nativo | `page.php` | existe | pagina indice con enlaces a hijas |
| Mesa Directiva | 3 | MIGRAR | `page` | nativo | `page.php` | existe | si necesita fichas mas ricas, evaluar fase 2 |
| Expresidentes | 3 | MIGRAR | `page` | nativo con limite | `page.php` | existe | puede resolverse con listado manual en fase 1 |
| Aspectos Legales | 3 | MIGRAR | `page` | nativo | `page.php` | existe | contenido estable |
| Institucion | 2 | MIGRAR | `page` padre | nativo | `page.php` | existe | pagina hub institucional |
| El Poder Legislativo | 3 | MIGRAR | `page` | nativo | `page.php` | existe | pagina informativa |
| Mision y Vision | 3 | MIGRAR | `page` | nativo | `page.php` | existe | pagina informativa |
| Plan Estrategico | 3 | MIGRAR | `page` | nativo | `template-documentos.php` o `page.php` | existe | usar template de documentos si hay muchos enlaces |
| Estructura Organica y Funciones | 3 | MIGRAR | `page` | nativo | `template-documentos.php` o `page.php` | existe | recomendable como documento institucional |
| Autoridades Administrativas | 2 | MIGRAR | `page` | nativo con limite | `page.php` | existe | si luego requiere fichas, fase 2 |
| Dependencias Generales | 2 | MIGRAR | `page` | nativo | `page.php` | existe | listado simple o grilla editorial |
| Senadores | 1 | MIGRAR | `page` padre | nativo con limite | `page.php` | existe | hub de seccion |
| Nomina de Senadores | 2 | MIGRAR | `page` + hijas | nativo con limite | `page.php` + `template-autoridad.php` | existe | pagina indice + una pagina por perfil |
| Bancadas | 2 | MIGRAR | `page` | nativo con limite | `page.php` | existe | listado manual en fase 1 |
| Marco Legal Electoral | 2 | MIGRAR | `page` | nativo | `template-documentos.php` o `page.php` | existe | contenido documental |
| Comisiones | 1 | MIGRAR | `page` padre | nativo con limite | `page.php` | existe | hub de seccion |
| Comisiones Permanentes | 2 | MIGRAR | `page` + hijas | nativo con limite | `page.php` + `template-comision.php` | existe | indice + una pagina por comision |
| Comisiones Especiales | 2 | MIGRAR | `page` + hijas | nativo con limite | `page.php` + `template-comision.php` | existe | idem |
| Comisiones Bicamerales y Nacionales | 2 | MIGRAR | `page` + hijas | nativo con limite | `page.php` + `template-comision.php` | existe | idem |
| Informes de Gestion | 2 | MIGRAR | `page` o `post` | nativo con limite | `template-documentos.php` | existe | si crece mucho, fase 2 |
| Actividad Legislativa | 1 | MIGRAR | `page` padre | nativo | `page.php` | existe | hub con accesos a agenda, secretaria y sistemas |
| Agenda Legislativa | 2 | MIGRAR | `post` + categoria `agenda` | nativo ahora / fase 2 despues | `home.php`, `archive.php`, `single.php` | existen | usar categoria `agenda` |
| Noticias Legislativas | 2 | SIMPLIFICAR | `post` + categorias | nativo | `home.php`, `archive.php`, `single.php` | existen | absorber dentro de `Noticias` |
| Secretaria General | 2 | MIGRAR | `page` | nativo | `page.php` | existe | hub de enlaces a sesiones, orden del dia y materiales |
| Sesiones y Materiales | 2 | INTEGRAR | `page` hub + enlaces externos | fase 2 parcial | `page.php` | existe | no modelar todavia en WP |
| Transparencia | 1 | MIGRAR | `page` padre | nativo | `template-documentos.php` o `page.php` | existe | hub principal de transparencia |
| Informes Institucionales | 2 | MIGRAR | `page` | nativo con limite | `template-documentos.php` | existe | listado de informes y memorias |
| MECIP | 2 | MIGRAR | `page` | nativo | `template-documentos.php` | existe | contenido documental |
| Licitaciones | 2 | INTEGRAR | `page` hub + enlace externo | nativo parcial | `template-documentos.php` | existe | derivar a DNCP |
| Ley 5189/14 | 2 | MIGRAR | `page` | nativo con limite | `template-documentos.php` | existe | hub documental |
| Datos y Tableros | 2 | INTEGRAR | `page` hub + enlaces externos | nativo parcial | `template-documentos.php` | existe | enlaces a tablero y datos |
| Noticias | 1 | MIGRAR | pagina de blog / archivo de posts | nativo | `home.php` | existe | nodo editorial principal |
| Presidencia | 2 | MIGRAR | categoria | nativo | `archive.php` | existe | categoria de noticias |
| Comisiones (noticias) | 2 | MIGRAR | categoria | nativo | `archive.php` | existe | categoria de noticias |
| Generales | 2 | MIGRAR | categoria | nativo | `archive.php` | existe | categoria de noticias |
| Servicios | 1 | MIGRAR | `page` hub | nativo | `page.php` | existe | agrupa sistemas externos |
| SILpy | 2 | INTEGRAR | enlace externo | fase 2 / integracion | menu o bloque de enlaces | existe via menus | no migrar en fase 1 |
| Digesto Legislativo | 2 | INTEGRAR | enlace externo | fase 2 / integracion | menu o bloque de enlaces | existe via menus | no migrar en fase 1 |
| Diario de Sesiones y Audios | 2 | INTEGRAR | enlace externo | fase 2 / integracion | menu o bloque de enlaces | existe via menus | mantener como acceso |
| Orden del Dia | 2 | INTEGRAR | enlace externo | fase 2 / integracion | menu o bloque de enlaces | existe via menus | mantener como acceso |
| SenadoTV | 2 | INTEGRAR | enlace externo o embed simple | nativo parcial | `page.php` si se quiere hub | existe | acceso a transmisiones |
| Datos Abiertos | 2 | INTEGRAR | enlace externo | nativo parcial | menu o bloque de enlaces | existe via menus | enlace institucional |
| Contacto | 1 | MIGRAR | `page` | nativo | `page.php` | existe | pagina simple |

## Paginas exactas a crear en WordPress para fase 1

## Paginas principales

1. Inicio
2. Senado
3. Senadores
4. Comisiones
5. Actividad Legislativa
6. Transparencia
7. Noticias
8. Servicios
9. Contacto

## Subpaginas institucionales

### Bajo Senado

1. La Camara
2. Institucion
3. Autoridades Administrativas
4. Dependencias Generales

### Bajo La Camara

1. Mesa Directiva
2. Expresidentes
3. Aspectos Legales

### Bajo Institucion

1. El Poder Legislativo
2. Mision y Vision
3. Plan Estrategico
4. Estructura Organica y Funciones

## Subpaginas de Senadores

1. Nomina de Senadores
2. Bancadas
3. Marco Legal Electoral

### Opcional en fase 1

- una pagina hija por senador o autoridad, debajo de `Nomina de Senadores`

## Subpaginas de Comisiones

1. Comisiones Permanentes
2. Comisiones Especiales
3. Comisiones Bicamerales y Nacionales
4. Informes de Gestion

### Opcional en fase 1

- una pagina hija por comision real debajo de cada indice correspondiente

## Subpaginas de Actividad Legislativa

1. Agenda Legislativa
2. Secretaria General
3. Sesiones y Materiales

## Subpaginas de Transparencia

1. Informes Institucionales
2. MECIP
3. Licitaciones
4. Ley 5189/14
5. Datos y Tableros

## Paginas especiales

1. una pagina por comision con plantilla `Comision institucional`
2. una pagina por senador o autoridad con plantilla `Senador o autoridad`
3. paginas documentales densas con plantilla `Transparencia y documentos`

## Entradas y categorias a crear

## Entradas

- noticias institucionales;
- agenda legislativa;
- comunicados o novedades segun criterio editorial.

## Categorias

1. noticias
2. agenda
3. presidencia
4. comisiones
5. generales

Recomendacion:

- usar `noticias` como categoria editorial paraguas si se necesita ordenar mejor la portada;
- usar `agenda` de forma exclusiva para actividades.

## Menus y submenus

## Menu principal final

1. Senado
   - La Camara
   - Institucion
   - Autoridades Administrativas
   - Dependencias Generales
2. Senadores
   - Nomina de Senadores
   - Bancadas
   - Marco Legal Electoral
3. Comisiones
   - Comisiones Permanentes
   - Comisiones Especiales
   - Comisiones Bicamerales y Nacionales
   - Informes de Gestion
4. Actividad Legislativa
   - Agenda Legislativa
   - Secretaria General
   - Sesiones y Materiales
5. Transparencia
   - Informes Institucionales
   - MECIP
   - Licitaciones
   - Ley 5189/14
   - Datos y Tableros
6. Noticias
   - Presidencia
   - Comisiones
   - Generales
7. Servicios
   - SILpy
   - Digesto Legislativo
   - Diario de Sesiones y Audios
   - Orden del Dia
   - SenadoTV
   - Datos Abiertos
8. Contacto

## Footer recomendado

### Menu footer

- Senado
- Contacto
- Transparencia
- Informes Institucionales
- Licitaciones
- Agenda Legislativa
- SILpy
- Digesto Legislativo

### Enlaces institucionales secundarios

- Camara de Diputados
- BACN
- Comision Bicameral de Presupuesto
- Datos Abiertos

## Accesos rapidos en home

1. Sesiones
2. Legislacion
3. Senadores
4. Comisiones
5. Transparencia
6. Contacto

### Accesos secundarios opcionales

- SILpy
- Digesto Legislativo
- SenadoTV
- Datos Abiertos

## Mapeo con el tema actual

| Tipo de seccion | Template actual | Existe | Ajuste minimo | Template nuevo mas adelante |
|---|---|---|---|---|
| Home | `front-page.php` | si | no | no |
| Pagina institucional general | `page.php` | si | no | no |
| Hub de seccion institucional | `page.php` | si | no | no |
| Noticia individual | `single.php` | si | no | no |
| Archivo de noticias | `home.php` / `archive.php` | si | no | no |
| Busqueda | `search.php` | si | no | no |
| Documentos / transparencia | `template-documentos.php` | si | no | tal vez en fase 2 si hay biblioteca documental |
| Comision | `template-comision.php` | si | no | si, si luego se modela CPT |
| Senador o autoridad | `template-autoridad.php` | si | no | si, si luego se modela CPT |
| Paginas hijas con navegacion contextual | `page.php` + `context-sidebar.php` | si | no | no |
| Servicios / integraciones | `page.php` | si | no | no |

## Recomendacion de uso del tema por seccion

### Usar `page.php`

- Senado
- La Camara
- Institucion
- Autoridades Administrativas
- Dependencias Generales
- Actividad Legislativa
- Secretaria General
- Sesiones y Materiales
- Servicios
- Contacto
- Bancadas

### Usar `template-documentos.php`

- Plan Estrategico
- Estructura Organica y Funciones
- Informes Institucionales
- MECIP
- Ley 5189/14
- Licitaciones
- Datos y Tableros
- Marco Legal Electoral

### Usar `template-comision.php`

- paginas individuales de comision

### Usar `template-autoridad.php`

- paginas individuales de senador o autoridad

### Usar `home.php`, `archive.php`, `single.php`

- Noticias
- categorias editoriales
- agenda legislativa basada en entradas

## Fase 2: fuera del alcance de esta implementacion

## CPTs potenciales

- `senador`
- `comision`
- `agenda`
- `documento`
- `sesion`

## Taxonomias potenciales

- `bancada`
- `tipo_de_comision`
- `tipo_documental`
- `periodo_legislativo`
- `tipo_de_actividad`

## Campos personalizados potenciales

- cargo;
- bancada;
- periodo;
- fotografia oficial;
- contacto;
- fecha y hora de evento;
- lugar;
- dependencia responsable;
- archivo adjunto;
- enlace a sistema externo;
- relacion con comision o senador.

## Integraciones profundas reservadas para fase 2

- SILpy
- Digesto Legislativo
- Diario de Sesiones y Audios
- Orden del Dia
- tableros y datos abiertos vivos
- biblioteca documental avanzada

## Recomendacion operativa final

La implementacion de fase 1 puede ejecutarse con el tema actual y WordPress nativo, creando:

- paginas jerarquicas;
- entradas y categorias para noticias y agenda;
- menus institucionales claros;
- hubs de servicios externos;
- paginas especiales solo donde el tema ya ofrece templates especificos.

La recomendacion es:

1. construir primero la arquitectura base en WordPress;
2. poblarla con contenido real en staging;
3. validar usabilidad, navegacion y gobernanza editorial;
4. recien despues abrir fase 2 para modelado estructurado.

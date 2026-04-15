# Sitemap objetivo para la nueva arquitectura del sitio del Senado

## Objetivo

Definir una arquitectura de informacion clara, institucional y mantenible para la futura web del Senado basada en WordPress, separando de forma explicita:

- lo que se migra al nuevo sitio;
- lo que se integra como sistema externo;
- lo que conviene simplificar, unificar o eliminar.

## Criterios de diseño del sitemap

- maximo 3 niveles de profundidad;
- menu principal breve y entendible;
- separacion entre contenido institucional, contenido editorial y sistemas externos;
- uso prioritario de WordPress nativo cuando sea razonable;
- posibilidad de evolucion a una fase 2 con CPTs o campos personalizados sin rehacer la base.

## Sitemap jerarquico objetivo

## Nivel 1 a 3

```text
Inicio
├── Senado
│   ├── La Camara
│   │   ├── Mesa Directiva
│   │   ├── Expresidentes
│   │   └── Aspectos Legales
│   ├── Institucion
│   │   ├── El Poder Legislativo
│   │   ├── Mision y Vision
│   │   ├── Plan Estrategico
│   │   └── Estructura Organica y Funciones
│   ├── Autoridades Administrativas
│   └── Dependencias Generales
├── Senadores
│   ├── Nomina de Senadores
│   ├── Bancadas
│   └── Marco Legal Electoral
├── Comisiones
│   ├── Comisiones Permanentes
│   ├── Comisiones Especiales
│   ├── Comisiones Bicamerales y Nacionales
│   └── Informes de Gestion
├── Actividad Legislativa
│   ├── Agenda Legislativa
│   ├── Noticias Legislativas
│   ├── Secretaria General
│   └── Sesiones y Materiales
├── Transparencia
│   ├── Informes Institucionales
│   ├── MECIP
│   ├── Licitaciones
│   ├── Ley 5189/14
│   └── Datos y Tableros
├── Noticias
│   ├── Presidencia
│   ├── Comisiones
│   └── Generales
├── Servicios
│   ├── SILpy
│   ├── Digesto Legislativo
│   ├── Diario de Sesiones y Audios
│   ├── Orden del Dia
│   ├── SenadoTV
│   └── Datos Abiertos
└── Contacto
```

## Justificacion de la estructura

### 1. Senado

Concentra toda la capa institucional e historica del organismo, evitando dispersarla entre varios nodos del menu.

### 2. Senadores

Se separa como macroseccion propia porque es una de las puertas de entrada mas frecuentes y porque hoy aparece mezclada con otras capas institucionales.

### 3. Comisiones

Se separa como macroseccion propia para dar visibilidad a un bloque funcional muy importante y porque hoy combina listados, informes y accesos a sistemas.

### 4. Actividad Legislativa

Se mantiene como eje principal, pero se simplifica como hub institucional y editorial. Los sistemas especializados quedan integrados como servicios, no mezclados en el arbol principal.

### 5. Transparencia

Se concentra en un solo nodo visible, corrigiendo la dispersion actual entre documentos, micrositios, leyes y tableros.

### 6. Noticias

Se separa de la agenda y del resto del contenido institucional para reforzar jerarquia editorial.

### 7. Servicios

Agrupa accesos a sistemas externos y micrositios, evitando contaminar el menu principal con plataformas ajenas al CMS.

### 8. Contacto

Permanece como acceso institucional simple y directo.

## Clasificacion por seccion

| Seccion objetivo | Accion | Tipo WordPress sugerido | Nativo WP | Fase 2 | Comentario |
|---|---|---|---|---|---|
| Inicio | MIGRAR | `page` + bloques de portada | si | no | home institucional |
| Senado | MIGRAR | `page` padre | si | no | contenedor institucional |
| La Camara | MIGRAR | `page` | si | no | paginas hijas |
| Mesa Directiva | MIGRAR | `page` o plantilla de pagina | si | posible | fase 2 solo si se requiere estructura de autoridades |
| Expresidentes | MIGRAR | `page` | si | posible | podria pasar a fichas si hay historico rico |
| Aspectos Legales | MIGRAR | `page` | si | no | contenido estable |
| Institucion | MIGRAR | `page` padre | si | no | subpaginas institucionales |
| El Poder Legislativo | MIGRAR | `page` | si | no | informativa |
| Mision y Vision | MIGRAR | `page` | si | no | informativa |
| Plan Estrategico | MIGRAR | `page` | si | no | documental |
| Estructura Organica y Funciones | MIGRAR | `page` | si | no | documental |
| Autoridades Administrativas | MIGRAR | `page` | si | posible | solo si luego necesita fichas |
| Dependencias Generales | MIGRAR | `page` | si | posible | puede seguir como pagina/listado |
| Senadores | MIGRAR | `page` padre | si | si | candidata clara a CPT en fase 2 |
| Nomina de Senadores | MIGRAR | `page` o listado de paginas | si | si | nativo en fase 1 |
| Bancadas | MIGRAR | `page` | si | si | luego podria ser taxonomia |
| Marco Legal Electoral | MIGRAR | `page` | si | no | documental |
| Comisiones | MIGRAR | `page` padre | si | si | candidata clara a CPT |
| Comisiones Permanentes | MIGRAR | `page` o listado de paginas | si | si | nativo en fase 1 |
| Comisiones Especiales | MIGRAR | `page` o listado de paginas | si | si | idem |
| Comisiones Bicamerales y Nacionales | MIGRAR | `page` o listado de paginas | si | si | idem |
| Informes de Gestion | MIGRAR | `page` o `post` segun volumen | si | posible | luego podria ser documental estructurado |
| Actividad Legislativa | MIGRAR | `page` hub | si | no | puerta de entrada simplificada |
| Agenda Legislativa | MIGRAR | `post` + categoria `agenda` | si | si | CPT solo si el modelo se complejiza |
| Noticias Legislativas | SIMPLIFICAR | `post` + categorias | si | no | conviene absorberlo dentro de Noticias |
| Secretaria General | MIGRAR | `page` hub | si | posible | integrando enlaces a sistemas |
| Sesiones y Materiales | INTEGRAR | pagina hub + enlaces externos | parcial | si | requiere integraciones o modelado futuro |
| Transparencia | MIGRAR | `page` padre | si | no | hub unico de transparencia |
| Informes Institucionales | MIGRAR | `page` | si | posible | puede pasar a documental estructurado |
| MECIP | MIGRAR | `page` | si | no | documental estable |
| Licitaciones | INTEGRAR | pagina hub + enlace DNCP | parcial | no | no conviene duplicar el sistema |
| Ley 5189/14 | MIGRAR | `page` o hub documental | si | posible | luego puede integrarse con documental estructurado |
| Datos y Tableros | INTEGRAR | pagina hub | parcial | no | agrupa datos abiertos y tableros externos |
| Noticias | MIGRAR | `page` de archivo o blog | si | no | editorial |
| Presidencia | MIGRAR | categoria | si | no | subcategoria o categoria |
| Comisiones (noticias) | MIGRAR | categoria | si | no | categoria |
| Generales | MIGRAR | categoria | si | no | categoria |
| Servicios | MIGRAR | `page` hub | si | no | hub de enlaces a sistemas |
| SILpy | INTEGRAR | enlace externo | no | si | sistema legislativo externo |
| Digesto Legislativo | INTEGRAR | enlace externo | no | si | sistema documental externo |
| Diario de Sesiones y Audios | INTEGRAR | enlace externo | no | si | sistema externo |
| Orden del Dia | INTEGRAR | enlace externo | no | si | sistema externo |
| SenadoTV | INTEGRAR | enlace externo o embed simple | parcial | no | acceso a streaming |
| Datos Abiertos | INTEGRAR | enlace externo | no | no | sistema de datos |
| Contacto | MIGRAR | `page` | si | no | contacto institucional |

## Secciones a simplificar o eliminar

| Elemento actual | Accion propuesta | Motivo |
|---|---|---|
| Noticias Presidencia / Noticias Comisiones / Noticias Generales como nodos dispersos | SIMPLIFICAR | agrupar dentro de `Noticias` con categorias |
| Agenda dentro de Noticias | SIMPLIFICAR | separar editorialmente `Agenda Legislativa` como bloque propio |
| Llamados y Licitaciones como pagina interna ambigua | SIMPLIFICAR | convertir en pagina hub clara que derive a DNCP |
| Multiples accesos sueltos a transparencia en home | SIMPLIFICAR | concentrar bajo `Transparencia` |
| Repeticion de enlaces institucionales en home y footer | SIMPLIFICAR | mantener solo accesos clave |
| Rutas tecnicas tipo `menu-contenido/listado-de-categoria-contenido` | ELIMINAR | reemplazar por slugs claros en WordPress |
| Sistemas externos dentro del menu principal mezclados con paginas | SIMPLIFICAR | mover a `Servicios` o a hubs tematicos |

## Redundancias actuales detectadas

- Noticias segmentadas en varias puertas de entrada separadas, cuando pueden resolverse con un solo archivo de noticias y categorias.
- Transparencia repartida entre paginas institucionales, leyes, tableros, nube y formularios.
- Actividad legislativa mezclada con herramientas externas y paginas internas.
- Menu principal, footer, mapa del sitio y home repiten rutas similares.
- Comisiones y senadores aparecen tanto en el sitio principal como en sistemas externos, sin una distincion clara para el usuario.

## Oportunidades de simplificacion

### 1. Consolidar nodos institucionales

Reunir bajo `Senado`:

- La Camara
- Institucion
- Autoridades Administrativas
- Dependencias

### 2. Separar personas y organos del resto institucional

Dar entidad propia a:

- `Senadores`
- `Comisiones`

### 3. Crear un verdadero hub de transparencia

Bajo `Transparencia`:

- informes;
- licitaciones;
- ley 5189/14;
- MECIP;
- datos y tableros.

### 4. Convertir sistemas en servicios

En lugar de competir con el contenido del sitio, los sistemas externos deben agruparse bajo `Servicios`.

### 5. Unificar noticias

Un solo nodo `Noticias` con categorias visibles y archivo claro.

## Mejoras de navegacion propuestas

- reducir el menu principal a 7 u 8 items de primer nivel;
- evitar mas de tres niveles;
- dejar las herramientas externas como accesos secundarios;
- eliminar tecnicismos de URL y nombres de categorias heredadas;
- dar jerarquia clara a `Noticias`, `Comisiones`, `Senadores` y `Transparencia`;
- usar hubs de seccion con contenido introductorio y accesos bien ordenados.

## Estructura final recomendada del menu principal

## Nivel 1

1. Senado
2. Senadores
3. Comisiones
4. Actividad Legislativa
5. Transparencia
6. Noticias
7. Servicios
8. Contacto

## Nivel 2 recomendado

### Senado

- La Camara
- Institucion
- Autoridades Administrativas
- Dependencias Generales

### Senadores

- Nomina de Senadores
- Bancadas
- Marco Legal Electoral

### Comisiones

- Permanentes
- Especiales
- Bicamerales y Nacionales
- Informes de Gestion

### Actividad Legislativa

- Agenda Legislativa
- Secretaria General
- Sesiones y Materiales

### Transparencia

- Informes Institucionales
- MECIP
- Licitaciones
- Ley 5189/14
- Datos y Tableros

### Noticias

- Presidencia
- Comisiones
- Generales

### Servicios

- SILpy
- Digesto Legislativo
- Diario de Sesiones y Audios
- Orden del Dia
- SenadoTV
- Datos Abiertos

## Estructura recomendada del footer

El footer no debe repetir todo el menu principal. Debe funcionar como cierre util y estable.

### Bloque 1: Institucional

- Senado
- Contacto
- Mapa del sitio

### Bloque 2: Transparencia

- Transparencia
- Informes Institucionales
- Licitaciones
- Ley 5189/14

### Bloque 3: Actividad Legislativa

- Agenda Legislativa
- Secretaria General
- SILpy
- Digesto Legislativo

### Bloque 4: Enlaces de interes

- Camara de Diputados
- BACN
- Comision Bicameral de Presupuesto
- Datos Abiertos

## Accesos rapidos recomendados en home

La home no deberia usar demasiados accesos rapidos. Conviene limitarse a 4 a 6.

### Accesos rapidos principales

- Sesiones
- Legislacion
- Senadores
- Comisiones
- Transparencia
- Contacto

### Accesos rapidos secundarios opcionales

- SILpy
- Digesto Legislativo
- SenadoTV
- Datos Abiertos

Estos accesos secundarios pueden ir en una banda o bloque de servicios, no en el centro editorial de la portada.

## Mapeo de implementacion en WordPress

## Puede resolverse con WordPress nativo

- paginas institucionales;
- hubs de seccion;
- noticias;
- agenda inicial;
- hubs de transparencia;
- menus;
- footer;
- home;
- listados simples de comisiones y perfiles en fase 1.

## Requiere fase 2 o integracion

- directorio completo de senadores;
- directorio completo de comisiones con relaciones;
- agenda con fecha y metadata estructurada;
- biblioteca documental avanzada;
- sesiones parlamentarias completas;
- integracion con expedientes legislativos y leyes;
- datos abiertos y tableros vivos.

## Recomendacion final

La arquitectura objetivo debe basarse en una primera fase de WordPress simple, clara y editorialmente ordenada, con hubs bien definidos y solo los sistemas necesarios integrados como servicios externos.

La clave no es migrar todo al CMS, sino:

1. migrar lo institucional y editorial;
2. integrar lo transaccional o especializado;
3. simplificar lo redundante;
4. reservar la complejidad estructurada para una segunda fase.

Este enfoque mejora:

- claridad;
- navegabilidad;
- mantenibilidad;
- facilidad de gestion para el equipo.

# Centralizador de Ofertas de Comida Rápida

## Descripción

Sistema web que busca centralizar ofertas y descuentos publicados en las páginas web seleccionadas de McDonald's, Burger King y Mostaza.

El proyecto busca facilitar la consulta de promociones desde un único lugar, evitando que los usuarios tengan que visitar diferentes sitios para encontrar la información.

La información se obtendrá mediante procesos automáticos de extracción y procesamiento de publicaciones.

## Objetivo

Desarrollar una aplicación web que permita consultar ofertas de comida rápida, comprender sus beneficios y condiciones conocidas, acceder a las publicaciones originales y reportar posibles errores en la información.

## Alcance del MVP

La primera versión del sistema se concentrará en las siguientes funcionalidades:

- Consultar ofertas obtenidas automáticamente de las fuentes web seleccionadas.
- Mostrar los beneficios y las condiciones disponibles de cada oferta.
- Acceder a la publicación original para consultar la información de la fuente.
- Reportar ofertas aparentemente vencidas.
- Reportar información incorrecta.
- Reportar enlaces que no funcionan.
- Procesar automáticamente las publicaciones y actualizar la información cuando sea posible.

La extracción automática, el OCR y el uso de inteligencia artificial se implementarán según las necesidades y la viabilidad técnica de las fuentes seleccionadas.

### Fuera del alcance inicial

- Gestión de pedidos o entregas.
- Comparación de ofertas entre marcas, productos o precios.
- Recomendaciones personalizadas.
- Notificaciones personalizadas.
- Garantizar la recopilación de todas las promociones publicadas por las marcas en cualquier canal.

## Tecnologías previstas

### Frontend
- React.
- JavaScript.
- Vite.
- HTML y CSS.

### Backend
- C#.
- ASP.NET Core Web API.
- Entity Framework Core, sujeto a la selección y compatibilidad del proveedor para MySQL.

### Base de datos
- MySQL.

## Documentación

La documentación del proyecto se encuentra en la carpeta `docs/`.

- [Historias de usuario](docs/user-stories/USER-STORIES.md)
- [Requisitos del sistema](docs/requirements/REQUIREMENTS.md)
- [Arquitectura del sistema](docs/architecture/ARCHITECTURE.md)
- [Diseño de la base de datos](docs/database/DATABASE-DESIGN.md)
- [Decisiones técnicas](docs/decisions/TECHNICAL-DECISIONS.md)
- [Convenciones de desarrollo](CONVENTIONS.md)

## Estado del proyecto

**Etapa actual:** preparación y documentación del proyecto.

El frontend inicial fue creado con React y Vite. El backend, la base de datos y las funcionalidades principales se desarrollarán progresivamente.

## Alcance académico

Este proyecto forma parte de un trabajo de desarrollo de software y se construirá de manera incremental, priorizando una solución sencilla, mantenible y alineada con los requisitos definidos para el MVP.

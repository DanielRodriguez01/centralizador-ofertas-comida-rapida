# Diseño inicial de la base de datos

## 1. Objetivo

Definir la estructura inicial de datos que utilizará el Centralizador de ofertas de comida rápida.

La base de datos permitirá almacenar las marcas, las fuentes web, las ofertas obtenidas automáticamente y los reportes enviados por los visitantes.

Este diseño es preliminar y podrá ajustarse durante el desarrollo, según las necesidades confirmadas del MVP.

## 2. Motor de base de datos

Se utilizará MySQL como sistema gestor de base de datos.

El backend en C# será responsable de acceder a los datos y realizar las operaciones necesarias.

El frontend en React no se conectará directamente con MySQL.

## 3. Entidades principales

### 3.1. Marca

Representa a una empresa o marca cuyas publicaciones de ofertas forman parte del sistema.

Ejemplos iniciales:

- McDonald's.
- Burger King.
- Mostaza.

Información prevista:

- Identificador único.
- Nombre de la marca.
- Estado de habilitación.

### 3.2. Fuente

Representa una página o ubicación web previamente seleccionada de la que el sistema obtiene publicaciones.

Información prevista:

- Identificador único.
- Marca asociada.
- URL de la fuente.
- Tipo de fuente.
- Estado de habilitación.
- Fecha de la última revisión, cuando corresponda.
- Información necesaria para registrar errores de extracción.

Una marca podrá tener varias fuentes.

La estrategia de obtención de información deberá validarse para cada fuente antes de implementar su extracción automática.

### 3.3. Oferta

Representa una promoción obtenida de una fuente web.

Información prevista:

- Identificador único.
- Marca asociada.
- Fuente de origen.
- Título de la publicación.
- Descripción o resumen del beneficio.
- Condiciones conocidas.
- Precio, descuento u otros datos del beneficio, cuando estén disponibles.
- Fecha de inicio, cuando se conozca.
- Fecha de finalización, cuando se conozca.
- URL de la publicación original.
- Fecha de obtención de la información.
- Fecha de la última actualización.
- Estado de la oferta.
- Información necesaria para identificar la publicación de origen.

Los datos que no puedan obtenerse o verificarse deberán tratarse como desconocidos, sin inventar valores.

El sistema deberá distinguir entre una oferta cuya vigencia está confirmada y una oferta cuya vigencia necesita revisión.

### 3.4. Reporte

Representa un aviso enviado por un visitante acerca de una oferta.

Información prevista:

- Identificador único.
- Oferta relacionada.
- Tipo de problema informado.
- Descripción adicional, cuando corresponda.
- Fecha de creación.
- Estado de revisión del reporte.

Tipos iniciales de reporte:

- Oferta aparentemente vencida.
- Información incorrecta.
- Enlace que no funciona.

El reporte no modificará automáticamente los datos de la oferta sin un proceso de validación.

## 4. Relaciones entre entidades

Las relaciones iniciales previstas son:

- Una marca puede tener varias fuentes.
- Una marca puede tener varias ofertas.
- Una fuente puede originar varias ofertas.
- Una oferta puede recibir varios reportes.
- Cada reporte estará asociado a una oferta.

Las relaciones definitivas se establecerán al implementar el modelo de datos.

## 5. Criterios de integridad

- Cada registro tendrá un identificador único.
- Las ofertas conservarán la referencia a su fuente original.
- Los reportes estarán vinculados a la oferta correspondiente.
- Los datos desconocidos no se completarán mediante suposiciones.
- Las fechas de vigencia deberán diferenciarse de las fechas en que el sistema obtuvo o actualizó la información.
- Los errores de extracción deberán poder registrarse sin presentar información no verificada como si fuera correcta.

## 6. Consideraciones para la extracción automática

El sistema deberá poder relacionar las ofertas obtenidas con sus fuentes originales.

También deberá contemplar que una misma publicación puede volver a detectarse en distintas ejecuciones del proceso de extracción.

Antes de guardar una publicación, se deberá evaluar cómo reconocer si ya existe para evitar duplicados innecesarios.

El criterio definitivo para identificar publicaciones repetidas se establecerá durante la implementación.

## 7. Decisiones pendientes

Antes de crear las tablas definitivas, será necesario:

- Validar las fuentes web que se utilizarán.
- Definir cómo se identificarán las publicaciones repetidas.
- Precisar los estados de las ofertas y de los reportes.
- Determinar qué datos del beneficio pueden obtenerse de cada fuente.
- Definir las restricciones y los índices necesarios.
- Verificar la compatibilidad del proveedor de Entity Framework Core seleccionado con MySQL y la versión de .NET elegida.
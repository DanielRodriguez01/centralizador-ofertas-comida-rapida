# Arquitectura del sistema — Centralizador de ofertas de comida rápida

## 1. Objetivo

Definir la organización general del sistema y las responsabilidades de sus principales componentes.

La arquitectura debe ser sencilla, mantenible y adecuada para el MVP inicial.

## 2. Estilo arquitectónico

El backend se desarrollará con una arquitectura de monolito modular.

Esto significa que el backend se ejecutará como una aplicación principal, pero su código estará organizado en módulos que agrupen funcionalidades relacionadas.

En el frontend se utilizará React con JavaScript, organizando el código por componentes y funcionalidades.

No se implementarán microservicios en el MVP.

## 3. Tecnologías principales

### Frontend

- React.
- JavaScript.
- Vite.
- HTML y CSS.

Responsabilidades:

- Mostrar las ofertas disponibles.
- Presentar sus beneficios y condiciones conocidas.
- Permitir acceder a las publicaciones originales.
- Permitir registrar reportes de los visitantes.
- Comunicar las acciones del usuario al backend mediante una API.

### Backend

- C#.
- ASP.NET Core Web API.
- Entity Framework Core, sujeto a la compatibilidad del proveedor elegido para MySQL.

Responsabilidades:

- Exponer los servicios que necesita el frontend.
- Gestionar las ofertas y sus datos.
- Registrar y gestionar los reportes.
- Obtener y procesar publicaciones automáticamente.
- Extraer y normalizar información.
- Utilizar OCR o IA cuando corresponda.
- Validar los datos antes de presentarlos como confirmados.
- Comunicarse con la base de datos.

### Base de datos

- MySQL.

Responsabilidades:

- Almacenar las ofertas obtenidas.
- Conservar los datos de las fuentes originales.
- Registrar los reportes de los visitantes.
- Mantener la información necesaria para actualizar las ofertas.

## 4. Comunicación entre componentes

React se comunicará con el backend mediante solicitudes HTTP a una API.

El backend será responsable de acceder a MySQL.

El frontend no se conectará directamente con la base de datos.

La comunicación permitirá consultar ofertas, obtener sus detalles y registrar reportes.

## 5. Procesamiento automático de publicaciones

El backend será responsable de coordinar la obtención y el procesamiento automático de publicaciones de las fuentes seleccionadas.

El proceso deberá contemplar:

1. Obtener publicaciones de las fuentes seleccionadas.
2. Extraer los datos relevantes.
3. Aplicar OCR cuando la información esté contenida en imágenes y resulte necesario.
4. Utilizar IA para clasificar, resumir o interpretar condiciones cuando aporte valor.
5. Normalizar y validar los datos.
6. Guardar o actualizar la información en MySQL.
7. Conservar la referencia a la publicación original.

La estrategia de extracción y la frecuencia de actualización se definirán después de comprobar las posibilidades técnicas de cada fuente.

## 6. Organización del backend

El backend seguirá un enfoque de monolito modular.

Los módulos se organizarán por funcionalidades del negocio y no únicamente por tipos técnicos de archivo.

Se priorizarán funcionalidades pequeñas y completas que permitan avanzar de manera incremental.

La estructura definitiva de carpetas se establecerá durante la preparación del backend.

## 7. Organización del frontend

El frontend se desarrollará con React y JavaScript.

Se utilizarán componentes reutilizables y una organización por funcionalidades cuando resulte útil.

Se evitará crear abstracciones innecesarias para el MVP.

## 8. Seguridad y confiabilidad

- Las credenciales de MySQL permanecerán en el backend.
- El frontend no contendrá secretos ni credenciales privadas.
- Los datos extraídos deberán validarse antes de presentarse como confirmados.
- Los resultados generados por IA no se considerarán automáticamente correctos.
- Los errores de extracción y los datos incompletos deberán gestionarse sin inventar información.

## 9. Decisiones pendientes de validación

Antes de implementar las funcionalidades correspondientes, será necesario:

- Comprobar las posibilidades de extracción de cada fuente.
- Seleccionar y verificar la compatibilidad del proveedor de Entity Framework Core para MySQL.
- Definir la estrategia de actualización automática.
- Determinar qué soluciones de OCR e IA son necesarias y viables.
- Diseñar el modelo de datos según las necesidades confirmadas del MVP.

## 10. Alcance de la arquitectura

La arquitectura se plantea para el MVP inicial.

Se prioriza una solución sencilla que permita implementar, probar y mantener las funcionalidades sin incorporar infraestructura innecesaria.
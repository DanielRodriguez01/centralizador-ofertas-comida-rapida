# Convenciones de desarrollo

## 1. Objetivo

Establecer reglas comunes para desarrollar y mantener el Centralizador de ofertas de comida rápida.

Estas convenciones se aplicarán al frontend, al backend, a la base de datos y a la documentación.

El objetivo es mantener un código claro, coherente y fácil de modificar, evitando la sobreingeniería.

## 2. Principios generales

- Priorizar soluciones sencillas que resuelvan las necesidades reales del MVP.
- Evitar agregar funcionalidades que no formen parte del alcance definido.
- No crear abstracciones, capas, interfaces o proyectos adicionales sin una necesidad concreta.
- Preferir nombres descriptivos y fáciles de comprender.
- Mantener las responsabilidades de cada componente bien delimitadas.
- No duplicar código innecesariamente.
- No incorporar dependencias sin justificar su utilidad.
- No reemplazar código funcional sin comprender primero su propósito.
- Antes de modificar una funcionalidad existente, revisar cómo se relaciona con el resto del sistema.

## 3. Organización del proyecto

El repositorio contendrá el frontend, el backend y la documentación.

### Frontend

Se desarrollará con React, JavaScript y Vite.

Su responsabilidad será presentar la información al visitante y permitir la interacción con las funcionalidades disponibles.

### Backend

Se desarrollará con C# y ASP.NET Core Web API.

Se organizará como un monolito modular, agrupando las funcionalidades relacionadas con el negocio.

### Base de datos

Se utilizará MySQL.

El acceso a los datos estará centralizado en el backend.

### Documentación

Se mantendrán documentadas las historias de usuario, los requisitos, la arquitectura, el diseño de la base de datos y las decisiones técnicas.

## 4. Convenciones del backend

- Utilizar C# y las características modernas compatibles con la versión de .NET seleccionada.
- Utilizar nombres descriptivos para clases, métodos, propiedades y variables.
- Mantener una nomenclatura coherente con las convenciones habituales de C#.
- Utilizar `PascalCase` para nombres de clases, métodos y propiedades públicas.
- Utilizar `camelCase` para variables locales y parámetros.
- Mantener los controladores y endpoints enfocados en la comunicación HTTP.
- Ubicar la lógica de negocio en el lugar correspondiente a la funcionalidad.
- Evitar concentrar toda la lógica de la aplicación en un único controlador.
- Validar los datos recibidos antes de procesarlos.
- Gestionar los errores de forma controlada.
- No devolver información interna sensible en las respuestas de la API.
- Utilizar Entity Framework Core para el acceso a datos si se confirma su compatibilidad con el proveedor de MySQL seleccionado.
- No incorporar AutoMapper ni otras bibliotecas de mapeo automático sin una necesidad concreta y justificada.
- Evitar crear interfaces e implementaciones duplicadas cuando no aporten una ventaja real.

## 5. Organización modular y vertical slices

El backend se organizará por funcionalidades del negocio.

Cada funcionalidad podrá agrupar los elementos que necesite para completar una operación, como la validación de datos, la lógica correspondiente y el acceso a los datos.

Se priorizará el enfoque de vertical slices: desarrollar una funcionalidad pequeña de principio a fin, incluyendo las partes necesarias para que funcione.

Por ejemplo, consultar ofertas puede constituir una funcionalidad completa que conecte el endpoint, la lógica necesaria y la base de datos.

No se crearán capas o proyectos adicionales únicamente por seguir una plantilla arquitectónica.

La estructura definitiva se establecerá al preparar el backend.

## 6. Convenciones del frontend

- Utilizar React con JavaScript.
- Mantener los componentes pequeños y con responsabilidades claras.
- Utilizar nombres descriptivos para los componentes y las funciones.
- Utilizar `PascalCase` para los nombres de componentes React.
- Utilizar `camelCase` para variables y funciones.
- Separar la presentación de la lógica que resulte conveniente reutilizar.
- Evitar duplicar componentes o lógica sin necesidad.
- No conectar React directamente con MySQL.
- Obtener y enviar información mediante la API del backend.
- Gestionar los estados de carga, error y ausencia de resultados cuando corresponda.
- Validar los formularios tanto en el frontend como en el backend cuando corresponda.
- Mantener un diseño adaptable a computadoras y dispositivos móviles.
- Evitar incorporar bibliotecas de interfaz o administración de estado sin una necesidad concreta.

## 7. Convenciones de la base de datos

- Utilizar MySQL como motor de base de datos.
- Definir identificadores únicos para los registros.
- Establecer relaciones y restricciones de integridad cuando correspondan.
- Utilizar nombres claros y consistentes para tablas y columnas.
- Conservar la referencia a la fuente original de cada oferta.
- Diferenciar las fechas de vigencia de las fechas de extracción y actualización.
- No guardar valores inventados para completar información desconocida.
- Evitar duplicar publicaciones mediante un criterio de identificación que se definirá durante la implementación.
- No guardar credenciales de conexión en el repositorio.

## 8. Extracción y procesamiento de ofertas

- La extracción de publicaciones deberá ser automática.
- Cada fuente deberá evaluarse antes de implementar su mecanismo de extracción.
- Se deberán respetar las condiciones de acceso aplicables a cada fuente.
- Los errores de extracción deberán registrarse y gestionarse.
- La información extraída deberá normalizarse y validarse antes de publicarse.
- Se conservará la referencia a la publicación original.
- No se considerará que una oferta continúa vigente únicamente porque sigue apareciendo en una página.
- No se marcará una oferta como vencida sin información suficiente que respalde esa conclusión.
- Se evitará crear registros duplicados cuando una publicación vuelva a detectarse.

### Uso de OCR e inteligencia artificial

- Utilizar OCR cuando sea necesario obtener texto de imágenes.
- Utilizar inteligencia artificial para clasificar, resumir o interpretar publicaciones únicamente cuando aporte valor.
- Validar los resultados generados automáticamente.
- No tratar los resultados de la IA como datos confirmados sin comprobaciones apropiadas.
- No inventar precios, beneficios, condiciones, códigos ni fechas.
- Si un dato no puede verificarse, conservarlo como desconocido o indicar que necesita revisión.

## 9. Seguridad y configuración

- No guardar contraseñas, claves de API ni otros secretos en el repositorio.
- Utilizar variables de entorno o mecanismos apropiados de configuración.
- Mantener las credenciales de MySQL exclusivamente en el backend.
- No exponer secretos en el código del frontend.
- Validar los datos recibidos por la API.
- Evitar devolver trazas internas o detalles sensibles en los errores.
- Revisar la seguridad de las dependencias incorporadas.

## 10. Pruebas y calidad

- Probar cada funcionalidad antes de considerarla terminada.
- Verificar los casos normales y los errores previsibles.
- Comprobar que los cambios no rompan funcionalidades existentes.
- Priorizar pruebas sobre las reglas de negocio importantes.
- Verificar que los datos presentados al visitante coincidan con la información disponible y validada.
- Documentar las limitaciones conocidas que puedan afectar al funcionamiento.

## 11. Uso de herramientas de inteligencia artificial para programar

Las herramientas de IA que colaboren en el desarrollo deberán:

- Leer este archivo antes de generar o modificar código.
- Respetar la arquitectura y el alcance del MVP.
- Revisar el código existente antes de realizar cambios.
- Evitar reemplazar archivos completos cuando basten modificaciones puntuales.
- No agregar proyectos, carpetas, capas, clases o dependencias innecesarias.
- Explicar qué archivos modifican y por qué.
- Indicar qué pruebas se realizaron y cuáles quedan pendientes.
- No afirmar que una funcionalidad fue probada si no se ejecutaron las pruebas correspondientes.
- No inventar información extraída de las fuentes.
- Solicitar aclaraciones cuando una decisión importante no esté definida y no pueda resolverse con seguridad a partir de la documentación existente.

## 12. Alcance del MVP

El sistema se concentrará en:

- Consultar ofertas obtenidas automáticamente de las fuentes web seleccionadas de McDonald's, Burger King y Mostaza.
- Mostrar los beneficios y las condiciones conocidas.
- Permitir acceder a las publicaciones originales.
- Permitir que los visitantes reporten ofertas aparentemente vencidas, información incorrecta o enlaces que no funcionan.

No se incorporarán al MVP funcionalidades de entrega de pedidos, comparación de ofertas, personalización de recomendaciones ni notificaciones personalizadas.

## 13. Regla final

Ante varias soluciones técnicamente válidas, se preferirá la más sencilla que cumpla los requisitos, mantenga la calidad necesaria y permita evolucionar el sistema sin complejidad innecesaria.
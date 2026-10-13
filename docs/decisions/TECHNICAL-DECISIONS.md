# Registro de decisiones técnicas

## 1. Objetivo

Registrar las principales decisiones técnicas del Centralizador de ofertas de comida rápida y los motivos que las justifican.

Las decisiones podrán revisarse si durante el desarrollo aparecen nuevas necesidades o limitaciones técnicas.

## 2. Decisión: utilizar React para el frontend

**Estado:** Aprobada.

**Decisión:**

Utilizar React con JavaScript y Vite para desarrollar la interfaz web.

**Motivo:**

Esta combinación permite construir una interfaz organizada en componentes y desarrollar las funcionalidades de manera incremental.

**Responsabilidad:**

El frontend mostrará las ofertas, sus condiciones conocidas, las publicaciones originales y los formularios para enviar reportes.

## 3. Decisión: utilizar C# y ASP.NET Core para el backend

**Estado:** Aprobada.

**Decisión:**

Utilizar C# con ASP.NET Core Web API.

**Motivo:**

Permite desarrollar una API que centralice las reglas del sistema, gestione las ofertas y los reportes, procese la información obtenida de las fuentes y se comunique con la base de datos.

**Responsabilidad:**

El backend será el intermediario entre el frontend, la base de datos y los procesos de extracción automática.

## 4. Decisión: utilizar MySQL

**Estado:** Aprobada.

**Decisión:**

Utilizar MySQL como motor de base de datos.

**Motivo:**

Se utilizará para conservar las marcas, las fuentes, las ofertas y los reportes del sistema.

**Pendiente de implementación:**

Seleccionar y verificar un proveedor de Entity Framework Core compatible con la versión de .NET elegida y con MySQL.

## 5. Decisión: utilizar un monolito modular

**Estado:** Aprobada.

**Decisión:**

Desarrollar el backend como una aplicación principal organizada en módulos relacionados con las funcionalidades del negocio.

**Motivo:**

El MVP no necesita la complejidad operativa de una arquitectura de microservicios.

La organización modular permitirá mantener separadas las responsabilidades sin multiplicar innecesariamente los proyectos y servicios.

## 6. Decisión: obtener las publicaciones automáticamente

**Estado:** Aprobada como requisito del MVP. La estrategia técnica está pendiente de validación.

**Decisión:**

La información de las ofertas deberá obtenerse automáticamente de las fuentes web seleccionadas.

No se utilizará la carga manual como mecanismo habitual para alimentar el catálogo de ofertas.

**Motivo:**

El objetivo del proyecto es centralizar promociones publicadas en la web y reducir la necesidad de consultar diferentes sitios manualmente.

**Consideraciones:**

La viabilidad de la extracción deberá comprobarse para cada fuente.

Se deberán respetar las condiciones de acceso aplicables y gestionar los errores de extracción.

## 7. Decisión: utilizar OCR e inteligencia artificial cuando corresponda

**Estado:** Requisito funcional previsto. Las herramientas concretas están pendientes de evaluación.

**Decisión:**

Se evaluará el uso de OCR para extraer texto de imágenes y de inteligencia artificial para clasificar publicaciones, resumir beneficios e interpretar condiciones.

**Motivo:**

Algunas publicaciones pueden contener información relevante dentro de imágenes o utilizar textos que requieran procesamiento adicional.

**Consideraciones:**

Los resultados deberán validarse.

La inteligencia artificial no deberá inventar precios, condiciones ni fechas de vigencia.

No se incorporarán herramientas innecesarias si una solución más sencilla resuelve el problema.

## 8. Decisión: conservar la publicación original

**Estado:** Aprobada.

**Decisión:**

Las ofertas deberán mantener una referencia a su publicación original.

**Motivo:**

Los visitantes necesitan poder consultar la fuente original y verificar las condiciones de una promoción.

## 9. Decisión: evitar funcionalidades fuera del MVP

**Estado:** Aprobada.

**Decisión:**

El desarrollo se concentrará en consultar ofertas de las marcas seleccionadas, comprender sus beneficios y condiciones, acceder a la publicación original y reportar posibles problemas.

**Motivo:**

Mantener un alcance acotado permite priorizar las funcionalidades esenciales y validar el funcionamiento del sistema antes de incorporar características adicionales.

Quedan fuera del MVP las comparaciones de ofertas, la entrega de pedidos, la personalización de recomendaciones y las notificaciones personalizadas.

## 10. Decisiones pendientes

Las siguientes decisiones se tomarán cuando exista información suficiente:

- Proveedor de Entity Framework Core para MySQL.
- Estructura definitiva de módulos y funcionalidades del backend.
- Estrategia de extracción para cada fuente.
- Frecuencia de actualización de las ofertas.
- Herramientas de OCR e inteligencia artificial.
- Estrategia para identificar publicaciones repetidas.
- Entorno de despliegue de la aplicación.
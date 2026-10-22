# Registro de prompts utilizados con IA

Este documento registra los prompts utilizados como herramienta de apoyo durante el desarrollo del proyecto **Centralizador de ofertas de comida rápida**.

El objetivo de este registro es documentar cómo se utilizó la Inteligencia Artificial durante el proceso de análisis, diseño, programación y documentación del sistema.

La utilización de IA no reemplaza el análisis y las decisiones del equipo. Las respuestas obtenidas son consideradas material de apoyo y son revisadas antes de incorporarlas al proyecto.

---

## Criterio de registro

Para cada utilización relevante de IA se registra:

* **Fecha:** cuándo se realizó la consulta.
* **Objetivo:** para qué se utilizó la IA.
* **Prompt:** consulta realizada.
* **Resultado / aporte:** qué información útil se obtuvo.
* **Decisión del equipo:** qué se decidió hacer después de analizar la respuesta.

---

# Prompts registrados

## Prompt 01 — Definición y planificación del proyecto

### 1. Identificación inicial de problemas

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 11:08 a. m.

**Objetivo:**
Analizar los problemas que podrían existir al construir un sistema centralizador de ofertas y descuentos publicados en la web, inicialmente limitado a páginas de McDonald’s, Burger King y Mostaza.

**Prompt utilizado:**

> Quiero construir un sistema centralizador de ofertas y descuentos publicados en la web. Inicialmente, nos limitamos a tres páginas de comida rápida: McDonald’s, Burger King y Mostaza. Actúa como consultor de producto. Genera una lista de problemas reales que se enfrentan al:
>
> * Leer las páginas publicadas y extraer sus ofertas.
> * Seleccionar una oferta y ser dirigido a la página que la ofrece.
>
> No propongas soluciones todavía. Solo identifica problemas y propone qué tipos de usuarios existirían.

**Resultado / aporte:**

La consulta permitió comenzar el análisis del problema antes de definir funcionalidades o soluciones. Se analizaron dos áreas principales:

* Los problemas relacionados con leer las páginas y extraer las ofertas.
* Los problemas relacionados con seleccionar una oferta y acceder a la página de origen.

También se identificaron los posibles tipos de usuarios relacionados con esas situaciones.

**Decisión del equipo:**

Se decidió continuar analizando los problemas antes de diseñar la solución, evitando comenzar directamente por las funcionalidades del sistema.

---

### 2. Análisis de problemas para definir el MVP

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 11:12 a. m.

**Objetivo:**
Evaluar los problemas identificados anteriormente para determinar cuáles tenían mayor relevancia para la definición del MVP.

**Prompt utilizado:**

> Analiza los problemas anteriores para plantear un MVP. Explica, para cada problema:
>
> * Impacto para el usuario.
> * Frecuencia del problema.
> * Facilidad de validación.
> * Potencial de negocio.

**Resultado / aporte:**

Se utilizó el análisis para comparar los problemas identificados considerando su impacto, frecuencia, facilidad de validación y potencial de negocio.

**Decisión del equipo:**

El análisis sirvió como base para continuar reduciendo el alcance del proyecto y seleccionar las funcionalidades que realmente fueran necesarias para validar la idea.

---

### 3. Identificación de funcionalidades posibles

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 11:29 a. m.

**Objetivo:**
Identificar todas las funcionalidades que podrían formar parte de una solución para los problemas analizados.

**Prompt utilizado:**

> Genera todas las funcionalidades que podrían formar parte de una solución. Agrúpalas por problema y no te limites. Incluye ideas básicas y avanzadas.

**Resultado / aporte:**

Se generó un conjunto amplio de funcionalidades agrupadas según los problemas previamente identificados.

Esto permitió diferenciar posteriormente las funcionalidades indispensables de aquellas que podían quedar para etapas posteriores.

**Decisión del equipo:**

Se decidió no incorporar automáticamente todas las funcionalidades propuestas. Las funcionalidades debían ser evaluadas posteriormente según su necesidad para validar el producto.

---

### 4. Clasificación de funcionalidades y reducción del alcance

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 1:58 p. m.

**Objetivo:**
Clasificar las funcionalidades propuestas anteriormente según su importancia para validar el producto y reducir el alcance del proyecto.

**Prompt utilizado:**

> Clasifica las funcionalidades anteriores en tres grupos, separados según los problemas ya enunciados:
>
> * «Problemas al leer las páginas y extraer ofertas».
> * «Problemas al elegir una oferta y abrir la página de origen».
>
> Para cada problema, usa estos grupos:
>
> 1. Imprescindibles para validar el producto.
> 2. Deseables, pero no necesarias.
> 3. Funcionalidades futuras.
>
> Usa este criterio: «¿Podemos demostrar que la idea funciona sin esta funcionalidad?»
>
> La lectura y extracción de ofertas debe ser automática, no manual. No consideres la opción de delivery. No incluyas la comparación de ofertas por marca, productos, precio, beneficio, vigencia o código.
>
> Explica cada decisión y genera un resumen.

**Resultado / aporte:**

Esta etapa permitió clasificar las funcionalidades según su importancia y aplicar un criterio concreto para reducir el alcance: determinar si el producto podía demostrar su funcionamiento sin una determinada funcionalidad.

También se establecieron restricciones importantes para el alcance:

* La extracción debía ser automática y no manual.
* No se incorporaría delivery.
* No se realizarían comparaciones entre ofertas por marca, productos, precio, beneficio, vigencia o código.

**Decisión del equipo:**

Se decidió utilizar estas restricciones para evitar que el MVP creciera innecesariamente y concentrar el desarrollo en la validación de la idea principal.

---

### 5. Definición del MVP mínimo

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 2:10 p. m.

**Objetivo:**
Diseñar un MVP extremadamente pequeño incorporando únicamente las funcionalidades consideradas indispensables y agregar determinadas capacidades de extracción, procesamiento y reporte.

**Prompt utilizado:**

> Con toda la información anterior, diseña un MVP extremadamente pequeño. Incluye únicamente funcionalidades indispensables y agrega las siguientes en el problema que corresponda:
>
> * Extraer y estructurar todos los tipos de beneficio.
> * Recibir reportes de usuarios sobre ofertas vencidas o datos incorrectos.
> * Normalizar formatos de fechas, precios y nombres.
> * Usar OCR para extraer promociones publicadas solo como imágenes y leer documentos automáticamente.
> * Usar IA para clasificar publicaciones, redactar resúmenes o interpretar condiciones.
>
> Justifica por qué cada funcionalidad forma parte del MVP.

**Resultado / aporte:**

Se definió un MVP que incorpora la extracción automática y estructuración de las ofertas, normalización de información, procesamiento mediante OCR, lectura automática de documentos, utilización de IA para determinadas tareas y recepción de reportes de usuarios.

Estas funcionalidades quedaron posteriormente reflejadas en el documento del MVP definitivo. La extracción contempla páginas públicas previamente seleccionadas y el procesamiento de diferentes tipos de beneficios.

**Decisión del equipo:**

Se decidió incorporar estas funcionalidades al MVP porque forman parte de la validación de la obtención y presentación confiable de las ofertas, manteniendo al mismo tiempo las fuentes limitadas a las tres marcas seleccionadas.

---

### 6. Resumen definitivo del MVP

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 2:20 p. m.

**Objetivo:**
Resumir las características definitivas del MVP y establecer claramente su alcance.

**Prompt utilizado:**

> Elabora un listado resumido de las características del MVP.

Como parte del resultado se estableció:

> # MVP: Centralizador de ofertas de comida rápida
>
> El MVP tendrá una sola experiencia para el usuario: ver ofertas de McDonald’s, Burger King y Mostaza, entenderlas y abrir su publicación original. La obtención de ofertas será automática.
>
> Para mantener el alcance pequeño, se leerán páginas públicas previamente seleccionadas de esas tres marcas, sin intentar descubrir todas las promociones disponibles en cada sitio o app.
>
> Las funcionalidades de extracción de beneficios, reportes, normalización, OCR e IA forman parte del MVP, pero se limitan a esas fuentes para conservar un alcance manejable.

**Resultado / aporte:**

El trabajo permitió establecer una experiencia única y sencilla para el usuario, centrada en visualizar las ofertas, comprenderlas y acceder a su publicación original.

También se definió que la obtención de las ofertas sería automática y que las fuentes estarían limitadas a páginas públicas previamente seleccionadas de McDonald’s, Burger King y Mostaza.

El documento definitivo del MVP confirma estas características y establece además el objetivo de validar que sea posible centralizar ofertas automáticamente, presentar información confiable y facilitar el acceso a las publicaciones originales.

**Decisión del equipo:**

Se adoptó este alcance como base del proyecto.

Se mantuvo un alcance limitado a las tres marcas y a las fuentes públicas seleccionadas. También quedaron fuera las comparaciones entre marcas, productos, precios o beneficios, así como delivery, cuentas de usuario, favoritos y notificaciones personalizadas.



## Prompt 02 — Planificación técnica inicial

**Fecha:** viernes 9 de octubre de 2026
**Hora:** 2:20 p. m.

**Objetivo:**
Definir las tecnologías iniciales del proyecto y establecer una planificación general para comenzar su construcción, teniendo en cuenta que se trata de un proyecto académico de la carrera.

**Prompt utilizado:**

> Bien ahora quiero que pasemos a crear el proyecto.
>
> La idea es que como base de datos usar MySql.
>
> Para el Back-End usar C# (Cuento Con Visual Studio 2026), no se si deberiamo usar Identity para el rol de usuario, eso te lo pregunto y veremos como lo creamos.
>
> Y para el Front End voy a usar React y cuento con Visual Studio Code.
>
> Dime todos los pasos que debemos realizar para ir construyendo todo y tambien algo muy importante es que al subir todo a mi github debo subir mi "User Historys" (O como se escriba) ayudame explicandome que son, como hacerlas ya que todo esto es un proyecto de mi carrera.

**Resultado / aporte:**

La consulta permitió pasar de la definición del MVP a la planificación técnica del sistema.

Se establecieron inicialmente las siguientes tecnologías:

* **MySQL** para la base de datos.
* **C#** para el backend.
* **Visual Studio 2026** como entorno de desarrollo del backend.
* **React** para el frontend.
* **Visual Studio Code** como entorno de desarrollo del frontend.

También se planteó la necesidad de analizar posteriormente si Identity era necesario para gestionar usuarios y roles.

Además, la consulta permitió incorporar al proceso de desarrollo la necesidad de documentar las User Stories y utilizar GitHub como parte del trabajo académico.

**Decisión del equipo:**

Se decidió utilizar MySQL, C# con ASP.NET Core y React como tecnologías principales del proyecto.

La incorporación de Identity quedó como una decisión pendiente de evaluar según las necesidades reales del MVP, en lugar de incorporarla automáticamente.

También se decidió documentar las User Stories y utilizar el repositorio de GitHub como parte del seguimiento y documentación del proyecto.


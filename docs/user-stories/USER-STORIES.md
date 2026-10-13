# Historias de usuario — Centralizador de ofertas de comida rápida

## 1. Información general

**Proyecto:** Centralizador de ofertas de comida rápida.

**Objetivo:** Centralizar ofertas publicadas en páginas web públicas seleccionadas de McDonald's, Burger King y Mostaza, permitiendo consultar su información esencial y acceder a la publicación original.

**Alcance:** MVP inicial.

**Usuarios principales:** Visitantes que consultan ofertas.

**Procesos internos:** Extracción automática, procesamiento, clasificación, normalización y actualización de publicaciones.

---

## 2. Historias de usuario

### HU-01 — Consultar ofertas disponibles

**Como** visitante,

**quiero** consultar las ofertas disponibles de las marcas incluidas,

**para** encontrar promociones sin tener que revisar cada página por separado.

**Prioridad:** Alta.

**Criterios de aceptación:**

- El sistema muestra las ofertas que tiene registradas y considera disponibles.
- Cada oferta identifica la marca a la que pertenece.
- La información muestra los datos esenciales que se hayan podido obtener.
- Cada oferta incluye un enlace a su publicación original cuando esté disponible.
- Si no hay ofertas para mostrar, el sistema presenta un mensaje comprensible.

---

### HU-02 — Comprender las condiciones de una oferta

**Como** visitante,

**quiero** consultar un resumen claro de una oferta y sus condiciones conocidas,

**para** comprender el beneficio y saber qué restricciones debo tener en cuenta.

**Prioridad:** Alta.

**Criterios de aceptación:**

- El sistema presenta el beneficio identificado en la publicación.
- Se muestran las condiciones relevantes que se hayan podido extraer.
- Se presentan las fechas de vigencia cuando estén disponibles y hayan podido verificarse.
- La información no inventa condiciones que no estén respaldadas por la publicación.
- El visitante puede acceder a la fuente original para consultar más detalles.

---

### HU-03 — Acceder a la publicación original

**Como** visitante,

**quiero** abrir la publicación original de una oferta,

**para** consultar directamente la información publicada por la marca.

**Prioridad:** Alta.

**Criterios de aceptación:**

- Cada oferta dispone de un enlace a su fuente original cuando se haya podido obtener.
- El enlace corresponde a la publicación asociada con esa oferta.
- Si el enlace no está disponible, el sistema no presenta una dirección inventada.
- El visitante recibe una indicación comprensible si no puede acceder a la fuente desde el sistema.

---

### HU-04 — Informar una oferta aparentemente vencida o incorrecta

**Como** visitante,

**quiero** reportar una oferta que parece vencida o contiene información incorrecta,

**para** contribuir a mantener confiable la información del centralizador.

**Prioridad:** Alta.

**Criterios de aceptación:**

- El visitante puede iniciar un reporte desde una oferta.
- El reporte queda asociado a la oferta correspondiente.
- El visitante puede seleccionar el motivo del reporte.
- El sistema confirma si el reporte se registró correctamente.
- El sistema no afirma que una oferta está vencida solamente porque un visitante la haya reportado.

---

### HU-05 — Informar un enlace que no funciona

**Como** visitante,

**quiero** informar que el enlace de una oferta no funciona,

**para** ayudar a detectar problemas de acceso a la publicación original.

**Prioridad:** Media.

**Criterios de aceptación:**

- El visitante puede indicar que el enlace de una oferta presenta un problema.
- El reporte queda asociado a la oferta correspondiente.
- El sistema confirma la recepción del reporte.
- El reporte no modifica automáticamente la publicación original.

---

## 3. Necesidades del procesamiento automático

Estas necesidades describen comportamientos internos del sistema. No son historias de usuario de un visitante, pero forman parte del alcance funcional del MVP.

### PA-01 — Obtener publicaciones automáticamente

El sistema debe obtener información de las páginas públicas seleccionadas de McDonald's, Burger King y Mostaza sin depender de la carga manual de cada oferta.

### PA-02 — Extraer y normalizar información

El sistema debe identificar los datos relevantes de las publicaciones y normalizar nombres, precios y fechas cuando corresponda.

### PA-03 — Procesar publicaciones con imágenes o documentos

Cuando una publicación contenga información relevante en imágenes o documentos compatibles, el sistema debe intentar extraerla mediante OCR u otras técnicas adecuadas.

### PA-04 — Clasificar y resumir publicaciones

El sistema puede utilizar IA para clasificar publicaciones, generar resúmenes y ayudar a interpretar condiciones. Los resultados deben validarse y no deben presentarse como hechos confirmados si la fuente no los respalda.

### PA-05 — Mantener actualizada la información

El sistema debe contemplar la actualización de las ofertas obtenidas y evitar presentar como vigentes aquellas cuya expiración se haya podido confirmar.

### PA-06 — Conservar la referencia a la fuente

El sistema debe conservar el vínculo entre la información procesada y su publicación original para facilitar la consulta y la verificación.

---

## 4. Fuera del alcance del MVP

El MVP inicial no incluye:

- Gestionar pedidos o entregas a domicilio.
- Comparar ofertas entre marcas, productos, precios o beneficios.
- Comparar códigos promocionales o condiciones de distintas publicaciones.
- Personalizar las ofertas según gustos o compras anteriores.
- Enviar notificaciones personalizadas.
- Garantizar la cobertura de todas las promociones existentes en cualquier canal.
- Afirmar que una oferta está vigente cuando no existen datos suficientes para comprobarlo.

---

## 5. Observaciones

Las ofertas y sus condiciones dependen de la información disponible en las publicaciones originales.

La extracción automática, el OCR y la IA pueden cometer errores. Por eso, el sistema debe conservar la referencia a la fuente y distinguir entre datos verificados, datos no disponibles y resultados que requieren comprobación.
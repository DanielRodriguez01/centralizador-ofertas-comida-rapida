# Requisitos del sistema — Centralizador de ofertas de comida rápida

## 1. Objetivo

Desarrollar una aplicación web que centralice ofertas publicadas en páginas web públicas seleccionadas de McDonald's, Burger King y Mostaza.

El sistema debe obtener y procesar información automáticamente, presentar las ofertas de forma comprensible y permitir que los visitantes accedan a las publicaciones originales.

También debe ofrecer un mecanismo para informar ofertas aparentemente vencidas, información incorrecta o enlaces que no funcionan.

## 2. Alcance

El MVP inicial contempla:

- Obtención automática de publicaciones desde las fuentes seleccionadas.
- Extracción y normalización de información.
- Clasificación y resumen de publicaciones mediante IA cuando resulte útil.
- Uso de OCR cuando la información relevante se encuentre en imágenes.
- Presentación de ofertas y sus condiciones conocidas.
- Acceso a las publicaciones originales.
- Registro de reportes enviados por los visitantes.
- Actualización de la información obtenida.

La extracción debe ser automática y no depender de que una persona cargue manualmente cada oferta.

## 3. Requisitos funcionales

### RF-01 — Consultar ofertas

El sistema debe permitir consultar las ofertas registradas y presentar la información esencial disponible de cada una.

### RF-02 — Identificar la marca

El sistema debe identificar la marca a la que pertenece cada oferta.

### RF-03 — Presentar los beneficios y condiciones

El sistema debe mostrar los beneficios y las condiciones relevantes que se hayan podido extraer de la publicación original.

### RF-04 — Acceder a la fuente original

El sistema debe conservar y presentar el enlace a la publicación original cuando esté disponible.

### RF-05 — Obtener publicaciones automáticamente

El sistema debe obtener información de las páginas públicas seleccionadas de McDonald's, Burger King y Mostaza sin depender de la carga manual de cada oferta.

### RF-06 — Extraer y normalizar información

El sistema debe extraer los datos relevantes y normalizar nombres, precios y fechas cuando corresponda.

### RF-07 — Procesar información en imágenes y documentos

El sistema debe poder utilizar OCR u otras técnicas adecuadas para intentar extraer información de imágenes y documentos compatibles.

### RF-08 — Clasificar y resumir publicaciones

El sistema debe poder utilizar IA para clasificar publicaciones, resumir su contenido e interpretar condiciones cuando resulte útil.

Los resultados generados por IA deben contrastarse con la información disponible y no deben presentarse como hechos confirmados cuando no estén respaldados por la fuente.

### RF-09 — Actualizar ofertas

El sistema debe contemplar la actualización automática de la información obtenida para reducir la posibilidad de mostrar datos desactualizados.

### RF-10 — Reportar ofertas aparentemente vencidas

El sistema debe permitir que un visitante informe que una oferta parece haber vencido.

### RF-11 — Reportar información incorrecta

El sistema debe permitir que un visitante informe datos aparentemente incorrectos en una oferta.

### RF-12 — Reportar enlaces que no funcionan

El sistema debe permitir que un visitante informe problemas con el enlace a una publicación original.

### RF-13 — Confirmar la recepción de reportes

El sistema debe informar al visitante si su reporte se registró correctamente.

### RF-14 — Asociar reportes con ofertas

Cada reporte debe quedar asociado a la oferta correspondiente para facilitar su revisión.

## 4. Requisitos no funcionales

### RNF-01 — Usabilidad

La interfaz debe presentar la información de manera clara y permitir que los visitantes comprendan las ofertas sin conocimientos técnicos.

### RNF-02 — Adaptabilidad

La interfaz debe poder utilizarse en computadoras y dispositivos móviles.

### RNF-03 — Trazabilidad de la información

El sistema debe conservar la referencia a la publicación original para facilitar la comprobación de los datos extraídos.

### RNF-04 — Integridad de la información

El sistema no debe inventar beneficios, precios, fechas, condiciones ni enlaces que no estén respaldados por información disponible.

### RNF-05 — Mantenibilidad

El código debe organizarse de manera que permita modificar o ampliar funcionalidades sin mezclar innecesariamente responsabilidades diferentes.

### RNF-06 — Manejo de errores

El sistema debe contemplar fallos de extracción, enlaces inaccesibles, información incompleta y errores al registrar reportes.

### RNF-07 — Rendimiento

La aplicación debe procurar tiempos de respuesta adecuados para la consulta habitual de ofertas. Los objetivos cuantitativos de rendimiento se definirán y verificarán durante las pruebas.

### RNF-08 — Compatibilidad de fuentes

La extracción debe diseñarse teniendo en cuenta las características y limitaciones de las páginas seleccionadas, respetando las condiciones de acceso aplicables.

## 5. Fuera del alcance del MVP

El MVP no contempla:

- Gestionar pedidos o entregas a domicilio.
- Comparar ofertas entre marcas, productos, precios o beneficios.
- Comparar códigos promocionales o condiciones entre publicaciones.
- Personalizar ofertas según gustos o compras anteriores.
- Enviar notificaciones personalizadas.
- Garantizar la cobertura de todas las promociones publicadas en cualquier canal.
- Confirmar automáticamente la vigencia de una oferta cuando no existan datos suficientes para comprobarla.

## 6. Observaciones

La disponibilidad y la exactitud de la información dependen de las fuentes originales y de la capacidad de extracción.

El uso de OCR e IA puede producir resultados incorrectos. Por ello, el sistema debe conservar la referencia a la fuente y contemplar la validación de los datos antes de presentarlos como confirmados.

La implementación deberá verificar la viabilidad técnica de las fuentes seleccionadas y de los mecanismos de extracción previstos.
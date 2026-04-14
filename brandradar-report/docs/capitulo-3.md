[← Capítulo II](./capitulo-2.md) &nbsp;|&nbsp; [← Volver al índice](../../README.md)

---

<div align="center">

# Capítulo III: Requirements Specification

</div>

---

## 3.1. User Stories

*(Introducción a los User Stories y Epics definidos para BrandRadar)*

> **Nota:** Los criterios de aceptación se redactan en tiempo presente, tercera persona, sin referencia a detalles de interfaz de usuario, y siguen la estructura **Gherkin (Given-When-Then)**.


| Epic / Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|:---------------:|:------:|:------------|:------------------------|:-------------------------:|
| **EP01** | `Real-Time Monitoring & Data Collection` | Sistema de recolección automatizada de datos desde redes sociales y fuentes digitales para el monitoreo de marcas. | — | — |
| US01 | `Integración de APIs Externas` | Como `Analista de Marketing`, quiero `conectar las API de Twitter e Instagram al sistema`, para `recolectar menciones de mi marca de forma automatizada`. | **Scenario 1:** Vincular cuenta exitosamente <br> **Given** que el usuario está en la sección de integraciones <br> **When** ingresa las credenciales válidas de la API <br> **Then** el sistema confirma la conexión y empieza a sincronizar menciones. | EP01 |
| US02 | `Filtrado de Exclusión` | Como `Dueño de un pequeño negocio`, quiero `definir palabras clave de exclusión (keywords negativas)`, para `evitar que el sistema capture ruido o menciones irrelevantes que no pertenecen a mi marca`. | **Scenario 1:** Agregar keyword de exclusión <br> **Given** que existen menciones de homónimos irrelevantes <br> **When** el usuario añade la palabra al "Blacklist" <br> **Then** el feed deja de mostrar publicaciones que contengan dicho término. | EP01 |
| US03 | `Live Feed Monitor` | Como `Community Manager`, quiero `ver un feed en vivo de las publicaciones recolectadas`, para `tener una visión inmediata de la conversación actual`. | **Scenario 1:** Actualización dinámica <br> **Given** que el usuario tiene abierto el dashboard principal <br> **When** una nueva mención es detectada por el backend <br> **Then** la interfaz se actualiza automáticamente mostrando el nuevo post al inicio. | EP01 |
| US04 | `Implementación de Webhooks` | Como `Desarrollador`, quiero `que el sistema use Webhooks para las notificaciones`, para `asegurar que la latencia entre la publicación y la alerta sea mínima`. | **Scenario 1:** Registro de Endpoint <br> **Given** que el desarrollador tiene una URL de escucha configurada <br> **When** registra el Webhook en el panel de BrandRadar <br> **Then** el sistema envía un paquete JSON de prueba para validar la conexión. | EP01 |
| **EP02** | `AI Sentiment Analysis` | Módulo de procesamiento de lenguaje natural (NLP) encargado de categorizar el tono emocional de las menciones recolectadas. | — | — |
| US05 | `Detección de Sarcasmo e Ironía` | Como `Gerente de Marca`, quiero `que el sistema identifique el sarcasmo en los comentarios`, para `que el análisis de sentimiento sea preciso y no arroje falsos positivos`. | **Scenario 1:** Clasificación de tono irónico <br> **Given** un comentario con palabras positivas pero contexto negativo <br> **When** el motor de IA procesa el texto <br> **Then** lo clasifica correctamente como "Negativo" basándose en el análisis de contexto. | EP02 |
| US06 | `Ajuste Manual de Polaridad` | Como `Analista de Datos`, quiero `poder corregir manualmente la polaridad de un comentario (cambiar de neutro a negativo)`, para `entrenar al modelo de IA con contextos específicos de mi industria`. | **Scenario 1:** Corrección de etiqueta <br> **Given** una mención mal categorizada por el sistema <br> **When** el analista selecciona la opción "Corregir Sentimiento" <br> **Then** el sistema actualiza la métrica y guarda la corrección para mejorar el algoritmo. | EP02 |
| US07 | `Visualización de Word Cloud` | Como `Usuario del sistema`, quiero `ver una nube de palabras (word cloud) basada en sentimientos`, para `identificar qué conceptos específicos están asociados a la frustración o alegría del cliente`. | **Scenario 1:** Generación de nube por sentimiento <br> **Given** que el usuario selecciona el filtro "Sentimiento Negativo" <br> **When** carga el reporte visual <br> **Then** se muestran los términos más repetidos en las quejas con un tamaño proporcional a su frecuencia. | EP02 |
| **EP03** | `Crisis Management & Alerts` | Herramientas de detección temprana y protocolos de acción ante incidentes que pongan en riesgo la reputación de la marca. | — | — |
| US08 | `Configuración de Semáforo de Crisis` | Como `Jefe de PR`, quiero `establecer un "Semáforo de Crisis" configurable`, para `que el equipo sepa visualmente cuándo la situación requiere intervención legal o corporativa`. | **Scenario 1:** Activación de Alerta Roja <br> **Given** un umbral de 50 menciones negativas en menos de una hora <br> **When** se alcanza o supera dicho límite <br> **Then** el dashboard principal cambia a color rojo y emite una alerta visual persistente. | EP03 |
| US09 | `Alertas Multicanal en Móvil` | Como `Usuario`, quiero `recibir alertas de crisis vía Telegram o WhatsApp`, para `estar enterado incluso si no estoy frente a la computadora`. | **Scenario 1:** Notificación externa inmediata <br> **Given** que el sistema detecta una anomalía reputacional <br> **When** el usuario tiene vinculado su perfil de mensajería <br> **Then** recibe un mensaje instantáneo con el resumen de la crisis y un enlace de acceso rápido. | EP03 |
| US10 | `Asignación de Tickets de Respuesta` | Como `Operador de Soporte`, quiero `asignar una mención negativa a un miembro específico del equipo`, para `que se gestione como un ticket de atención al cliente de forma inmediata`. | **Scenario 1:** Derivación de caso crítico <br> **Given** una mención negativa detectada <br> **When** el operador selecciona a un responsable del equipo de atención <br> **Then** el sistema crea un ticket y notifica al responsable para su resolución. | EP03 |


<!--
| Epic / Story ID | Título | Descripción | Criterios de Aceptación | Relacionado con (Epic ID) |
|:---------------:|:------:|:------------|:------------------------|:-------------------------:|
| **EP01** | `Real-Time Monitoring & Data Collection` | *(Descripción del Epic)* | — | — |
| US01 | `[Título de User Story]` | Como `Analista de Marketing`, quiero `conectar las API de Twitter e Instagram al sistema`, para `recolectar menciones de mi marca de forma automatizada.`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| US02 | `[Título de User Story]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP01 |
| **EP02** | `[Título del Epic 2]` | *(Descripción del Epic)* | — | — |
| US03 | `[Título de User Story]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP02 |
| **EP0n** | `[Landing Page Epic]` | *(Epic para user stories del sitio estático)* | — | — |
| US0n | `[User Story Landing Page]` | Como visitante, deseo `[acción]`, para `[beneficio]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[contexto]` <br> **When** `[acción]` <br> **Then** `[resultado esperado]` | EP0n |
| **TS01** | `[Technical Story — API]` | Como Developer, deseo `[endpoint]`, para `[propósito]`. | **Scenario 1:** `[Nombre]` <br> **Given** `[request context]` <br> **When** `[se llama al endpoint]` <br> **Then** `[response esperado]` | — |
-->
---

## 3.2. Impact Mapping

*(Introducción y capturas del Impact Mapping elaborado en la herramienta indicada — UXPressia)*

*(Business Goals deben cumplir criterios SMART. Ejemplo: "Alcanzar los 600 usuarios suscritos al plan A en el lapso de 8 meses.")*

![Impact Map](../assets/impact-mapping/impact-map.png)

*(Explicación del Impact Map: Business Goals, Actors/Personas, Impacts, Deliverables y User Stories)*

---

## 3.3. Product Backlog

*(Introducción al Product Backlog de BrandRadar)*

> **Herramienta utilizada:** `[Pivotal Tracker / JetBrains YouTrack / Jira / Trello]`
>
> **URL del Product Backlog:** [`[URL pública del Product Backlog]`](`[URL]`)

*(Captura del Product Backlog en la herramienta indicada)*

![Product Backlog](../assets/product-backlog/product-backlog.png)

| # Orden | User Story ID | Título | Descripción | Story Points |
|:-------:|:-------------:|:------:|:------------|:------------:|
| 1 | US01 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | `1 / 2 / 3 / 5 / 8` |
| 2 | US02 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 3 | US03 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 4 | US04 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| 5 | US05 | `[Título]` | Como `[rol]`, deseo `[acción]`, para `[beneficio]`. | |
| n | TS01 | `[Technical Story]` | Como Developer, deseo `[endpoint]`, para `[propósito]`. | |

---

<div align="center">

[← Capítulo II](./capitulo-2.md) &nbsp;|&nbsp; [Capítulo IV →](./capitulo-4.md) &nbsp;|&nbsp; [← Volver al índice](../../README.md)

</div>

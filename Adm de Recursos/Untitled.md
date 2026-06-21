

  

## Alcance

- Archivos revisados en `src/`, `prisma/schema.prisma`, `prisma.config.ts`, `chat-bot.ts`, `test-e2e.ts`, `README.md` y `package.json`.

  

## Descripcion del proyecto

El proyecto es un bot conversacional para RepuestosShop, construido con NestJS, LangGraph y LangChain. Recibe mensajes de WhatsApp via Kapso, normaliza el payload, conversa con el usuario para recolectar datos de cliente/vehiculo/repuesto, y cuando el agente genera un JSON, guarda datos en PostgreSQL con Prisma, genera un PDF con Gotenberg, lo sube a Supabase Storage y lo envia al cliente por WhatsApp. Ademas, analiza imagenes con GPT-4o y usa Redis para buffer de mensajes y estado efimero.

  

## Problemas y riesgos detectados

  

### 1) Estado de chat inconsistente entre Redis y BD

- Que puede fallar: el comando de ver solicitudes se permite aunque el chat este en curso.

- Por que puede fallar: el estado del chat se guarda en BD por `MemoryService`, pero el flujo de ver solicitudes usa Redis (`RedisService.getChatState`). No hay sincronizacion entre ambos. Cuando el agente pasa a `EN_CURSO`, Redis sigue en `NUEVO` porque nunca se actualiza ahi.

- Impacto: el usuario puede pedir ver solicitudes en medio de una solicitud activa; rompe el flujo conversacional y puede generar respuestas fuera de contexto.

  

### 2) Estado en BD no se reinicia al finalizar solicitud

- Que puede fallar: el estado en BD queda en `EN_CURSO` aun luego de generar un JSON.

- Por que puede fallar: tras `handleSolicitudJson`, solo se actualiza Redis a `NUEVO`. `MemoryService.setChatState` no se llama al finalizar.

- Impacto: futuros flujos que dependan del estado almacenado en BD pueden bloquearse o comportarse de forma incorrecta.

  

### 3) Buffer de mensajes en Redis no se usa en el webhook

- Que puede fallar: mensajes consecutivos pueden procesarse por separado y perder contexto.

- Por que puede fallar: `RedisService.addToBuffer` y `combineAndClearBuffer` existen, pero `WebhookController` no los utiliza.

- Impacto: conversaciones con multiples mensajes seguidos pueden generar respuestas erraticas o incompletas, reduciendo autonomia.

  

### 4) Ausencia de control de idempotencia en webhook

- Que puede fallar: duplicacion de solicitudes por reintentos del proveedor.

- Por que puede fallar: no hay control de deduplicacion por `message.id` o timestamp.

- Impacto: multiples registros en BD, multiples PDFs enviados y confusion operativa.

  

### 5) Webhook sin autenticacion ni validacion de firma

- Que puede fallar: terceros pueden enviar payloads falsos al webhook.

- Por que puede fallar: el endpoint acepta cualquier `POST` sin firma ni token.

- Impacto: spam, creacion de datos no deseados, gastos de API y degradacion del servicio.

  

### 6) Manejo de imagenes con clave basada en nombre de archivo

- Que puede fallar: colisiones y sobrescritura de imagenes.

- Por que puede fallar: `generateImageKey` deriva un hash del nombre de archivo, no del contenido ni de un identificador unico del mensaje.

- Impacto: imagenes distintas pueden terminar con la misma clave y sobrescribir archivos, asociando imagen incorrecta a una solicitud.

  

### 7) Inconsistencia de rutas de imagen entre BD y Storage

- Que puede fallar: enlaces almacenados en BD no corresponden a la ubicacion real.

- Por que puede fallar: en BD se guarda `/repuestoshop/fotos-repuestos/confirmados/${key}`, pero en Storage se usa `confirmed/${imageKey}.png`.

- Impacto: integraciones que lean la URL desde BD pueden fallar al resolver la imagen.

  

### 8) Dependencia en `fetch` global sin garantia de runtime

- Que puede fallar: descarga de imagenes falla en entornos sin `fetch` global.

- Por que puede fallar: `StorageService.downloadImageFromUrl` usa `fetch` sin import.

- Impacto: imagenes no se descargan ni almacenan, el agente pierde contexto visual.

  

### 9) Validacion minima del JSON generado por el agente

- Que puede fallar: datos incompletos o mal formateados pasan a BD.

- Por que puede fallar: `parseAgentResponse` solo comprueba existencia de `cliente`, `vehiculo`, `repuesto` y no valida campos obligatorios ni tipos.

- Impacto: registros incompletos, PDFs con datos faltantes y frustracion del usuario.

  

### 10) LLM puede devolver JSON con texto adicional

- Que puede fallar: el JSON no se detecta y el flujo no genera solicitud.

- Por que puede fallar: el agente puede incluir texto extra o formato diferente al esperado. La deteccion en `parseAgentResponse` es estricta.

- Impacto: el usuario queda sin cierre de solicitud y se estanca el flujo.

  

### 11) Log de informacion sensible en consola

- Que puede fallar: exposicion de datos personales.

- Por que puede fallar: se imprime contenido del mensaje y datos del usuario en consola.

- Impacto: riesgo de cumplimiento y privacidad en entornos productivos.

  

### 12) PDF depende de servicio externo sin reintentos ni timeout

- Que puede fallar: generacion de PDF se queda sin respuesta o falla de forma intermitente.

- Por que puede fallar: `axios` no define timeout ni reintentos en `PdfService`.

- Impacto: el usuario puede no recibir el PDF aunque la solicitud haya sido creada.

  

### 13) Redis queda deshabilitado tras un error y no reintenta

- Que puede fallar: el buffer y el estado se desactivan permanentemente.

- Por que puede fallar: ante errores se marca `isConnected = false` y no existe logica de reconexion activa.

- Impacto: funcionalidades de buffer y estado dejan de operar, degradando autonomia.

  

### 14) Discrepancia entre JSON esperado y esquema de BD

- Que puede fallar: campos como `año` pueden omitirse o venir como `anio`.

- Por que puede fallar: el JSON usa clave `año` con `ñ`, mientras el schema usa `anio`. El modelo puede devolver variantes.

- Impacto: datos incompletos en BD y PDF con campos vacios.

  

### 15) Mensajes no soportados se responden como texto generico

- Que puede fallar: documentos o videos recibidos se ignoran con respuesta fija.

- Por que puede fallar: `normalizeKapsoPayload` clasifica tipos no previstos como `other`.

- Impacto: el usuario puede enviar informacion relevante y recibir rechazo, afectando autonomia.

  

### 16) Falta de manejo de concurrencia por sesion

- Que puede fallar: dos mensajes simultaneos de la misma sesion pueden intercalar estados.

- Por que puede fallar: el flujo no bloquea por sesion ni usa colas; depende de orden de llegada.

- Impacto: respuestas contradictorias o JSON armado con datos mezclados.

  

### 17) Costo y latencia por multiples llamadas LLM

- Que puede fallar: tiempos de respuesta altos en picos de trafico.

- Por que puede fallar: cada imagen usa Vision, y cada mensaje usa LLM principal y subagente.

- Impacto: demoras en el chat, perdida de continuidad, mayor costo operativo.

  

### 18) Fallbacks silenciosos pueden ocultar fallos reales

- Que puede fallar: operaciones criticas fallan sin alerta clara.

- Por que puede fallar: varios `catch` retornan `null` o `false` sin propagacion de error.

- Impacto: el sistema aparenta funcionar pero no completa acciones clave.

  

### 19) Dependencia fuerte de instrucciones del prompt

- Que puede fallar: el agente no sigue reglas y rompe el flujo.

- Por que puede fallar: no hay validacion estricta de salida, solo parsing parcial.

- Impacto: se reciben respuestas fuera de contrato y no se genera solicitud.

  

### 20) Inexistencia de pruebas automatizadas para casos de negocio

- Que puede fallar: regresiones en flujos criticos.

- Por que puede fallar: existen pruebas de ejemplo, pero no cubren escenarios de negocio ni validan JSON end-to-end.

- Impacto: cambios futuros pueden romper el bot sin deteccion temprana.

  

## Mejoras para autonomia total del bot

- Orquestacion de mensajes por sesion usando el buffer de Redis, consolidando mensajes antes de llamar al agente.

- Estado unico de conversacion con fuente de verdad consistente (BD o Redis), y actualizaciones sincronizadas.

- Validacion estricta del JSON del agente con un esquema formal y rechazo de respuestas fuera de contrato.

- Politicas de idempotencia en webhook usando `message.id` y almacenamiento de eventos procesados.

- Control de autenticacion del w
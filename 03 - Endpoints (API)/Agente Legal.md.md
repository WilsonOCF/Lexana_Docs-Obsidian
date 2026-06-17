# Endpoints — Agente Legal IA
### Nota sobre archivos adjuntos
El agente legal actualmente **no procesa imágenes**. 
Al subir una imagen el payload no cambia — solo se envía 
el texto del prompt. El agente responde indicando que no 
puede ver ni procesar imágenes y sugiere describir el 
contenido en texto.

---

## GET aiAgent.getHistory

**¿Cuándo se llama?** Al cargar el módulo de Agente Legal.
**¿Para qué sirve?** Trae el historial de mensajes de la 
sesión actual.

### Payload
| Campo | Tipo | Descripción |
| --- | --- | --- |
| sessionId | string | ID único de la conversación |

### Response
Lista de mensajes anteriores. Vacía si es conversación nueva.

---

## POST ai-agent

**¿Cuándo se llama?** Al enviar un mensaje en el chat.
**¿Para qué sirve?** Envía el mensaje del usuario al agente 
legal IA y recibe la respuesta en tiempo real.

### Payload (lo que envía)

| Campo | Tipo | Descripción |
| --- | --- | --- |
| endpoint | string | Origen: "web" |
| source | string | Fuente: "web" |
| user_id | string | ID del usuario |
| session_id | string | ID de la conversación activa |
| body.prompt | string | Mensaje del usuario |

### Response
La respuesta llega en formato **streaming** — palabra por palabra 
en tiempo real. Cada fragmento tiene este formato:

```json
data: {"text": "fragmento de texto"}
```

### Modelo de IA
Usa **Claude 4 Opus** de Anthropic como modelo base.

### Notas
- Cada conversación tiene un session_id único
- El streaming permite mostrar la respuesta mientras se genera
- Soporta búsqueda web cuando se activa el botón "Web"
- Tipos de consulta: Consulta General y otros modos
### Nota sobre opciones de configuración
- El botón **Web** y el selector de **tipo de consulta** 
  (Consulta General, Búsqueda Jurisprudencial, etc.) no modifican 
  el payload enviado al servidor.
- Estas opciones probablemente afectan el comportamiento interno 
  del servidor (prompt del sistema, herramientas disponibles).
- El campo `endpoint: "web"` indica el origen de la petición 
  (interfaz web), no si la búsqueda web está activada.


---

## GET aiAgent.listSessions

**¿Cuándo se llama?** Al hacer clic en "Historial" o al 
cargar el módulo.
**¿Para qué sirve?** Trae la lista de conversaciones anteriores 
del usuario con el agente legal.

### Response

| Campo     | Tipo     | Descripción                        |
| --------- | -------- | ---------------------------------- |
| id        | string   | ID único de la sesión (session_id) |
| title     | string   | Título de la conversación          |
| createdAt | datetime | Fecha de creación                  |
| updatedAt | datetime | Fecha de última actualización      |


---

## POST aiAgent.createSession

**¿Cuándo se llama?** Al hacer clic en "+ Nueva conversación".
**¿Para qué sirve?** Crea una nueva sesión de chat con el 
agente legal.

### Payload
Vacío — no requiere datos de entrada.

### Response

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único de la nueva sesión |
| title | string | Título por defecto: "Nueva conversación" |
| createdAt | datetime | Fecha de creación |
| updatedAt | datetime | Fecha de actualización |

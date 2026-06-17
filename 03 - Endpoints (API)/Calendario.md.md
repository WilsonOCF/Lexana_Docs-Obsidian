# Endpoints — Calendario

---
# Endpoints — Calendario

---

## GET calendar.list

**¿Cuándo se llama?** Al cargar el módulo de Calendario.
**¿Para qué sirve?** Trae todos los eventos del calendario 
de la organización.

---

## GET organization.listMembers

**¿Cuándo se llama?** Al abrir el formulario "+ Nuevo Evento".
**¿Para qué sirve?** Carga la lista de miembros de la organización 
para poder invitarlos al evento.

---

## POST calendar.create

**¿Cuándo se llama?** Al hacer clic en "Crear evento".
**¿Para qué sirve?** Crea un nuevo evento en el calendario.

### Payload (lo que envía)

| Campo | Tipo | Requerido | Descripción |
| --- | --- | --- | --- |
| title | string | Sí | Título del evento |
| description | string | No | Descripción del evento |
| startAt | datetime | Sí | Fecha y hora de inicio |
| endAt | datetime | Sí | Fecha y hora de fin |
| allDay | boolean | No | Si es un evento de todo el día |
| isShared | boolean | No | Si el evento es compartido |
| sharedWithUserIds | array | No | IDs de usuarios invitados |
| color | string | No | Color del evento: BLUE, RED, etc |

### Response

| Campo           | Tipo          | Descripción                          |
| --------------- | ------------- | ------------------------------------ |
| id              | string        | ID único del evento                  |
| title           | string        | Título del evento                    |
| description     | string        | Descripción                          |
| startAt         | datetime      | Fecha y hora de inicio               |
| endAt           | datetime      | Fecha y hora de fin                  |
| allDay          | boolean       | Si es todo el día                    |
| isShared        | boolean       | Si es compartido                     |
| color           | string        | Color del evento                     |
| type            | string        | Tipo: MANUAL, o generado por sistema |
| procedureId     | string / null | ID del expediente relacionado        |
| milestoneId     | string / null | ID del hito relacionado              |
| createdByUserId | string        | ID del usuario que creó el evento    |
| organizationId  | string        | ID de la organización                |
| createdAt       | datetime      | Fecha de creación                    |
| updatedAt       | datetime      | Fecha de actualización               |
## POST calendar.update

**¿Cuándo se llama?** Al guardar cambios en un evento existente.
**¿Para qué sirve?** Actualiza los datos de un evento del calendario.

### Payload (lo que envía)

| Campo | Tipo | Requerido | Descripción |
| --- | --- | --- | --- |
| id | string | Sí | ID del evento a actualizar |
| title | string | Sí | Título del evento |
| description | string | No | Descripción |
| startAt | datetime | Sí | Fecha y hora de inicio |
| endAt | datetime | Sí | Fecha y hora de fin |
| allDay | boolean | No | Si es todo el día |
| isShared | boolean | No | Si es compartido |
| sharedWithUserIds | array | No | IDs de usuarios invitados |
| color | string | No | Color del evento |

### Response
Devuelve el evento con los datos actualizados. 
El campo `updatedAt` se actualiza automáticamente.

---

## POST calendar.delete

**¿Cuándo se llama?** Al confirmar la eliminación de un evento.
**¿Para qué sirve?** Elimina un evento del calendario.

### Payload (lo que envía)

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del evento a eliminar |

### Response

| Campo   | Tipo    | Descripción                      |
| ------- | ------- | -------------------------------- |
| success | boolean | true si se eliminó correctamente |
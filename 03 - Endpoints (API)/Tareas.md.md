# Endpoints — Tareas

---

## GET auth.member.getActiveRole / milestone.listMyMilestones

**¿Cuándo se llama?** Al cargar el módulo de Tareas.
**¿Para qué sirve?** Trae el rol activo del usuario y la lista 
de tareas (hitos) asignadas.

### Bloque 1 — Rol activo del usuario

| Campo | Tipo | Descripción |
| --- | --- | --- |
| json | string | Rol del usuario: "member", "admin", "owner" |

### Bloque 2 — Hitos propios (vacío si no hay)
Lista vacía si el usuario no tiene hitos asignados con 
los filtros seleccionados.

### Bloque 3 — Lista de tareas/hitos

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único del hito |
| title | string | Título de la tarea |
| description | string | Descripción |
| dueDate | datetime | Fecha límite |
| status | string | Estado: IN_PROGRESS, PENDING, COMPLETED |
| assignerId | string | ID del usuario que asignó la tarea |
| assigneeId | string | ID del usuario asignado |
| procedureId | string | ID del expediente relacionado |
| createdAt | datetime | Fecha de creación |
| updatedAt | datetime | Fecha de actualización |

**Datos del asignado (assignee)**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del usuario |
| name | string | Nombre |
| email | string | Correo |
| role | string | Rol en el sistema |
| image | string | URL de foto de perfil |

**Archivos adjuntos (milestoneFiles)**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del archivo adjunto |
| fileId | string | ID del archivo |
| file.fileName | string | Nombre del archivo |
| file.fileType | string | Tipo: image/jpeg, etc |
| file.fileSize | number | Tamaño en bytes |
| file.fileUrl | string | URL del archivo |
| file.state | string | Estado: UPLOADED |

**Expediente relacionado (procedure)**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del expediente |
| code | string | Código del expediente |
| name | string | Nombre del expediente |
| ticketNumber | number | Número de ticket |

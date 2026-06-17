# Endpoints — Tablero Principal

---

## GET /api/auth/get-session

**¿Cuándo se llama?** Al cargar cualquier página de la plataforma.
**¿Para qué sirve?** Verifica que el usuario esté logueado y devuelve 
sus datos de sesión activa.
**¿Requiere autenticación?** Sí (envía cookie de sesión automáticamente)

### Response (lo que devuelve)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| session.id | string | ID único de la sesión |
| session.token | string | Token de autenticación |
| session.createdAt | datetime | Fecha de inicio de sesión |
| session.expiresAt | datetime | Fecha de expiración |
| session.ipAddress | string | IP del usuario |
| session.userId | string | ID del usuario logueado |
| session.activeOrganizationId | string | ID de la organización activa |
| user.name | string | Nombre del usuario |
| user.email | string | Correo del usuario |
| user.role | string | Rol del usuario (ej: "user") |
| user.banned | boolean | Si el usuario está baneado |

### Ejemplo de respuesta
```json
{
  "session": {
    "userId": "86b2988e-...",
    "activeOrganizationId": "deac97aa-...",
    "expiresAt": "2026-06-21T15:53:31.103Z"
  },
  "user": {
    "name": "Wilson Carrasco",
    "email": "carrascowils1111@gmail.com",
    "role": "user"
  }
}
```

---

---

## POST dashboardApp.getMetrics / dashboardApp.getTasksByMember

**¿Cuándo se llama?** Al cargar el Tablero Principal.
**¿Para qué sirve?** Carga todos los datos del tablero en una sola llamada.

### Bloque 1 — Métricas generales (las 4 tarjetas)

| Campo | Tipo | Descripción |
| --- | --- | --- |
| totalProcedures | number | Total de expedientes activos |
| newProcedures | number | Expedientes nuevos (últimos 7 días) |
| overdueTasks | number | Tareas que superaron su fecha límite |
| lastSinoeCheck | datetime / null | Última revisión de SINOE |

### Bloque 2 — Tareas sin cerrar por miembro

| Campo | Tipo | Descripción |
| --- | --- | --- |
| memberId | string | ID del miembro |
| memberName | string | Nombre del miembro |
| count | number | Cantidad de tareas sin cerrar |

### Bloque 3 — Expedientes por área legal

| Campo | Tipo | Descripción |
| --- | --- | --- |
| areaName | string | Nombre del área legal |
| areaId | string | ID del área |
| count | number | Cantidad de expedientes |

### Bloque 4 — Eventos SINOE
Lista vacía si no hay notificaciones pendientes.

### Bloque 5 — Miembros de la organización

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del miembro |
| role | string | Rol: owner, admin, member |
| user.name | string | Nombre del usuario |
| user.email | string | Correo del usuario |

### Bloque 6 — Usuario logueado

| Campo | Tipo | Descripción |
| --- | --- | --- |
| name | string | Nombre del usuario |
| email | string | Correo |
| role | string | Rol en el sistema |
| banned | boolean | Si está baneado |

### Bloque 7 — Agenda del día
Lista vacía si no hay reuniones para hoy.

---

## POST organization.listOrganizations / organization.getActiveOrganization

**¿Cuándo se llama?** Al cargar cualquier página de la plataforma.
**¿Para qué sirve?** Trae la lista de organizaciones del usuario y 
los detalles completos de la organización activa (miembros, 
invitaciones, equipos).

### Bloque 1 — Lista de organizaciones del usuario

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único de la organización |
| name | string | Nombre de la organización |
| slug | string | Identificador en la URL |
| logo | string | URL del logo |
| createdAt | datetime | Fecha de creación |

### Bloque 2 — Organización activa (detalle completo)

**Datos generales**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID de la organización |
| name | string | Nombre |
| slug | string | Identificador en URL |
| logo | string | URL del logo |

**Invitaciones**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID de la invitación |
| email | string | Correo invitado |
| role | string | Rol asignado: admin, member |
| status | string | Estado: pending, accepted |
| expiresAt | datetime | Fecha de expiración |
| inviterId | string | ID del usuario que invitó |

**Miembros**

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del miembro |
| userId | string | ID del usuario |
| role | string | Rol: owner, admin, member |
| createdAt | datetime | Fecha de ingreso |
| user.name | string | Nombre del usuario |
| user.email | string | Correo del usuario |
| user.image | string | URL de foto de perfil |

### Bloque 3 — Usuario logueado
Mismos campos que en `get-session`.

### Bloque 4 — Equipos
Devuelve null si

---

## POST notification.getUnreadCount

**¿Cuándo se llama?** Periódicamente mientras el usuario está en 
cualquier página de la plataforma.
**¿Para qué sirve?** Obtiene la cantidad de notificaciones sin leer 
para mostrar el contador en el menú.
**Frecuencia:** Se llama múltiples veces automáticamente para 
mantener el contador actualizado en tiempo real.

### Response

| Campo | Tipo | Descripción |
| --- | --- | --- |
| count | number | Cantidad de notificaciones sin leer |

### Ejemplo
```json
{ "count": 0 }
```
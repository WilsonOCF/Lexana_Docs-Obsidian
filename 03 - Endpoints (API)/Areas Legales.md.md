# Endpoints — Áreas Legales

---

## GET legalArea.list

**¿Cuándo se llama?** Al cargar el módulo de Áreas Legales.
**¿Para qué sirve?** Trae la lista de todas las áreas legales 
de la organización.

### Response

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único del área legal |
| name | string | Nombre del área |
| slug | string | Identificador único en URL |
| description | string | Descripción del área |
| logo | string | URL del logo o imagen |
| createdAt | datetime | Fecha de creación |
| updatedAt | datetime | Fecha de última actualización |
| organizationId | string | ID de la organización |

---

## POST legalArea.create

**¿Cuándo se llama?** Al guardar el formulario de "+ Nueva Área Legal".
**¿Para qué sirve?** Crea una nueva área legal en la organización.

### Payload (lo que envía)

| Campo | Tipo | Requerido | Descripción |
| --- | --- | --- | --- |
| name | string | Sí | Nombre del área legal |
| slug | string | Sí | Identificador único en URL |
| description | string | No | Descripción del área |
| logo | string / null | No | URL del logo |

### Response
Devuelve el área legal recién creada con todos sus campos 
más el `id`, `createdAt` y `updatedAt` generados por el sistema.

### Error conocido
Si el slug ya existe devuelve error con código -32603 
e httpStatus 500.


---

## POST legalArea.update

**¿Cuándo se llama?** Al guardar el formulario de edición 
(botón lápiz ✏️ → "Actualizar").
**¿Para qué sirve?** Actualiza los datos de un área legal existente.

### Payload (lo que envía)

| Campo | Tipo | Requerido | Descripción |
| --- | --- | --- | --- |
| id | string | Sí | ID del área legal a actualizar |
| name | string | Sí | Nombre del área |
| slug | string | Sí | Identificador en URL |
| description | string | No | Descripción |
| logo | string / null | No | URL del logo |

### Response 
Devuelve el área legal con los datos actualizados. El campo `updatedAt` se actualiza automáticamente.

---

## POST legalArea.delete

**¿Cuándo se llama?** Al confirmar el botón "Eliminar" en el modal 
de confirmación.
**¿Para qué sirve?** Elimina un área legal de la organización.

### Payload (lo que envía)

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID del área legal a eliminar |

### Response
Devuelve los datos del área legal que fue eliminada.

| Campo | Tipo   | Descripción               |
| ----- | ------ | ------------------------- |
| id    | string | ID del área eliminada     |
| name  | string | Nombre del área eliminada |
| slug  | string | Slug del área eliminada   |
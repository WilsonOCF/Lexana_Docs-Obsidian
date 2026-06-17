# Endpoints — Expedientes

---

## GET legalArea.list / procedure.list

**¿Cuándo se llama?** Al cargar el módulo de Expedientes.
**¿Para qué sirve?** Carga en una sola llamada las áreas legales 
(para el filtro) y la lista de expedientes de la organización.

### Bloque 1 — Áreas legales (para filtro)
Mismos campos que en [[Endpoints - Areas Legales#GET legalArea.list]]

### Bloque 2 — Lista de expedientes

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único del expediente |
| code | string | Código del expediente en la plataforma del estado |
| name | string | Nombre del caso |
| status | string | Estado del expediente |
| clientId | string | ID del cliente asociado |
| legalAreaId | string | ID del área legal |
| createdAt | datetime | Fecha de creación |
| organizationId | string | ID de la organización |

Devuelve lista vacía si no hay expedientes creados.

---

## GET client.list / procedure.list / legalArea.list

**¿Cuándo se llama?** Al abrir el formulario "+ Nuevo Expediente".
**¿Para qué sirve?** Carga los datos necesarios para los selectores 
del formulario: clientes, expedientes existentes y áreas legales.

---

## POST procedure.create

**¿Cuándo se llama?** Al hacer clic en "Guardar" en el formulario 
de nuevo expediente.
**¿Para qué sirve?** Crea un nuevo expediente en la organización.

### Payload (lo que envía)

| Campo | Tipo | Requerido | Descripción |
| --- | --- | --- | --- |
| code | string | Sí | Código interno del expediente |
| name | string | Sí | Nombre del caso |
| description | string / null | No | Descripción del expediente |
| objective | string / null | No | Objetivo del caso |
| status | string | Sí | Estado: TODO, IN_PROGRESS, DONE |
| startAt | datetime / null | No | Fecha de inicio |
| endAt | datetime / null | No | Fecha de cierre |
| clientId | string | Sí | ID del cliente asociado |
| legalAreaId | string | Sí | ID del área legal |

### Response

| Campo          | Tipo     | Descripción                               |
| -------------- | -------- | ----------------------------------------- |
| id             | string   | ID único del expediente                   |
| code           | string   | Código interno                            |
| ticketNumber   | number   | Número de ticket asignado automáticamente |
| name           | string   | Nombre del caso                           |
| status         | string   | Estado: TODO, IN_PROGRESS, DONE           |
| legalAreaId    | string   | ID del área legal                         |
| clientId       | string   | ID del cliente                            |
| organizationId | string   | ID de la organización                     |
| createdAt      | datetime | Fecha de creación                         |
| updatedAt      | datetime | Fecha de actualización                    |
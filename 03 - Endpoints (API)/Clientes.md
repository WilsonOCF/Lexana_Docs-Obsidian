# Endpoints — Clientes

---

## GET client.list

**¿Cuándo se llama?** Al cargar el módulo de Clientes.
**¿Para qué sirve?** Trae la lista de todos los clientes de la 
organización.

### Response

| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID único del cliente |
| type | string | Tipo: COMPANY o PERSON |
| fullName | string / null | Nombre completo (solo personas) |
| profession | string / null | Profesión (solo personas) |
| dni | string / null | DNI (solo personas) |
| companyName | string / null | Nombre empresa (solo empresas) |
| ruc | string / null | RUC (solo empresas) |
| sector | string | Sector de la empresa |
| mainContact | string | Nombre del contacto principal |
| mainContactRole | string | Rol del contacto principal |
| email | string | Correo del cliente |
| phone | string | Teléfono |
| address | string | Dirección |
| source | string | Origen del cliente |
| priority | string | Prioridad: MEDIUM, HIGH, LOW |
| status | string | Estado: ACTIVE, INACTIVE |
| tags | array | Etiquetas asignadas |
| createdAt | datetime | Fecha de creación |
| organizationId | string | ID de la organización |


---

## POST client.update

**¿Cuándo se llama?** Al guardar cambios en el formulario de edición 
de un cliente (botón lápiz ✏️).
**¿Para qué sirve?** Actualiza los datos de un cliente existente.

### Response
Devuelve el cliente completo con los datos ya actualizados.

| Campo       | Tipo          | Descripción                   |
| ----------- | ------------- | ----------------------------- |
| id          | string        | ID del cliente actualizado    |
| type        | string        | Tipo: COMPANY o PERSON        |
| fullName    | string / null | Nombre completo               |
| companyName | string / null | Nombre de empresa             |
| ruc         | string / null | RUC                           |
| dni         | string / null | DNI                           |
| email       | string        | Correo                        |
| phone       | string        | Teléfono                      |
| priority    | string        | Prioridad: MEDIUM, HIGH, LOW  |
| status      | string        | Estado: ACTIVE, INACTIVE      |
| updatedAt   | datetime      | Fecha de última actualización |


---

## GET client.list (con filtros)

**¿Cuándo se llama?** Al usar el buscador o aplicar filtros en 
la lista de clientes.
**¿Para qué sirve?** Trae la lista de clientes filtrada por 
nombre, RUC o DNI.

### Diferencia con client.list normal
Mismo response pero recibe parámetros de búsqueda en la URL. 
Los campos devueltos son idénticos.

---

---

## POST client.create

**¿Cuándo se llama?** Al guardar el formulario de "+ Nuevo Cliente".
**¿Para qué sirve?** Crea un nuevo cliente en la organización.

### Payload (lo que envía)

| Campo           | Tipo          | Requerido    | Descripción                   |
| --------------- | ------------- | ------------ | ----------------------------- |
| type            | string        | Sí           | Tipo: PERSON o COMPANY        |
| fullName        | string / null | Sí (persona) | Nombre completo               |
| profession      | string / null | No           | Profesión                     |
| dni             | string / null | Sí (persona) | DNI                           |
| companyName     | string / null | Sí (empresa) | Nombre de empresa             |
| ruc             | string / null | Sí (empresa) | RUC                           |
| sector          | string        | No           | Sector                        |
| mainContact     | string        | No           | Nombre del contacto principal |
| mainContactRole | string        | No           | Rol del contacto principal    |
| email           | string        | No           | Correo                        |
| phone           | string        | No           | Teléfono                      |
| address         | string        | No           | Dirección                     |
| source          | string        | No           | Origen del cliente            |
| priority        | string        | No           | Prioridad: MEDIUM, HIGH, LOW  |
| status          | string        | No           | Estado: ACTIVE, INACTIVE      |
| tags            | array         | No           | Etiquetas                     |

### Response
Devuelve el cliente recién creado con todos sus campos más el `id` 
y `createdAt` generados por el sistema.
### Diferencia entre PERSON y COMPANY

| Campo       | PERSON    | COMPANY   |
| ----------- | --------- | --------- |
| type        | "PERSON"  | "COMPANY" |
| fullName    | requerido | null      |
| dni         | requerido | null      |
| profession  | opcional  | null      |
| companyName | null      | requerido |
| ruc         | null      | requerido |
| sector      | opcional  | opcional  |
| mainContact | opcional  | opcional  |

---

## POST client.delete

**¿Cuándo se llama?** Al confirmar el botón "Eliminar" en el modal 
de confirmación.
**¿Para qué sirve?** Elimina un cliente y todos sus datos asociados. 
Esta acción no se puede deshacer.

### Payload (lo que envía)

| Campo | Tipo   | Descripción               |
| ----- | ------ | ------------------------- |
| id    | string | ID del cliente a eliminar |

### Response

| Campo | Tipo | Descripción |
| --- | --- | --- |
| success | boolean | true si se eliminó correctamente |

### Nota importante
Al eliminar un cliente también se eliminan todos los datos 
asociados a él (expedientes, tareas, etc).
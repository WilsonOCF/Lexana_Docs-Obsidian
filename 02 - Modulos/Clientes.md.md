# Clientes

## ¿Qué es?
Gestión de la cartera de clientes del estudio jurídico. Permite registrar personas naturales y empresas jurídicas.

## Cómo acceder
Menú lateral → Clientes

---

## Pantalla principal

Ruta: Tablero Principal > Clients

- Título: "Mis clientes"
- Subtítulo: "Gestiona tu cartera de personas y empresas jurídicas."

**Barra superior:**

- Buscador con placeholder "Buscar por nombre, RUC, DNI..."
- Botón "Columnas" para mostrar u ocultar columnas
- Botón "+ Nuevo Cliente" para crear un cliente nuevo

**Tabla de clientes:**

| Columna | Descripción |
| --- | --- |
| Cliente | Ícono de tipo + nombre + profesión o sector |
| Tipo / ID | Tipo (Persona o Empresa) + DNI o RUC |
| Contacto | Tipo de contacto + correo electrónico |
| Prioridad | Nivel de prioridad con punto de color (ej: Media en amarillo) |
| Estado | Badge de estado (ej: Activo en verde) |
| Origen | Origen del cliente (vacío si no se especificó) |
| Acciones | Botón editar (lápiz) y botón eliminar (basurero) |

**Íconos de tipo de cliente:**

- Persona: ícono de silueta humana
- Empresa: ícono de edificio

**Paginación:**

- Selector "Rows per page" con opciones de cantidad
- Contador de registros (ej: 1-5 de 5)
- Botones de navegación entre páginas

---

## Modal — Nuevo Cliente (Persona)

Se abre al hacer clic en "+ Nuevo Cliente" con la pestaña "Persona" seleccionada.

- Título: "Nuevo Cliente"
- Subtítulo: "Rellena la información del cliente."
- Selector de tipo con dos pestañas: "Persona" y "Empresa"
- Botón X para cerrar

**Campos del formulario:**

| Campo | Tipo | Placeholder |
| --- | --- | --- |
| Nombre Completo | Texto | "Juan Pérez" |
| DNI | Texto | "12345678" |
| Profesión | Texto | "Abogado" |
| Correo Electrónico | Email | "juan@ejemplo.com" |
| Teléfono | Texto | "+51 999 999 999" |

**Botón:** "Guardar Cliente"

---

## Modal — Nuevo Cliente (Empresa)

Se abre al hacer clic en "+ Nuevo Cliente" con la pestaña "Empresa" seleccionada.

- Título: "Nuevo Cliente"
- Subtítulo: "Rellena la información del cliente."
- Selector de tipo con dos pestañas: "Persona" y "Empresa"
- Botón X para cerrar

**Campos del formulario:**

| Campo | Tipo | Placeholder |
| --- | --- | --- |
| Razón Social | Texto | "Empresa SAC" |
| RUC | Texto | "20123456789" |
| Sector | Texto | "Tecnología" |
| Contacto Principal | Texto | "María García" |
| Cargo del Contacto | Texto | "Gerente General" |
| Correo Electrónico | Email | "contacto@empresa.com" |
| Teléfono | Texto | "+51 999 999 999" |

**Botón:** "Guardar Cliente"

---

## Modal — Editar Cliente

Se abre al hacer clic en el ícono de editar (lápiz ).

- Título: "Editar Cliente"
- Subtítulo: "Actualiza la información del cliente."
- Los campos vienen prerrellenados con los datos actuales
- Botón X para cerrar

**Campos del formulario (tipo Persona):**

| Campo | Tipo |
| --- | --- |
| Nombre Completo | Texto |
| DNI | Texto |
| Profesión | Texto |
| Correo Electrónico | Email |
| Teléfono | Texto |

**Botón:** "Guardar Cambios"

---

## Modal — Eliminar Cliente

Se abre al hacer clic en el ícono de eliminar (basurero 🗑️).

- Título: "Eliminar Cliente"
- Mensaje: "¿Estás seguro de que deseas eliminar a [nombre]? Esta acción no se puede deshacer."
- Alerta en rojo: "Al eliminar este cliente también se eliminarán todos los datos asociados. Por favor, confirma si deseas continuar."
- Botón "Cancelar": cierra el modal sin eliminar
- Botón "Eliminar": confirma la eliminación (rojo)
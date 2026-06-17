# Áreas Legales

## ¿Qué es?
Gestión de las áreas legales de la organización. Permite organizar los expedientes por especialidad jurídica como Penal, Civil, Laboral, etc.

## Cómo acceder
Menú lateral → Áreas Legales

---

## Pantalla principal

Ruta: Tablero Principal > Áreas Legales

**Barra superior:**

- Buscador con placeholder "Buscar por nombre o descripción..."
- Botón "Columnas" para mostrar u ocultar columnas de la tabla
- Botón "+ Nueva Área Legal" para crear un área nueva

**Tabla de áreas legales:**

| Columna | Descripción |
| --- | --- |
| Área Legal | Ícono de color + nombre del área + descripción |
| Slug | Identificador único del área en la URL |
| Fecha de Creación | Fecha en que se creó el área |
| Acciones | Botón editar (azul) y botón eliminar (rojo) |

**Paginación:**

- Selector "Rows per page" con opciones de cantidad
- Contador de registros (ej: 1-2 de 2)
- Botones de navegación entre páginas

---

## Modal — Nueva Área Legal

Se abre al hacer clic en "+ Nueva Área Legal".

- Título: "Nueva Área Legal"
- Subtítulo: "Rellena la información del área legal."
- Botón X para cerrar

**Campos del formulario:**

| Campo | Tipo | Obligatorio | Placeholder |
| --- | --- | --- | --- |
| Nombre del área legal | Texto | Sí | "Ej. Penal, Civil, Laboral..." |
| Alias (Slug) | Texto | Sí | "ej-penal" |
| Descripción | Texto | No | "Breve descripción del área legal" |

**Botón:** "Guardar"

---

## Modal — Actualizar Área Legal

Se abre al hacer clic en el ícono de editar (lápiz azul ✏️).

- Título: "Actualizar Área Legal"
- Subtítulo: "Modifica la información del área legal."
- Botón X para cerrar
- Los campos vienen prerrellenados con los datos actuales

**Campos del formulario:**

| Campo | Tipo | Obligatorio |
| --- | --- | --- |
| Nombre del área legal | Texto | Sí |
| Alias (Slug) | Texto | Sí |
| Descripción | Texto | No |

**Botón:** "Actualizar"

---

## Modal — Eliminar Área Legal

Se abre al hacer clic en el ícono de eliminar (basurero rojo 🗑️).

- Título: "Eliminar Área Legal"
- Mensaje: "¿Estás seguro de que deseas eliminar el área legal [nombre]? Esta acción no se puede deshacer."
- Botón "Cancelar": cierra el modal sin eliminar
- Botón "Eliminar": confirma la eliminación (rojo)
# Expedientes

## ¿Qué es?
Gestión de expedientes y casos legales del estudio jurídico. Cada expediente representa un caso legal de un cliente con su código para rastrearlo en la plataforma del estado.

## ¿Quién lo usa?
- Abogados: crean expedientes y asignan tareas a practicantes
- Practicantes: revisan sus expedientes asignados y completan tareas

## Cómo acceder
Menú lateral → Expedientes

---

## Pantalla principal

Ruta: Tablero Principal > Expedientes

- Título: "Expedientes"
- Subtítulo: "Gestiona tus expedientes y casos legales."

**Barra superior:**

- Buscador con placeholder "Buscar por nombre, código o descripción..."
- Selector "Todas las áreas" para filtrar por área legal
- Selector "Todos los estados" para filtrar por estado del expediente
- Botón "Columnas" para mostrar u ocultar columnas
- Botón "+ Nuevo Expediente" para crear un expediente nuevo

**Tabla de expedientes:**

| Columna | Descripción |
| --- | --- |
| Expediente | Nombre e ícono del caso |
| Cliente / Área | Cliente asociado y área legal |
| Estado | Estado actual del expediente |
| Fecha de Creación | Fecha en que se registró |
| Acciones | Acciones disponibles |

**Estado vacío:**

Muestra mensaje "Sin registros" cuando no hay expedientes que coincidan con los filtros aplicados.

**Paginación:**

- Selector "Rows per page" con opciones de cantidad
- Contador de registros (ej: 1-10 de 0)
- Botones de navegación entre páginas

---

## Modal — Nuevo Expediente

Se abre al hacer clic en "+ Nuevo Expediente".

- Título: "Nuevo Expediente"
- Subtítulo: "Ingresa la información del nuevo expediente."
- Botón X para cerrar

**Campos del formulario:**

| Campo | Tipo | Placeholder | Obligatorio |
| --- | --- | --- | --- |
| Nombre del expediente | Texto | "Caso principal..." | Sí |
| Código Interno | Texto | "EXP-2024-001" | Sí |
| Cliente | Selector desplegable | "Selecciona un cliente" | Sí |
| Área Legal | Selector desplegable | "Selecciona un área" | Sí |
| Estado | Selector desplegable | "Por Hacer" por defecto | Sí |

**Estados disponibles:**

- Por Hacer
- En Progreso
- Completado

**Botón:** "Guardar"

---

## Nota importante
El acceso a crear expedientes puede estar restringido según el plan contratado o el rol del usuario. Consultar con el administrador si no aparecen los expedientes creados.
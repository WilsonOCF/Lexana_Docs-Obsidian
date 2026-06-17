# Tablero Principal

## ¿Qué es?
Pantalla de inicio de Lexana. Muestra un resumen general del estado del despacho jurídico: expedientes, tareas, distribución por área y agenda del día.

## Cómo acceder
Menú lateral → Inicio

---

## Encabezado

Muestra la información de la organización activa:

- Logo y nombre de la organización (ej: Lexana-Prod)
- Subtítulo de la organización (ej: Procesos Jurídicos)
- Avatares de los miembros activos con contador (+1 si hay más)
- Botón "+" para agregar nuevos miembros
- Nombre y rol del usuario logueado (esquina superior derecha)

---

## Tarjetas de resumen

4 tarjetas en la parte superior que muestran métricas clave.

**Tarjeta 1 — Total de Expedientes**

Muestra el total de expedientes activos entre todas las áreas. Tiene botón "Activos" como indicador.

**Tarjeta 2 — Nuevos Expedientes**

Muestra expedientes creados en los últimos 7 días. Tiene botón "Últimos 7 días" como indicador del período.

**Tarjeta 3 — Tareas Retrasadas**

Muestra tareas que superaron su fecha límite. Muestra badge "Atención" en rojo cuando hay tareas retrasadas.

**Tarjeta 4 — Última Revisión de SINOE**

Muestra la fecha de la última sincronización con SINOE. Muestra badge "Pendiente" cuando está pendiente. Muestra "No disponible" con mensaje "Verificar conexión" cuando no hay integración activa.

---

## Tareas sin cerrar

Gráfico de barras horizontal que muestra la cantidad de tareas sin cerrar por cada miembro del equipo.

- Subtítulo: "Por miembro · click para ver detalle"
- Botón "Ver todas" redirige al módulo de Tareas
- Al pasar el cursor sobre una barra aparece tooltip: "X tareas · click para ver"

**Al hacer clic en una barra** se abre un panel lateral derecho con el detalle de tareas del miembro:

- Encabezado con iniciales, nombre completo del miembro y subtítulo "Tareas con fecha límite asignadas a este miembro"
- Botón X para cerrar el panel

| Columna | Descripción |
| --- | --- |
| Tarea | Nombre de la tarea |
| Expediente | Expediente al que pertenece |
| Estado | Badge de estado (ej: Retrasado en rojo) |
| Límite | Fecha límite y hace cuántos días venció |
| Acciones | Botón "Ir al expediente →" |

---

## Distribución por Área

Gráfico de dona que muestra el porcentaje de expedientes por área legal.

- Subtítulo con el total de expedientes activos
- Leyenda con nombre del área y cantidad de expedientes
- Ejemplo: Mi Area Legal (3), Penal (6)

---

## Eventos & SINOE

Muestra notificaciones y eventos del sistema judicial SINOE.

- Enlace "Ver todas" redirige al módulo SINOE
- Muestra "No hay notificaciones SINOE" cuando no hay eventos pendientes

---

## Agenda del Día

Calendario mensual con los eventos del día seleccionado.

- Título dinámico con la fecha actual (ej: Agenda del Día 16 Jun)
- Navegación entre meses con flechas
- Día actual resaltado en color oscuro
- Panel lateral derecho muestra eventos del día seleccionado
- Muestra "Sin eventos este día" cuando no hay reuniones
- Botón "+ Nueva Reunión" para crear un evento directamente desde aquí

---

## Menú lateral

| Opción | Descripción |
| --- | --- |
| Inicio | Tablero principal |
| Áreas Legales | Gestión de áreas del despacho |
| Expedientes | Gestión de casos legales |
| Sinoe | Notificaciones judiciales |
| Clientes | Cartera de clientes |
| Tareas | Tareas e hitos del equipo |
| Calendario | Eventos y fechas importantes |
| Agente Legal | Asistente de IA jurídica |
| Búsqueda Legal | Búsqueda de jurisprudencia |

**Opciones adicionales:**

- Ícono de campana: notificaciones
- Toggle claro/oscuro: cambio de tema
- Colapsar menú: oculta el menú lateral
- Cerrar sesión
# SINOE

## ¿Qué es?
Integración con el Sistema de Notificaciones del Poder Judicial del Perú (SINOE). Permite a los abogados consultar sus notificaciones judiciales directamente desde Lexana sin tener que entrar a la plataforma del estado.

## Cómo acceder
Menú lateral → Sinoe

---

## Pantalla principal

Ruta: Tablero Principal > Sinoe notifications

- Título: "Notificaciones SINOE"
- Subtítulo: "Consulta tus notificaciones judiciales del sistema SINOE."

**Barra superior:**

- Buscador con placeholder "Buscar por número, expediente, sumilla......"
- Botón "Columnas" para mostrar u ocultar columnas de la tabla

**Tabla de notificaciones:**

| Columna | Descripción |
| --- | --- |
| Notificación | Número o identificador de la notificación judicial |
| Órgano Jurisdiccional | Juzgado o tribunal que emite la notificación |
| Sumilla | Resumen del contenido de la notificación |
| Estado | Estado actual de la notificación |
| Fecha | Fecha de emisión de la notificación |
| Acciones | Acciones disponibles sobre la notificación |

**Estado vacío:**

Muestra mensaje "Sin registros" cuando no hay notificaciones o cuando no hay conexión activa con SINOE.

**Paginación:**

- Selector "Rows per page" con opciones de cantidad
- Contador de registros (ej: 1-10 de 0)
- Botones de navegación entre páginas

---

## Nota importante
Este módulo requiere que la organización tenga configurada la integración con SINOE. Cuando no hay conexión activa, el tablero principal muestra "No disponible - Verificar conexión" en la tarjeta de última revisión.
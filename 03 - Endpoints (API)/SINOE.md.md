# Endpoints — SINOE

---

## GET sinoeNotification.list

**¿Cuándo se llama?** Al cargar el módulo de SINOE.
**¿Para qué sirve?** Trae la lista de notificaciones judiciales 
sincronizadas desde el sistema SINOE del Poder Judicial del Perú.

### Response
Devuelve un array con las notificaciones. Si no hay conexión 
activa con SINOE o no hay notificaciones, devuelve lista vacía.

```json
[]
```

### Campos esperados cuando hay datos
| Campo | Tipo | Descripción |
| --- | --- | --- |
| id | string | ID de la notificación |
| numero | string | Número de expediente |
| organoJurisdiccional | string | Juzgado o tribunal |
| sumilla | string | Resumen del contenido |
| estado | string | Estado de la notificación |
| fecha | datetime | Fecha de la notificación |

### Nota
El módulo muestra "No disponible" en el tablero cuando no hay 
conexión activa con SINOE. Se requiere configurar la integración 
para recibir notificaciones.
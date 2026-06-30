# Lexana — Documentación Técnica

Repositorio de documentación oficial de **Lexana**, una plataforma SaaS de gestión jurídica para despachos legales peruanos.

---

## ¿Qué es Lexana?

Lexana permite a abogados y sus equipos gestionar expedientes, clientes, tareas y mantenerse al día con el sistema judicial del Estado (SINOE). Incluye un agente de IA jurídica y un módulo de búsqueda de jurisprudencia.

**Dirigido a:**
- Estudios jurídicos y despachos legales
- Abogados independientes con equipo a cargo
- Practicantes y asistentes legales

---

## Stack tecnológico

| Capa | Tecnología |
|---|---|
| Frontend | Next.js |
| Hosting | Vercel |
| IA | Claude Opus 4 (Anthropic) |
| Almacenamiento | AWS S3 |

---

## Roles de usuario

| Rol | Descripción |
|---|---|
| Owner | Dueño del despacho, acceso total |
| Admin | Administrador con permisos avanzados |
| Member | Miembro del equipo, acceso estándar |

---

## Módulos del sistema

- **Tablero Principal** — Resumen general del despacho: expedientes, tareas y agenda
- **Areas Legales** — Organizacion de casos por especialidad juridica
- **Expedientes** — Gestion completa de casos legales
- **Clientes** — Cartera de clientes del despacho
- **Tareas** — Asignacion y seguimiento de tareas del equipo
- **Calendario** — Eventos, audiencias y fechas limite
- **SINOE** — Integracion con el sistema judicial del Estado peruano
- **Agente Legal IA** — Asistente de inteligencia artificial para analisis juridico
- **Busqueda Legal** — Busqueda de jurisprudencia y documentos legales

---

## Estructura de la documentacion

```
00 - Inicio/          Punto de entrada y guia de navegacion
01 - Vision General/  Descripcion del sistema, audiencia y tecnologia
02 - Modulos/         Documentacion visual de cada modulo (pantallas, formularios, comportamientos)
03 - Endpoints (API)/ Documentacion tecnica de cada llamada al servidor
04 - Flujos/          Flujos de trabajo tipicos del sistema
```

---

## Flujos principales

**Flujo del abogado**
1. Revisa el Tablero → registra al cliente → crea el expediente → asigna tareas → consulta el Calendario → revisa SINOE

**Flujo del practicante**
1. Revisa tareas en el Tablero → abre el expediente → busca en SINOE → ejecuta la tarea → actualiza el estado

**Flujo de busqueda juridica**
1. Entra a Busqueda Legal → aplica filtros → revisa resultados → consulta al Agente Legal IA

---

**Proyecto:** Lexana — Sistema de Gestion Juridica
**Documentado por:** Wilson Carrasco
**Fecha de inicio:** Junio 2026

# Práctica guiada (resuelta) — Módulo 3: Spec-Driven Development con GitHub Spec Kit

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

Recorrer el flujo completo `constitution → specify → clarify → plan → tasks/analyze` para la primera funcionalidad del proyecto final: **crear y listar tareas**.

## Paso 1 — Constitución (`constitution`)

```markdown
# Constitución — TaskFlow

1. La seguridad y la validación de entradas no son negociables en ningún endpoint.
2. La arquitectura respeta la separación en capas definida en copilot-instructions.md.
3. Toda funcionalidad nueva requiere al menos pruebas de caso feliz y de error.
4. No se introducen dependencias externas sin justificación documentada en el PR.
```

## Paso 2 — Especificación (`specify`)

```markdown
# Especificación — Crear y listar tareas

## Historias de usuario
- Como miembro del equipo, quiero crear una tarea con título y descripción para registrar trabajo pendiente.
- Como miembro del equipo, quiero listar las tareas existentes para conocer el estado del trabajo.

## Criterios de aceptación
- Crear una tarea requiere título (obligatorio) y descripción (opcional).
- Una tarea creada inicia en estado "pendiente".
- Listar tareas devuelve todas las tareas existentes con su estado actual.
- Un título vacío debe rechazarse con un error claro.
```

## Paso 3 — Clarificación (`clarify`)

Preguntas resueltas antes de continuar:

- ¿Hay límite de longitud para el título/descripción? → Sí, título máx. 120 caracteres.
- ¿Se pueden crear tareas duplicadas (mismo título)? → Sí, no hay restricción de unicidad.
- ¿El listado debe soportar paginación? → No en esta primera iteración.

## Paso 4 — Plan técnico (`plan`)

```markdown
# Plan — Crear y listar tareas

- Endpoint POST /tasks y GET /tasks.
- Capa de servicio `TaskService` con validación de título.
- Persistencia simple (archivo JSON o SQLite según stack del grupo).
- Respuesta de error con código 400 y mensaje claro si el título es inválido.
```

## Paso 5 — Tareas y análisis de consistencia (`tasks` / `analyze`)

| Tarea | Cubre criterio de aceptación |
| :---- | :---- |
| Implementar `TaskService.create()` con validación de título | Título obligatorio, máx. 120 caracteres |
| Implementar endpoint POST /tasks | Creación de tarea, estado inicial "pendiente" |
| Implementar endpoint GET /tasks | Listado de tareas |
| Pruebas unitarias de `TaskService` (caso feliz + título vacío) | Validación de entradas |

`analyze` (revisión manual en clase): todos los criterios de aceptación tienen al menos una tarea asociada; no hay tareas que implementen algo fuera de lo especificado (ej. no se agrega paginación, consistente con la clarificación).

## Cierre de la práctica

Antes de pasar a `implement` (que se realizará en el Módulo 4 junto con agentic development), el instructor valida en grupo que specs, plan y tareas sean consistentes entre sí.

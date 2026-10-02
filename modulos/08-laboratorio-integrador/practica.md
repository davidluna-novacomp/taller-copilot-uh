# Práctica guiada (resuelta) — Módulo 8: Laboratorio integrador end-to-end

> Guion de la práctica integradora, con una solución de referencia completa sobre una funcionalidad de ejemplo **distinta** a la que cada estudiante implementará en su propio proyecto final, para no "regalar" la respuesta del laboratorio evaluado.

## Funcionalidad de ejemplo usada en esta guía: "Cerrar una tarea con motivo"

### Paso 1 — Requirement

Necesidad: el equipo quiere poder cerrar una tarea registrando el motivo de cierre, para tener trazabilidad de por qué se dejó de trabajar en ella.

### Paso 2 — Spec Kit (resumen)

```markdown
# Especificación — Cerrar tarea con motivo

## Criterios de aceptación
- Solo se puede cerrar una tarea que no esté ya cerrada.
- Cerrar una tarea requiere un motivo (texto no vacío, máx. 250 caracteres).
- Una tarea cerrada cambia su estado a "cerrada" y almacena el motivo y la fecha de cierre.
- Intentar cerrar una tarea ya cerrada devuelve un error claro (no la vuelve a cerrar).
```

Clarificaciones resueltas: no se permite reabrir una tarea cerrada en esta iteración; el motivo no admite formato enriquecido, solo texto plano.

Plan técnico (resumen): endpoint `POST /tasks/:id/close`, método `TaskService.close(id, reason)`, validación de estado actual antes de cerrar.

Tareas: implementar `close()`, endpoint, validaciones, tests.

### Paso 3 — Context & Instructions

Se confirma que `copilot-instructions.md` y el checklist de seguridad/Definition of Done (Módulos 2 y 6) siguen vigentes sin cambios para esta funcionalidad.

### Paso 4 — Agent (Plan → Execute → Verify)

Alcance de delegación: archivos `src/tasks/**`, `tests/tasks/**`; no instalar dependencias; verificar con tests + revisión manual del estado de la tarea antes/después de cerrar.

### Paso 5 — Testing

Casos: cierre exitoso, motivo vacío, tarea ya cerrada, motivo que excede 250 caracteres.

### Paso 6 — Security

Checklist del Módulo 6 aplicado: validación de entrada del motivo (longitud, no vacío), sin exposición de información sensible en el mensaje de error.

### Paso 7 — Observability

Log estructurado de evento `task.close.success` / `task.close.rejected` con correlation ID; contador `tasks_closed_total`.

### Paso 8 — Pull Request

Se crea un PR describiendo la funcionalidad, enlazando la especificación y las tareas correspondientes.

### Paso 9 — Code Review

Revisión asistida por Copilot con el prompt file `revisar-pr` (Módulo 2) + revisión humana final antes de aprobar.

### Paso 10 — Metrics & Retrospective

```markdown
# Retrospectiva — Cerrar tarea con motivo

- Qué delegó la IA: implementación inicial del método close() y de los tests de caso feliz.
- Qué verificó el equipo: casos de error (tarea ya cerrada, motivo vacío/largo), checklist de seguridad, logging.
- Evidencia disponible: especificación, plan, tareas, PR, resultados de tests, checklist de seguridad completado.
```

## Cómo usar esta guía en tu propio laboratorio

Repite exactamente esta misma secuencia de 10 pasos, pero sobre la funcionalidad nueva que elegiste en `ejercicios.md`, y documenta tu entrega en `proyecto_avance.md`.

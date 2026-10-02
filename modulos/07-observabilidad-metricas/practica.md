# Práctica guiada (resuelta) — Módulo 7: Observabilidad y métricas

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

1. Definir un conjunto mínimo de KPIs para evaluar el programa de Copilot del equipo.
2. Agregar requisitos de observabilidad a la especificación de "crear y listar tareas" y a su implementación.

## Parte A — KPIs del programa de Copilot (solución de referencia)

```markdown
# KPIs del programa de Copilot — [Equipo/Proyecto]

## Adopción
- % de desarrolladores con licencia que usaron Copilot en los últimos 30 días.

## Productividad
- Lead time promedio de PRs (desde creación hasta merge), comparado mes a mes.
- Throughput: número de PRs mergeados por sprint.

## Calidad
- % de PRs que requieren cambios solicitados en revisión (rework rate).
- Defectos reportados en producción por período, relacionados con cambios recientes.

## Riesgo
- Número de hallazgos de seguridad detectados en revisión antes de merge (no después).
- Dependencias nuevas introducidas sin verificación documentada.
```

Discusión guiada: ningún KPI se mira de forma aislada; por ejemplo, un aumento de throughput sin cambios en rework rate o defectos es una señal más confiable de mejora real que el throughput solo.

## Parte B — Observabilidad en "crear y listar tareas"

### Paso 1 — Requisitos de observabilidad agregados a la especificación

```markdown
## Requisitos de observabilidad (agregado al Módulo 3)
- Cada creación de tarea exitosa o fallida debe generar un log estructurado con: acción, resultado, duración, correlation ID.
- Debe existir un contador de tareas creadas y un contador de errores de validación.
- El endpoint GET /tasks debe registrar su tiempo de respuesta.
```

### Paso 2 — Implementación mínima (ejemplo conceptual, adaptar al stack real)

```text
POST /tasks
  -> log: { event: "task.create.attempt", correlationId, title_length }
  -> si falla validación: log: { event: "task.create.validation_error", correlationId, reason }
  -> si éxito: log: { event: "task.create.success", correlationId, taskId, durationMs }
  -> métricas: counter(tasks_created_total), counter(tasks_validation_errors_total)
```

### Paso 3 — Definir un SLI/SLO simple para este endpoint

- **SLI:** % de solicitudes a `POST /tasks` que responden exitosamente (sin error 5xx).
- **SLO:** 99% de éxito medido en ventanas de 7 días.

## Cierre de la práctica

El instructor conecta este trabajo con el checklist de seguridad del Módulo 6 (los logs no deben exponer datos sensibles) y anticipa que en el Módulo 8 esta observabilidad formará parte de la Definition of Done del laboratorio integrador.

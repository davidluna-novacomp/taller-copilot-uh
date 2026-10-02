# Práctica guiada (resuelta) — Módulo 4: Agentic Development y Model Context Protocol (MCP)

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

Implementar, delegando al agente, las tareas definidas en el Módulo 3 ("crear y listar tareas") aplicando el patrón **Plan → Execute → Verify**, y (si el entorno lo permite) usar una herramienta MCP.

## Paso 1 — Definir el alcance de la delegación (antes de ejecutar)

```markdown
# Alcance de delegación — Implementar "crear y listar tareas"

- Archivos permitidos: src/tasks/**, tests/tasks/**
- Herramientas permitidas: edición de archivos, terminal para correr tests.
- No permitido sin confirmación: instalar dependencias nuevas, hacer commit/push.
- Verificación: correr la suite de tests y revisar que cumple los criterios de aceptación del Módulo 3.
```

## Paso 2 — Plan (solicitado al agente antes de ejecutar)

Prompt de referencia:

> "Antes de escribir código, dame un plan paso a paso para implementar las tareas de `tasks.md` del Módulo 3, respetando `copilot-instructions.md`. No modifiques archivos todavía."

Plan esperado (resumen):
1. Crear `TaskService` con método `create(title, description)` y validación de título.
2. Crear almacenamiento simple en memoria/archivo para las tareas.
3. Crear endpoint `POST /tasks`.
4. Crear endpoint `GET /tasks`.
5. Crear pruebas unitarias de `TaskService` (caso feliz + título vacío).

## Paso 3 — Execute

Se aprueba el plan y se permite al agente implementar los pasos, revisando el diff incrementalmente en lugar de aceptar todo de una vez.

## Paso 4 — Verify

- Ejecutar la suite de tests.
- Confirmar manualmente contra los criterios de aceptación del Módulo 3 (título obligatorio, máx. 120 caracteres, estado inicial "pendiente", listado sin paginación).
- Confirmar que el agente no tocó archivos fuera del alcance definido en el Paso 1.

## Paso 5 (si el entorno lo permite) — Uso de una herramienta MCP

Ejemplo con GitHub MCP Server: pedir al agente que consulte si existe un issue relacionado con "crear y listar tareas" antes de implementar, o que prepare (sin ejecutar) la creación de un Pull Request al finalizar. El instructor enfatiza que cualquier operación de escritura (crear PR, comentar, hacer merge) requiere confirmación humana explícita.

## Cierre de la práctica

Discusión en grupo: ¿el plan propuesto por el agente coincidía con las tareas definidas en el Módulo 3? ¿hubo que corregir el alcance durante la ejecución? ¿qué se verificó antes de aceptar el resultado como definitivo?

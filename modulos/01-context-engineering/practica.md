# Práctica guiada (resuelta) — Módulo 1: Copilot avanzado y Context Engineering

> Esta práctica está pensada para desarrollarse **en clase junto con el instructor**. Incluye la solución de referencia para que el instructor pueda guiar la discusión y anticipar variaciones razonables.

## Objetivo de la práctica

Diseñar el **"AI Development Context"** inicial del proyecto final (`proyecto-final/`), es decir, el conjunto mínimo de información que debería estar disponible para que Copilot produzca sugerencias consistentes con la arquitectura y convenciones del proyecto.

## Paso 1 — Definir el alcance funcional de referencia

Usamos como base el proyecto final "TaskFlow" (ver [proyecto-final/README.md](../../proyecto-final/README.md)): gestión simple de tareas (crear, listar, actualizar, cerrar, comentar).

## Paso 2 — Completar la plantilla de contexto (solución de referencia)

```markdown
# AI Development Context — TaskFlow

## Arquitectura
- API REST con separación en capas: rutas/controladores, servicios (lógica de negocio), acceso a datos.
- Una sola responsabilidad por módulo; no mezclar lógica de negocio en controladores.

## Convenciones
- Nomenclatura en inglés para código, en español para documentación del curso.
- Manejo de errores centralizado (middleware/handler único), nunca `try/catch` silenciosos.
- Respuestas de la API siguen un formato consistente de éxito/error.

## Restricciones
- Sin dependencias externas no aprobadas por el instructor/equipo.
- Persistencia simple (archivo JSON o SQLite); no se requiere una base de datos productiva.

## Definition of Done
- Código con al menos una prueba unitaria por caso de uso principal.
- Sin secretos ni credenciales hardcodeadas.
- Endpoint documentado (entrada, salida, errores posibles).

## Estándares de testing
- Framework de pruebas del stack elegido por el grupo.
- Casos felices + al menos un caso de error por endpoint.
```

## Paso 3 — Guardar el contexto de forma persistente

Discusión guiada: en este módulo **solo diseñamos el contenido**; en el Módulo 2 se decide el mecanismo formal de persistencia (`.github/copilot-instructions.md`, instrucciones por ruta, etc.). Por ahora, se guarda como `proyecto-final/ai-context.md` (o el nombre que el grupo prefiera) dentro del propio proyecto final.

## Paso 4 — Probar el efecto del contexto

1. Con el archivo de contexto **cerrado/no referenciado**, pide a Copilot Chat: *"Implementa el endpoint para crear una tarea"*.
2. Abre el archivo de contexto en el editor (o pégalo al inicio del chat) y repite la misma petición.
3. Compara ambas respuestas en grupo: ¿cambió el manejo de errores? ¿el formato de respuesta? ¿la estructura en capas?

## Paso 5 — Identificar un candidato a Skill

Discusión guiada: del contexto diseñado en el Paso 2, ¿hay algo que no aplique a todo el proyecto o que sea demasiado extenso para vivir en una instrucción global? Por ejemplo, un procedimiento detallado para generar la documentación de un endpoint, o el conocimiento específico de cómo integrar con un servicio externo puntual. Eso es candidato a convertirse en un Skill (se formaliza en el Módulo 2), no a agregarse al contexto siempre activo.

## Cierre de la práctica

El instructor recoge 2-3 ejemplos de la clase donde el contexto cambió claramente el resultado, y refuerza la heurística de "mínimo, relevante y mantenible" antes de pasar a `ejercicios.md`.

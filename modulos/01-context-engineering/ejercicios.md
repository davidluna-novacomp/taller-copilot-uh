# Ejercicios — Módulo 1: Copilot avanzado y Context Engineering

> Resuelve estos ejercicios de forma individual, después de revisar `teoria.md` y `practica.md`. No requieren que el instructor esté presente.

## Ejercicio 1 — Comparar respuestas con y sin contexto

1. Elige una función o endpoint sencillo de un proyecto que conozcas.
2. Pide a Copilot Chat que la implemente **sin ningún contexto adicional** (repositorio vacío o chat nuevo sin archivos relevantes abiertos).
3. Abre en el editor 2-3 archivos representativos del proyecto real (que muestren convenciones, manejo de errores, estilo) y repite la misma petición.
4. Compara ambas respuestas y documenta al menos 3 diferencias concretas (nombres, manejo de errores, estructura, dependencias usadas).

**Entregable:** un párrafo comparando ambas respuestas y explicando qué señales de contexto influyeron.

## Ejercicio 2 — Auditoría de contexto disperso

1. Revisa un proyecto existente (tuyo o de tu equipo) y lista todo el "contexto" que hoy vive solo en la cabeza de las personas o en documentos no versionados (wikis, mensajes de chat, README desactualizados).
2. Clasifica cada elemento encontrado como **global**, **de dominio** o **de tarea**, según la tabla de `teoria.md`.

**Entregable:** una tabla con columnas `Elemento | Dónde vive hoy | Nivel (global/dominio/tarea) | ¿Debería persistir?`.

## Ejercicio 3 — Detectar sobrecarga de instrucciones

Te entregan (o redactas) una lista de 10 instrucciones para Copilot. Identifica:

- Cuáles son vagas o no verificables (ej. "escribe código limpio").
- Cuáles son redundantes o se contradicen entre sí.
- Cuáles sobrevivirían a la heurística "si no cambia el comportamiento observable, no debería estar".

**Entregable:** la lista original con anotaciones de qué eliminarías, reescribirías o mantendrías, y por qué.

## Ejercicio 4 — Clasificar información real de tu proyecto

Tomando el proyecto final del curso (ver `proyecto_avance.md`), enumera al menos:

- 3 elementos de contexto **global**.
- 2 elementos de contexto **de dominio**.
- 1 elemento de contexto **de tarea** (específico de la primera funcionalidad que vas a construir).

**Entregable:** lista organizada por nivel, lista para ser reutilizada como insumo del `proyecto_avance.md`.

## Ejercicio 5 — Instrucción global vs. Skill

De la lista de contexto que armaste en el Ejercicio 4 (o de cualquier proyecto real), identifica al menos 2 elementos que deberían vivir en una instrucción always-on (`copilot-instructions.md`) y al menos 1 elemento que sería mejor empaquetar como un Skill activado bajo demanda. Justifica cada decisión usando los criterios de `teoria.md` (punto 6): alcance, tamaño y si es una regla permanente o un procedimiento.

**Entregable:** tabla `Elemento | Instrucción global o Skill | Justificación`.

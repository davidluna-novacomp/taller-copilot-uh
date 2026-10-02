# Ejercicios — Módulo 5: Testing y Code Review asistidos por IA

## Ejercicio 1 — Traducir criterios de aceptación a casos de prueba

Toma 3 criterios de aceptación de cualquier funcionalidad (puede ser de tu proyecto final) y escribe, para cada uno, al menos un caso de prueba concreto (entrada, acción, resultado esperado).

**Entregable:** tabla `Criterio de aceptación | Caso de prueba | Resultado esperado`.

## Ejercicio 2 — Detectar cobertura sesgada hacia el camino feliz

Pide a Copilot que genere tests para una función con validaciones (puede ser `TaskService.create`). Revisa el resultado y responde: ¿cuántos tests son de camino feliz vs. de error/edge case? Pide explícitamente más casos negativos y compara.

**Entregable:** lista de tests generados en ambas rondas, clasificados como feliz/negativo/edge case.

## Ejercicio 3 — Evaluar un mock generado por IA

Pide a Copilot que genere un mock para una dependencia externa (ej. repositorio de datos). Evalúa: ¿el mock es fiel al comportamiento real? ¿oculta algún caso de error real (ej. fallo de conexión)?

**Entregable:** breve análisis (5-8 líneas) + ajuste del mock si era necesario.

## Ejercicio 4 — Aplicar el checklist de revisión

Aplica manualmente el checklist de 7 dimensiones de `teoria.md` sobre un PR o cambio de código real (tuyo o de un compañero).

**Entregable:** checklist completado con hallazgos por dimensión (aunque sea "sin hallazgos" en algunas).

## Ejercicio 5 — Comparar revisión de Copilot vs. revisión humana

Sobre el mismo cambio de código, pide a Copilot una revisión con el checklist y luego haz tu propia revisión manual sin ver primero la de Copilot. Compara ambas: ¿qué encontró cada una que la otra no?

**Entregable:** tabla comparativa `Hallazgo | Detectado por Copilot | Detectado por revisión humana`.

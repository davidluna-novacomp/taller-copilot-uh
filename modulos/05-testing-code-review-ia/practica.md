# Práctica guiada (resuelta) — Módulo 5: Testing y Code Review asistidos por IA

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

1. Ampliar la cobertura de pruebas de "crear y listar tareas" (implementada en el Módulo 4).
2. Analizar un Pull Request con fallas deliberadas usando el checklist de revisión, comparando hallazgos de Copilot, herramientas automáticas y revisión humana.

## Parte A — Ampliar cobertura de pruebas

### Paso 1 — Inventario de casos ya cubiertos

De la implementación del Módulo 4: caso feliz de creación, título vacío.

### Paso 2 — Pedir explícitamente casos negativos y edge cases

Prompt de referencia:

> "Genera casos de prueba adicionales para `TaskService.create` cubriendo: título con más de 120 caracteres, descripción ausente, título con solo espacios en blanco, y creación de dos tareas con el mismo título."

### Paso 3 — Resultado esperado (resumen)

| Caso | Resultado esperado |
| :---- | :---- |
| Título > 120 caracteres | Error de validación |
| Descripción ausente | Tarea creada (descripción opcional) |
| Título solo espacios | Error de validación (equivalente a vacío) |
| Título duplicado | Tarea creada (sin restricción de unicidad, según clarificación del Módulo 3) |

## Parte B — PR con fallas deliberadas (solución de referencia)

El instructor entrega un PR de ejemplo con al menos estas fallas intencionales:

1. Endpoint que no valida el título antes de guardar.
2. Manejo de errores con `try/catch` que solo hace `console.log` y continúa (viola `copilot-instructions.md`).
3. Un `TODO` con una credencial de ejemplo dejada en el código (riesgo de seguridad, se retoma en el Módulo 6).
4. Falta de test para el caso de título duplicado, a pesar de estar en la especificación.

### Paso 1 — Revisión asistida por Copilot

Se invoca el prompt file `revisar-pr` creado en el Módulo 2 sobre este PR.

### Paso 2 — Revisión con herramientas automáticas (si disponibles)

Linter/analizador estático del stack del grupo, para detectar por ejemplo el `console.log` o código no utilizado.

### Paso 3 — Revisión humana manual

Cada estudiante aplica el checklist de 7 dimensiones sin ver primero los hallazgos de Copilot.

### Paso 4 — Comparación en grupo

Se construye en el pizarrón/documento compartido una tabla: `Hallazgo | Copilot | Herramienta automática | Revisión humana`, discutiendo qué detectó cada mecanismo y qué se le escapó (por ejemplo, la credencial de ejemplo puede ser detectada por un scanner de secretos pero pasada por alto en una revisión rápida).

## Cierre de la práctica

El instructor refuerza: ninguno de los tres mecanismos por separado es suficiente; la combinación reduce el riesgo, pero la **aprobación final sigue siendo humana**.

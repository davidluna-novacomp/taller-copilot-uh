# Ejercicios — Módulo 2: Instrucciones, prompts reutilizables y agentes

## Ejercicio 1 — Migrar contexto a instrucciones formales

Toma el archivo de contexto que creaste en el Módulo 1 (`ai-context.md`) y conviértelo en un `.github/copilot-instructions.md` real dentro de tu proyecto. Ajusta el lenguaje para que sea directamente accionable (evita prosa larga, prioriza listas concretas).

**Entregable:** el archivo `.github/copilot-instructions.md` creado y commiteado.

## Ejercicio 2 — Instrucciones por ruta

Identifica una carpeta de tu proyecto (por ejemplo, la capa de acceso a datos o la carpeta de tests) que necesite reglas distintas al resto del repositorio. Crea un archivo en `.github/instructions/` con el `applyTo` correspondiente.

**Entregable:** archivo de instrucciones por ruta + una prueba (captura o texto) mostrando que Copilot respeta esa regla al trabajar en esa carpeta.

## Ejercicio 3 — Detectar conflictos de instrucciones

Te entregan (o redactas) dos conjuntos de instrucciones: una global y una por ruta, que se contradicen en al menos un punto (por ejemplo, estilo de manejo de errores). Explica:

- Cuál debería prevalecer y por qué.
- Cómo reescribirías ambas para eliminar la ambigüedad.

**Entregable:** breve análisis escrito (5-10 líneas) + la versión corregida de ambos archivos.

## Ejercicio 4 — Crear un prompt file reutilizable

Diseña un prompt file (`.github/prompts/generar-tests.prompt.md` o similar) que, al invocarse sobre un archivo de código, genere pruebas unitarias siguiendo las convenciones de tu proyecto.

**Entregable:** el prompt file + evidencia de haberlo ejecutado sobre al menos un archivo real, con el resultado obtenido.

## Ejercicio 5 — Checklist de calidad de instrucciones

Aplica los 4 criterios de `teoria.md` (concisión, alcance, verificabilidad, prevención de conflictos) a tu propio `copilot-instructions.md` y anota qué reglas mejorarías.

**Entregable:** tabla `Regla | Cumple concisión | Cumple alcance | Cumple verificabilidad | Acción a tomar`.

## Ejercicio 6 — Crear un Skill

Tomando el candidato a Skill que identificaste en el Módulo 1 (`proyecto_avance.md`), redacta un archivo `SKILL.md` con nombre, una descripción clara de cuándo debería activarse (y cuándo no) y el contenido detallado del procedimiento/conocimiento. Verifica que la descripción por sí sola permitiría decidir si aplica a una tarea dada, sin necesidad de leer el resto del archivo.

**Entregable:** el archivo `SKILL.md` + una prueba de una tarea donde debería activarse y otra donde no debería hacerlo.

## Ejercicio 7 — Crear un chat mode acotado

Diseña un `.github/chatmodes/*.chatmode.md` para una tarea sensible de tu proyecto (por ejemplo, revisar código sin poder editarlo, o solo consultar el estado de tareas sin poder crear/cerrar ninguna). Define explícitamente la lista de `tools` permitidas.

**Entregable:** el archivo del chat mode + una prueba mostrando que, en ese modo, Copilot respeta la restricción (por ejemplo, se niega a editar un archivo).

## Ejercicio 8 — `AGENTS.md` raíz vs. anidado

Redacta un `AGENTS.md` mínimo para la raíz de tu proyecto (cómo construir/testear/ejecutar, qué puede hacer el agente sin preguntar) y, si tu proyecto tiene al menos dos carpetas con necesidades distintas (ej. `backend/` y `frontend/`), redacta un segundo `AGENTS.md` anidado con las particularidades de esa subcarpeta.

**Entregable:** los archivos `AGENTS.md` creados + una nota explicando qué información pusiste en la raíz y cuál solo en el anidado, y por qué.

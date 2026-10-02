# Ejercicios — Módulo 4: Agentic Development y Model Context Protocol (MCP)

## Ejercicio 1 — Definir el alcance de una delegación

Elige una tarea multi-archivo de un proyecto (real o de laboratorio) y define por escrito, antes de delegarla al agente:

- Qué archivos/carpetas puede tocar.
- Qué herramientas puede usar (edición, terminal, MCP si aplica).
- Qué NO debe hacer sin confirmación (ej. instalar dependencias, hacer push).
- Cómo vas a verificar el resultado (tests, revisión manual, criterio de aceptación).

**Entregable:** documento breve "alcance de delegación" con las 4 secciones anteriores.

## Ejercicio 2 — Aplicar Plan → Execute → Verify

Delega al agente una tarea siguiendo el patrón explícito: primero pide el plan, revísalo, aprueba o ajusta, luego permite la ejecución, y finalmente documenta cómo verificaste el resultado.

**Entregable:** transcripción o resumen de las 3 fases (plan, ejecución, verificación) con el resultado final.

## Ejercicio 3 — Identificar operaciones de alto riesgo

Lista 5 operaciones que un agente con acceso a MCP/terminal podría intentar realizar en tu proyecto que deberían requerir confirmación humana explícita (ej. borrar archivos, hacer push, modificar datos en una base compartida).

**Entregable:** tabla `Operación | Por qué requiere confirmación humana | Cómo se controla hoy (o cómo se debería controlar)`.

## Ejercicio 4 — Caso "cuándo NO usar un agente"

Describe un escenario real o hipotético donde delegar la tarea completa a un agente sería una mala decisión, y explica qué harías en su lugar (reducir alcance, resolver ambigüedad primero, ejecutar manualmente).

**Entregable:** párrafo de análisis (8-12 líneas).

## Ejercicio 5 — Mínimo privilegio en una herramienta MCP

Si tienes acceso a un servidor MCP (por ejemplo, GitHub MCP Server), documenta qué operaciones habilitarías y cuáles restringirías para un flujo de trabajo específico de tu proyecto (ej. solo lectura de issues, sin permisos de merge).

**Entregable:** lista de operaciones permitidas/restringidas con justificación.

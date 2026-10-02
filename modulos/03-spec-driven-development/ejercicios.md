# Ejercicios — Módulo 3: Spec-Driven Development con GitHub Spec Kit

## Ejercicio 1 — Redactar una constitución mínima

Redacta la constitución de un proyecto personal o de laboratorio (no el proyecto final) en máximo 10 líneas: principios innegociables de arquitectura, calidad y seguridad.

**Entregable:** archivo `constitution.md` con la constitución redactada.

## Ejercicio 2 — Detectar especificaciones contaminadas con implementación

Te entregan (o redactas) una especificación que mezcla criterios de aceptación con decisiones de implementación (ej. "debe usar Redis para cachear la respuesta"). Reescríbela separando claramente qué es **especificación** (qué debe pasar) de qué es **plan** (cómo se implementa).

**Entregable:** dos documentos separados: especificación limpia + notas de plan.

## Ejercicio 3 — Ejercicio de clarificación

A partir de una especificación breve (3-5 criterios de aceptación), lista al menos 5 preguntas de clarificación que un buen analista/agente debería hacer antes de pasar a la fase de plan (casos borde, reglas de negocio implícitas, datos faltantes).

**Entregable:** lista de preguntas + respuestas hipotéticas razonables.

## Ejercicio 4 — Análisis de consistencia manual

Con una especificación, un plan y una lista de tareas de ejemplo (puedes usar los del `practica.md`), verifica manualmente:

- ¿Todo lo especificado tiene al menos una tarea asociada?
- ¿Existe alguna tarea que implemente algo no especificado?

**Entregable:** tabla `Criterio de aceptación | Tarea(s) que lo cubren | ¿Cubierto?`.

## Ejercicio 5 — Greenfield vs. brownfield

Toma una funcionalidad de tu proyecto final y redacta dos versiones breves de su constitución/plan: una asumiendo que el proyecto es greenfield y otra asumiendo que debe integrarse con un sistema legado con restricciones (ej. una API externa ya definida). Explica qué cambia.

**Entregable:** comparación de ambas versiones (5-8 líneas cada una).

# Ejercicios — Módulo 7: Observabilidad y métricas

## Ejercicio 1 — Clasificar métricas por categoría

Te entregan (o generas) una lista de 8 métricas relacionadas con Copilot y el ciclo de entrega (ej. % de sugerencias aceptadas, lead time, defectos post-entrega, número de PRs revisados por Copilot, cobertura de tests, time-to-merge, dependencias con vulnerabilidades, líneas de código generadas).

Clasifica cada una en: **Adopción, Productividad, Calidad o Riesgo** (tabla de `teoria.md`).

**Entregable:** tabla `Métrica | Categoría | Justificación breve`.

## Ejercicio 2 — Detectar métricas de "vanidad"

De la lista del ejercicio anterior, identifica cuáles serían fáciles de manipular o de mejorar sin que exista una mejora real (ej. "líneas de código generadas" puede subir sin que mejore la calidad), y propone una métrica complementaria que corrija ese riesgo.

**Entregable:** lista de métricas de riesgo + métrica complementaria sugerida para cada una.

## Ejercicio 3 — Diseñar un cuadro de mando mínimo

Define 1-2 métricas por cada una de las 4 categorías (adopción, productividad, calidad, riesgo) específicas para tu equipo/proyecto real, incluyendo cómo se calcularía cada una hoy con las herramientas disponibles.

**Entregable:** cuadro de mando propuesto (tabla de 4 categorías x 1-2 métricas c/u).

## Ejercicio 4 — Agregar logging estructurado a una función existente

Toma una función o endpoint de tu proyecto (puede ser de un módulo anterior) y agrégale logging estructurado mínimo: un evento de inicio, uno de éxito y uno de error, con un correlation ID si aplica.

**Entregable:** código antes/después + explicación de qué información aporta cada log agregado.

## Ejercicio 5 — Definir un SLI/SLO simple

Elige un endpoint crítico de tu proyecto y define un SLI (ej. porcentaje de respuestas exitosas) y un SLO asociado (ej. 99% de respuestas exitosas en una ventana de 30 días).

**Entregable:** definición del SLI y SLO + cómo se mediría en la práctica.

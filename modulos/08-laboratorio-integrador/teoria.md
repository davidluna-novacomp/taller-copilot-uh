# Teoría — Módulo 8: Laboratorio integrador end-to-end

## 1. Por qué un flujo integrador y no módulos aislados

Cada módulo anterior enseñó una capacidad específica (contexto, instrucciones, especificación, agentes/MCP, testing, seguridad, observabilidad). El riesgo de detenerse ahí es que el equipo aprenda "features" de Copilot sin integrarlas en un flujo de ingeniería real. Este módulo existe para demostrar que las 7 capacidades anteriores **funcionan como un sistema**, no como herramientas sueltas.

## 2. El flujo integrador de 10 pasos

| Paso | Módulo de origen | Qué implica |
| :---- | :---- | :---- |
| 1. Requirement | — | Definir el requerimiento y criterios de aceptación iniciales. |
| 2. Spec Kit | Módulo 3 | Constitution → specify → clarify → plan → tasks/analyze. |
| 3. Context & Instructions | Módulos 1-2 | Confirmar/actualizar contexto e instrucciones del repositorio para esta funcionalidad. |
| 4. Agent | Módulo 4 | Delegar la implementación con Plan → Execute → Verify, con o sin MCP. |
| 5. Testing | Módulo 5 | Generar y revisar pruebas, incluyendo edge cases. |
| 6. Security | Módulo 6 | Aplicar el checklist de seguridad/gobernanza. |
| 7. Observability | Módulo 7 | Agregar logging, métricas, SLI/SLO si corresponde. |
| 8. Pull Request | — | Crear/actualizar el PR con la funcionalidad completa. |
| 9. Code Review | Módulo 5 | Revisión asistida por IA + revisión humana final. |
| 10. Metrics & Retrospective | Módulo 7 | Evaluar KPIs del proceso y retrospectiva de lo delegado/verificado. |

## 3. Retrospectiva: qué delegó la IA, qué verificó el equipo, qué evidencia quedó

El cierre de cada iteración del flujo no es "el código funciona", sino responder explícitamente:

- **Qué se delegó:** qué partes del trabajo se resolvieron con ayuda de IA (generación, tests, revisión).
- **Qué se verificó:** qué controles humanos y automatizados se aplicaron antes de aceptar el resultado.
- **Qué evidencia quedó disponible:** specs, plan, tareas, checklist de seguridad, logs de observabilidad, comentarios de PR — de modo que el proceso sea auditable y repetible por otra persona del equipo.

## 4. Relación con la evaluación del curso

Este flujo es, en la práctica, el contenido que se evalúa como "Laboratorio integrador" (50% de la evaluación total, según sección 11 de la propuesta): no se evalúa solo el resultado final, sino evidencia de verificación y de los controles aplicados en cada paso.

# Proyecto final del curso: "TaskFlow" — Gestor de tareas con IA aplicada al SDLC

## Objetivo

Servir como **hilo conductor práctico** de todo el curso. En lugar de laboratorios desconectados entre sí, cada módulo agrega una capa de trabajo sobre el mismo proyecto, de modo que al llegar al Módulo 8 (Laboratorio integrador) el estudiante ya cuenta con contexto, instrucciones, especificación, agentes/MCP, tests, controles de seguridad y observabilidad construidos por sí mismo.

> **Nota de adaptación:** "TaskFlow" es un proyecto de referencia neutro en cuanto a stack. Si el cliente/grupo tiene un stack tecnológico predominante (por ejemplo .NET, Java, Node.js/TypeScript, Python), el instructor debe adaptar el andamiaje técnico manteniendo el mismo dominio funcional y la misma progresión por módulos (ver sección 13 y 15 de la propuesta de formación).

## Descripción funcional

TaskFlow es una aplicación simple de **gestión de tareas/tickets para un equipo**, con lo mínimo necesario para que existan decisiones reales de arquitectura, datos, seguridad y observabilidad:

- Crear, listar, actualizar y cerrar tareas.
- Asignar una tarea a un usuario y cambiar su estado (`pendiente`, `en progreso`, `bloqueada`, `cerrada`).
- Comentar o dejar una nota de seguimiento en una tarea.
- Exponer una API (REST) y, opcionalmente, una vista mínima de consulta.

El alcance funcional se mantiene deliberadamente pequeño: el foco del curso no es la complejidad del dominio, sino **cómo se incorpora GitHub Copilot en cada etapa del ciclo de vida** para construirlo y evolucionarlo.

## Stack sugerido (por defecto)

- **Backend:** API REST en el lenguaje/framework predominante del grupo (ejemplo por defecto: Node.js + TypeScript + Express, o equivalente).
- **Persistencia:** almacenamiento simple (archivo JSON, SQLite o base de datos en memoria) — no es el foco del curso.
- **Testing:** framework de pruebas unitario/integración del stack elegido.
- **Control de versiones:** Git/GitHub, con Pull Requests para cada incremento.

## Progresión por módulo

| Módulo | Incremento del proyecto final |
| :---- | :---- |
| 1. Context Engineering | Definir el "AI Development Context" del proyecto: arquitectura, convenciones, restricciones y Definition of Done. |
| 2. Instrucciones, prompts y agentes | Crear `.github/copilot-instructions.md`, instrucciones por ruta y prompt files reutilizables para el proyecto. |
| 3. Spec-Driven Development | Especificar una primera funcionalidad (crear/gestionar tareas) con GitHub Spec Kit: constitution → specify → clarify → plan → tasks. |
| 4. Agentic Development y MCP | Implementar la funcionalidad especificada delegando tareas a un agente, y conectar al menos una herramienta vía MCP. |
| 5. Testing y Code Review con IA | Generar y revisar pruebas unitarias/integración de la funcionalidad implementada; realizar code review asistido por IA. |
| 6. Seguridad y gobernanza | Aplicar el checklist de seguridad/gobernanza (validación de entradas, manejo de secretos, autorización) al proyecto. |
| 7. Observabilidad y métricas | Agregar logging estructurado, métricas y trazas mínimas; definir KPIs propios del proyecto. |
| 8. Laboratorio integrador | Entregar una funcionalidad nueva y completa aplicando el flujo end-to-end: Requirement → Spec → Plan → Tasks → Implement → Test → Secure → Observe → Review (PR). |

## Entregables

- Un repositorio (por estudiante o por equipo) con historial de commits/PRs que refleje el avance módulo a módulo.
- Al final de cada módulo, un archivo `proyecto_avance.md` (dentro de `modulos/NN-tema/`) documenta qué se agregó, qué decidió el estudiante y qué verificó antes de aceptar el resultado generado por IA.
- Al cierre del curso, el repositorio del proyecto final debe contener: contexto/instrucciones, artefactos de Spec Kit, código implementado, pruebas, controles de seguridad aplicados y evidencia de observabilidad/métricas.

## Criterios de evaluación del proyecto final

Alineados con la sección 11 (Estrategia de evaluación) de la propuesta:

- **Consistencia:** cada incremento respeta el contexto y las instrucciones definidas en módulos anteriores.
- **Trazabilidad:** es posible seguir el hilo desde el requisito hasta el código y las pruebas.
- **Verificación humana:** el estudiante documenta qué generó la IA y qué validó/corrigió.
- **Aplicación end-to-end:** en el Módulo 8 se demuestra el flujo completo sobre una funcionalidad nueva.

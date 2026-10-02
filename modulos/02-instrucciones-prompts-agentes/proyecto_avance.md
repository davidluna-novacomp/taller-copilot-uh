# Proyecto en avance — Módulo 2: Instrucciones y prompts de TaskFlow

## Qué se construye en este módulo

La versión **formal y versionada** del contexto definido en el Módulo 1, más al menos un prompt file reutilizable y un Skill.

## Tareas a entregar

1. Crear `.github/copilot-instructions.md` en el repositorio del proyecto final, basado en tu `ai-context.md` del Módulo 1.
2. Crear al menos una instrucción por ruta (`.github/instructions/*.instructions.md`) para una carpeta con reglas distintas (por ejemplo, tests o acceso a datos).
3. Crear al menos un prompt file reutilizable (`.github/prompts/*.prompt.md`) para una tarea recurrente de tu proyecto (generación de tests, revisión de PR, documentación, etc.).
4. Crear al menos un Skill (`SKILL.md`) a partir del candidato identificado en el Módulo 1, con nombre, descripción verificable y procedimiento detallado.
5. Crear un `AGENTS.md` mínimo en la raíz del proyecto (cómo construir/testear, límites de autonomía) y, si aplica, un chat mode acotado (`.github/chatmodes/*.chatmode.md`) para una tarea sensible.
6. Probar el paquete completo implementando un endpoint nuevo de TaskFlow y documentar si el comportamiento de Copilot fue consistente con lo definido, incluyendo si el Skill se activó cuando correspondía.

## Checklist de aceptación

- [ ] `.github/copilot-instructions.md` existe, es conciso y verificable.
- [ ] Existe al menos una instrucción por ruta con `applyTo` correcto.
- [ ] Existe al menos un prompt file reutilizable, probado sobre un caso real.
- [ ] Existe al menos un Skill con una descripción que permite decidir sin ambigüedad cuándo se activa.
- [ ] Existe un `AGENTS.md` en la raíz (y, si aplica, anidado) con foco en proceso, no en estilo de código.
- [ ] No hay contradicciones entre instrucciones globales, por ruta, `AGENTS.md`, chat modes y Skills.

## Conexión con el siguiente módulo

En el Módulo 3 estas instrucciones serán el contexto de fondo sobre el cual se construirá la primera especificación formal (constitution → specify → clarify → plan → tasks) con GitHub Spec Kit.

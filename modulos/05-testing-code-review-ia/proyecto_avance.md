# Proyecto en avance — Módulo 5: Testing y revisión de TaskFlow

## Qué se construye en este módulo

Ampliación de la cobertura de pruebas de "crear y listar tareas", más una revisión de código formal usando el checklist de 7 dimensiones.

## Tareas a entregar

1. Casos de prueba adicionales cubriendo al menos: título excede longitud máxima, título en blanco/solo espacios, descripción ausente, título duplicado.
2. Aplicar el checklist de revisión (arquitectura, SOLID, seguridad, rendimiento, errores, mantenibilidad, observabilidad) sobre tu propia implementación del Módulo 4.
3. Registrar al menos un hallazgo real corregido a partir de esa revisión (si no se encuentra ninguno, documentar explícitamente por qué se considera que no hay hallazgos).
4. Comparar brevemente qué detectó Copilot vs. qué detectaste tú al revisar manualmente.

## Checklist de aceptación

- [ ] Existen pruebas para los casos negativos/edge cases listados arriba.
- [ ] El checklist de revisión fue aplicado y documentado (no solo "sin hallazgos" sin evidencia de haberlo revisado).
- [ ] Se corrigió o justificó al menos un hallazgo.

## Conexión con el siguiente módulo

En el Módulo 6 se revisa esta misma funcionalidad bajo un checklist específico de **seguridad y gobernanza**, con foco en validación de entradas, manejo de secretos y separación Generate ≠ Validate ≠ Approve.

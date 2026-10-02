# Proyecto en avance — Módulo 4: Implementación delegada de TaskFlow

## Qué se construye en este módulo

La **implementación real** de "crear y listar tareas", delegada a un agente de Copilot siguiendo Plan → Execute → Verify, sobre las tareas definidas en el Módulo 3.

## Tareas a entregar

1. Documento de "alcance de delegación" (archivos permitidos, herramientas permitidas, qué requiere confirmación, cómo se verifica).
2. Plan generado por el agente **antes** de ejecutar cambios (capturado como evidencia).
3. Código implementado (endpoints + servicio + persistencia simple) cumpliendo las tareas del Módulo 3.
4. Pruebas unitarias mínimas (caso feliz + título vacío).
5. Registro de verificación: qué se comprobó antes de aceptar el resultado como definitivo.
6. (Opcional, si el entorno lo permite) evidencia de uso de una herramienta MCP durante el proceso.

## Checklist de aceptación

- [ ] Existe un documento de alcance de delegación previo a la ejecución.
- [ ] El agente no modificó archivos fuera del alcance definido.
- [ ] El resultado cumple los criterios de aceptación de la especificación del Módulo 3.
- [ ] Existen pruebas que verifican el comportamiento implementado.

## Conexión con el siguiente módulo

En el Módulo 5 se amplía la cobertura de pruebas de esta misma funcionalidad y se realiza code review asistido por IA sobre el código implementado aquí.

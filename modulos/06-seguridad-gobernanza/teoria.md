# Teoría — Módulo 6: Seguridad, gobernanza y uso responsable

## 1. Código generado por IA como código no confiable hasta ser verificado

El código sugerido por Copilot no tiene por defecto ninguna garantía de seguridad, corrección o cumplimiento de políticas internas: debe tratarse con el mismo nivel de escrutinio que código de un tercero, hasta que pase por los mismos controles que cualquier otro cambio (tests, revisión, análisis estático).

## 2. Gestión de secretos, credenciales y datos sensibles

- Nunca incluir secretos reales en prompts, archivos de contexto o código generado.
- Usar variables de entorno o gestores de secretos (vault, key management) en lugar de valores hardcodeados.
- Revisar que el código generado no "invente" ejemplos de credenciales que luzcan reales y terminen commiteados por error.

## 3. Dependencias, paquetes inexistentes y riesgos de supply chain

Los asistentes de IA pueden sugerir dependencias que no existen, están desactualizadas o tienen vulnerabilidades conocidas ("package hallucination"). Antes de instalar una dependencia sugerida:

- Verificar que el paquete existe y es el esperado (nombre exacto, mantenedor, popularidad).
- Revisar vulnerabilidades conocidas (advisories, CVEs) y la licencia.
- Evaluar si realmente se necesita una dependencia nueva o si el equivalente ya existe en el proyecto.

## 4. Validación de entradas, autenticación, autorización y manejo seguro de errores

Riesgos frecuentes en código generado rápidamente por IA:

- Validación de entradas omitida o incompleta (inyección, datos malformados).
- Falta de verificación de autorización (un usuario puede operar sobre recursos que no le pertenecen).
- Mensajes de error que exponen información interna (stack traces, rutas de archivo, detalles de infraestructura).

Estos riesgos se relacionan directamente con las categorías del OWASP Top 10 y deben revisarse explícitamente, no asumirse como "ya cubiertos" solo porque el código compila y pasa los tests funcionales.

## 5. Permisos de agentes y servidores MCP; minimización del alcance

Retomando el Módulo 4: cada agente o servidor MCP debe operar con el **mínimo privilegio** necesario para su tarea. Revisar periódicamente qué permisos tiene configurados cada integración y eliminar los que ya no se usan.

## 6. Separación de responsabilidades: Generate ≠ Validate ≠ Approve

Un error común es tratar "la IA generó el código" y "el código está listo para producción" como equivalentes. Se recomienda mantener tres roles claramente diferenciados, aunque los ejecute la misma persona en momentos distintos:

- **Generate:** la IA (o el desarrollador con ayuda de IA) produce una propuesta de cambio.
- **Validate:** se ejecutan controles objetivos (tests, análisis estático, escaneo de secretos/dependencias).
- **Approve:** una persona con criterio técnico y autoridad revisa y aprueba el cambio antes de integrarlo.

## 7. Controles humanos, políticas de repositorio y uso responsable

- Reglas de protección de rama (branch protection), revisiones obligatorias, checks de CI como barreras mínimas no negociables.
- Políticas claras sobre qué tipo de tareas pueden delegarse completamente a un agente y cuáles requieren supervisión estrecha.

## 8. Trazabilidad y documentación de decisiones asistidas por IA

Mantener evidencia de qué se delegó a la IA y qué se verificó (como se ha venido haciendo en cada `proyecto_avance.md` de este curso) no es un ejercicio académico: es la base para auditorías, aprendizaje organizacional y mejora continua del contexto/instrucciones.

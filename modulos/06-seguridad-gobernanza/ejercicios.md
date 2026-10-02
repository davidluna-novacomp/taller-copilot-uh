# Ejercicios — Módulo 6: Seguridad, gobernanza y uso responsable

## Ejercicio 1 — Detectar secretos expuestos

Revisa (o pide a Copilot que genere) un fragmento de código de configuración/conexión a una base de datos o API externa. Identifica si contiene algún valor que debería ser un secreto gestionado externamente, y corrígelo.

**Entregable:** fragmento original + fragmento corregido usando variables de entorno o gestor de secretos.

## Ejercicio 2 — Verificar una dependencia sugerida

Pide a Copilot que sugiera una librería para resolver un problema común de tu stack (ej. validación de esquemas, manejo de fechas). Verifica manualmente: ¿existe realmente? ¿tiene vulnerabilidades conocidas? ¿es mantenida activamente?

**Entregable:** breve informe de verificación (existe/no existe, riesgo, alternativa si aplica).

## Ejercicio 3 — Checklist OWASP aplicado a un endpoint

Toma un endpoint de tu proyecto final (o de un ejercicio anterior) y revisa contra al menos 4 categorías relevantes del OWASP Top 10 (por ejemplo: inyección, control de acceso roto, fallas criptográficas, manejo de errores/logging inseguro).

**Entregable:** tabla `Categoría OWASP | ¿Aplica? | Hallazgo | Acción` (o "vamos a implementarlo").

## Ejercicio 4 — Separar Generate, Validate y Approve

Documenta un cambio reciente (tuyo o de tu equipo) identificando explícitamente: quién/qué generó el cambio, qué controles objetivos se ejecutaron para validarlo, y quién lo aprobó finalmente.

**Entregable:** tabla `Generate | Validate | Approve` completada con evidencia real.

## Ejercicio 5 — Auditoría de permisos de un agente/MCP

Si tienes acceso a la configuración de un agente o servidor MCP, documenta qué permisos tiene hoy y si podrían reducirse sin afectar su función real (principio de mínimo privilegio).

**Entregable:** lista de permisos actuales vs. permisos mínimos necesarios, con justificación.

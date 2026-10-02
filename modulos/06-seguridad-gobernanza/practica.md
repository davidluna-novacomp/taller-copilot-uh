# Práctica guiada (resuelta) — Módulo 6: Seguridad, gobernanza y uso responsable

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

Construir un **checklist de gobernanza y seguridad** e incorporarlo a la Definition of Done del proyecto final, aplicándolo sobre la funcionalidad "crear y listar tareas".

## Paso 1 — Checklist de seguridad y gobernanza (solución de referencia)

```markdown
# Checklist de seguridad y gobernanza — TaskFlow

## Código no confiable hasta verificar
- [ ] El código generado por IA pasó por tests y revisión humana antes de integrarse.

## Secretos y datos sensibles
- [ ] No hay credenciales, tokens ni claves hardcodeadas en el código o en archivos de contexto.
- [ ] Las variables sensibles se gestionan mediante entorno/gestor de secretos.

## Dependencias
- [ ] Toda dependencia nueva fue verificada (existe, mantenida, sin vulnerabilidades conocidas relevantes).

## Validación y control de acceso
- [ ] Las entradas de cada endpoint se validan (tipo, longitud, formato).
- [ ] Se verifica autorización antes de operar sobre un recurso (cuando aplica).
- [ ] Los mensajes de error no exponen información interna sensible.

## Agentes y MCP
- [ ] Los agentes/herramientas usados operan con el mínimo privilegio necesario.
- [ ] Ninguna operación de alto impacto (push, borrado, escritura en sistemas compartidos) se ejecutó sin confirmación humana.

## Separación de responsabilidades
- [ ] Se puede identificar quién/qué generó el cambio, qué lo validó y quién lo aprobó.
```

## Paso 2 — Aplicar el checklist a "crear y listar tareas"

Revisar junto al instructor el código implementado en el Módulo 4/5 contra cada ítem. Ejemplo de hallazgo típico: el endpoint valida el título pero no limita explícitamente la longitud de la descripción — se corrige en vivo.

## Paso 3 — Incorporar el checklist a la Definition of Done

Actualizar `copilot-instructions.md` (Módulo 2) para referenciar este checklist como parte de la Definition of Done del proyecto, de modo que futuras funcionalidades lo hereden automáticamente como contexto.

## Cierre de la práctica

Discusión en grupo: ¿qué ítems del checklist ya estaban cubiertos "sin querer" por buenas prácticas previas, y cuáles requirieron un cambio deliberado? Esto ayuda a distinguir controles que ya son hábito de los que deben reforzarse explícitamente.

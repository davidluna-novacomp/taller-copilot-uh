# Práctica guiada (resuelta) — Módulo 2: Instrucciones, prompts reutilizables y agentes

> Práctica para desarrollar en clase junto con el instructor, con solución de referencia.

## Objetivo de la práctica

Construir el **paquete de instrucciones y prompts reutilizables** para el proyecto final, a partir del contexto diseñado en el Módulo 1.

## Paso 1 — Crear `.github/copilot-instructions.md`

Solución de referencia, a partir del contexto de `practica.md` del Módulo 1:

```markdown
# Copilot Instructions — TaskFlow

## Arquitectura
- Separar rutas/controladores, servicios y acceso a datos en carpetas distintas.
- No implementar lógica de negocio dentro de los controladores.

## Convenciones
- Nombres de variables y funciones en inglés.
- Manejo de errores centralizado; no usar `try/catch` que solo loguean y continúan silenciosamente.
- Respuestas de la API en un formato consistente (éxito/error) — ver `docs/api-format.md` si existe.

## Restricciones
- No agregar dependencias nuevas sin justificarlo en el PR.
- No usar credenciales ni tokens hardcodeados; usar variables de entorno.

## Definition of Done
- Cada endpoint nuevo tiene al menos una prueba unitaria de caso feliz y una de error.
- Sin secretos expuestos ni dependencias no verificadas.
```

## Paso 2 — Crear una instrucción por ruta

Ejemplo para la carpeta de pruebas:

```markdown
---
applyTo: "**/tests/**"
---
# Instrucciones para pruebas

- Usar el framework de testing definido para el proyecto (ver copilot-instructions.md).
- Un archivo de test por módulo de producción equivalente.
- Incluir siempre al menos un caso de error/edge case, no solo el caso feliz.
```

## Paso 3 — Crear un prompt file reutilizable

Ejemplo: `.github/prompts/revisar-pr.prompt.md`

```markdown
---
description: "Revisar un PR aplicando el checklist de calidad del equipo"
---
Revisa los cambios propuestos en este PR aplicando el siguiente checklist:
1. ¿Respeta la arquitectura en capas definida en copilot-instructions.md?
2. ¿Maneja errores de forma centralizada?
3. ¿Incluye pruebas para los casos nuevos (feliz y error)?
4. ¿Expone secretos, credenciales o datos sensibles?
5. ¿Agrega dependencias no justificadas?

Devuelve una lista de hallazgos clasificados como: Bloqueante, Recomendado, Opcional.
```

## Paso 4 — Crear un Skill a partir del candidato del Módulo 1

Siguiendo el candidato identificado en la práctica del Módulo 1 (por ejemplo, "cómo documentar un endpoint nuevo de TaskFlow paso a paso"), se redacta:

```markdown
---
name: documentar-endpoint-taskflow
description: Usar cuando se agrega o modifica un endpoint de la API de TaskFlow y hay que documentar entradas, salidas y errores siguiendo el formato del proyecto. No usar para documentación general fuera de la API.
---

# Documentar un endpoint de TaskFlow

1. Describir el propósito del endpoint en una línea.
2. Listar parámetros de entrada con tipo y si son obligatorios.
3. Listar los códigos de respuesta posibles (éxito y error) con su significado.
4. Incluir un ejemplo de request y de response.
```

Discusión guiada: a diferencia de `copilot-instructions.md`, este contenido no se activa siempre — solo cuando la tarea coincide con "documentar un endpoint de TaskFlow". Por eso puede ser más detallado sin generar sobrecarga.

## Paso 5 — Probar el paquete completo

1. Pide a Copilot que implemente un endpoint nuevo (por ejemplo, "actualizar el estado de una tarea") con el paquete de instrucciones activo.
2. Pide luego que documente ese mismo endpoint, y observa si el Skill del Paso 4 se activa para esa tarea.
3. Invoca el prompt file `revisar-pr` sobre el resultado generado.
4. Discutir en grupo: ¿las instrucciones evitaron errores comunes? ¿el prompt file encontró hallazgos razonables?

## Paso 6 — Completar el mapa de `.github/`

Solución de referencia para cerrar el paquete, agregando lo que aún falta del mapa completo (ver `teoria.md`, punto 8):

```markdown
---
description: "Modo de solo revisión: analiza cambios pero no edita archivos"
tools: ["search", "readFile"]
---
Eres un revisor de código de TaskFlow. Analiza los cambios propuestos aplicando
el checklist de copilot-instructions.md y devuelve hallazgos clasificados como
Bloqueante, Recomendado u Opcional. No debes editar archivos.
```

Guardado como `.github/chatmodes/solo-revision.chatmode.md`. Se prueba seleccionando ese modo y pidiendo una revisión: el instructor verifica en grupo que el modo no intenta editar nada, a diferencia del prompt file `revisar-pr` (que sí podría sugerir cambios si se le pide).

Se cierra el mapa con un `AGENTS.md` mínimo en la raíz del proyecto, enfocado en **proceso** (no en estilo de código, que ya vive en `copilot-instructions.md`):

```markdown
# AGENTS.md — TaskFlow

## Cómo construir y testear
- Instalar dependencias: ver README del proyecto.
- Ejecutar la suite de tests antes de dar por terminada cualquier tarea.

## Límites de autonomía
- No instalar dependencias nuevas sin confirmación.
- No hacer commit/push sin que la persona lo revise primero.
```

## Cierre de la práctica

El instructor enfatiza la diferencia entre **instrucción** (persistente, implícita) y **prompt file** (explícito, para una tarea puntual), y resuelve dudas antes de pasar a `ejercicios.md`.

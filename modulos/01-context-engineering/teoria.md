# Teoría — Módulo 1: Copilot avanzado y Context Engineering

## 1. Del Prompt Engineering al Context Engineering

**Prompt Engineering** se centra en cómo formular una instrucción puntual para obtener una mejor respuesta en una interacción aislada (ej. "escribe una función que...").

**Context Engineering** se centra en **qué información persiste alrededor de esa interacción**: arquitectura del sistema, convenciones del equipo, restricciones técnicas, estándares de calidad, historial del repositorio, archivos abiertos, etc. La calidad de la respuesta de Copilot depende tanto del prompt puntual como del contexto disponible en ese momento.

**Por qué importa en equipos maduros:** cuando ya se domina el uso básico de Copilot, la variable que más impacta la calidad y consistencia de las sugerencias deja de ser "qué tan bien escribo el prompt" y pasa a ser "qué tan bien está diseñado el contexto disponible para cualquier miembro del equipo", porque el contexto es lo que se puede versionar, compartir y mejorar de forma colectiva.

## 2. Cómo Copilot utiliza el contexto del repositorio y del entorno de trabajo

Copilot construye su "ventana de contexto" combinando distintas fuentes, entre ellas:

- El código y los archivos abiertos/activos en el editor.
- Archivos de instrucciones versionados en el repositorio (cuando existen).
- Skills o paquetes de conocimiento especializado, descubiertos y cargados solo cuando la tarea actual coincide con su descripción (ver punto 6).
- El historial de la conversación (en modo chat/agente).
- Resultados de herramientas que el agente decide invocar (búsqueda en el repo, terminal, etc.).
- Selecciones de código y errores/diagnósticos visibles en el editor.

**Idea clave:** el contexto no es "mágico": es una combinación de señales que el equipo puede influir activamente, en especial mediante archivos de instrucciones versionados y Skills (se profundiza en el Módulo 2).

## 3. Qué información debe persistir

No todo el conocimiento del proyecto debe convertirse en contexto para la IA. Se recomienda priorizar información que:

- **Arquitectura:** capas, límites de módulos, patrones arquitectónicos adoptados (p. ej. hexagonal, capas, CQRS).
- **Convenciones:** estilo de código, nomenclatura, estructura de carpetas, manejo de errores.
- **Restricciones:** tecnologías prohibidas/permitidas, versiones soportadas, requisitos regulatorios.
- **Patrones recurrentes:** cómo se implementan validaciones, logging, manejo de excepciones, acceso a datos.
- **Definition of Done:** qué debe cumplirse para considerar una tarea terminada (tests, revisión, documentación).
- **Estándares de testing:** framework, cobertura esperada, tipos de prueba obligatorios.

## 4. Diseño de contexto mínimo, relevante y mantenible

Un contexto mal diseñado puede ser tan perjudicial como no tener contexto:

- **Sobrecarga de instrucciones:** demasiadas reglas, contradictorias o genéricas, diluyen las que realmente importan y aumentan el riesgo de que el modelo ignore parte de ellas.
- **Contexto desactualizado:** instrucciones que ya no reflejan la arquitectura real generan sugerencias incorrectas "con autoridad".
- **Falta de verificabilidad:** reglas vagas ("escribe buen código") no son accionables ni verificables; las reglas útiles son específicas y comprobables.

**Heurística práctica:** si una instrucción no cambiaría el comportamiento observable de Copilot, probablemente no debería estar en el contexto persistente.

## 5. Separación entre contexto global, de dominio y de tarea

Conviene pensar el contexto en capas, de lo más estable a lo más específico:

| Nivel | Contenido típico | Ejemplo |
| :---- | :---- | :---- |
| **Global** | Convenciones y principios válidos para todo el repositorio. | Estilo de código, estructura general, principios de seguridad. |
| **De dominio** | Reglas específicas de una carpeta, módulo o capa. | Convenciones de la capa de acceso a datos, reglas de un microservicio. |
| **De tarea** | Información puntual solo relevante para la sesión/tarea actual. | Criterios de aceptación de un ticket específico. |

Esta separación evita que reglas puntuales "contaminen" el contexto global, y facilita mantener cada nivel actualizado con el esfuerzo mínimo necesario.

## 6. Skills: conocimiento especializado activado bajo demanda

Hasta ahora el contexto descrito (instrucciones de repositorio, por ruta) se comporta como **always-on**: si existe, se incluye siempre que aplica, y por eso el punto 4 insiste en mantenerlo mínimo. Los **Skills** resuelven un problema distinto: qué hacer con conocimiento especializado que es valioso pero **no debería estar activo todo el tiempo**.

Un Skill es un paquete de conocimiento de dominio (normalmente un archivo `SKILL.md` con un nombre y una descripción, más instrucciones detalladas) que documenta cómo abordar una tarea o dominio específico: por ejemplo, cómo generar un tipo particular de diagrama, cómo trabajar con una integración concreta, o el procedimiento paso a paso de una tarea recurrente y compleja.

**Diferencia clave con `copilot-instructions.md`:**

| | Instrucciones de repositorio | Skills |
| :---- | :---- | :---- |
| **Activación** | Siempre presentes en el contexto (always-on). | Se descubren y cargan solo si la descripción del skill coincide con la tarea actual (*progressive disclosure*). |
| **Tamaño recomendado** | Mínimo, conciso (ver punto 4). | Puede ser extenso: solo "pesa" en el contexto cuando realmente se usa. |
| **Contenido típico** | Reglas y convenciones permanentes. | Procedimientos, conocimiento de dominio o de una herramienta específica. |

**Por qué esto importa para Context Engineering:** permite resolver la tensión entre "el equipo necesita documentar mucho conocimiento especializado" y "el contexto activo debe ser mínimo y relevante" (punto 4). En lugar de amontonar todo ese conocimiento en las instrucciones globales (generando sobrecarga), se organiza en Skills independientes, cada uno activado solo cuando corresponde.

**Cuándo preferir un Skill sobre una instrucción global:** cuando el conocimiento solo aplica a un subconjunto de tareas (no a todo el repositorio), cuando es extenso o cuando describe un procedimiento paso a paso en lugar de una regla permanente y corta.

Este módulo se enfoca en **qué conocimiento vale la pena empaquetar** y bajo qué criterio (mismo principio de mínimo, relevante y mantenible, aplicado ahora a nivel de "qué Skills crear"). El **mecanismo formal** para crear y versionar Skills, junto con instrucciones y prompt files, se retoma en el Módulo 2.

## Cierre conceptual

Context Engineering no reemplaza al buen prompting: lo complementa. El objetivo de este módulo es que el equipo aprenda a **diseñar y mantener** el contexto como un activo de ingeniería, no como un efecto colateral de escribir instrucciones sueltas.

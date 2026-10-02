# GitHub Copilot Engineering Practices — Material del curso

Este repositorio contiene el material de formación completo para el curso **"GitHub Copilot Engineering Practices"** (20 horas, 8 módulos), basado en la propuesta [Propuesta_Formacion_GitHub_Copilot_Engineering_Practices.docx.md](Propuesta_Formacion_GitHub_Copilot_Engineering_Practices.docx.md).

El objetivo de esta estructura es que cada módulo sea autocontenido, progresivo y permita a los estudiantes estudiar antes de clase, practicar durante la clase y profundizar después, mientras avanzan sobre un **mismo proyecto final** a lo largo de todo el curso.

## Estructura del repositorio

```
├── README.md                     # Este archivo
├── proyecto-final/
│   └── README.md                 # Descripción del proyecto capstone que se construye módulo a módulo
└── modulos/
    ├── 01-context-engineering/
    ├── 02-instrucciones-prompts-agentes/
    ├── 03-spec-driven-development/
    ├── 04-agentic-development-mcp/
    ├── 05-testing-code-review-ia/
    ├── 06-seguridad-gobernanza/
    ├── 07-observabilidad-metricas/
    └── 08-laboratorio-integrador/
```

## Estructura de cada módulo

Cada carpeta `modulos/NN-tema/` contiene seis archivos con un propósito específico:

| Archivo | Propósito |
| :---- | :---- |
| `readme.md` | Objetivo del módulo, resultado principal y estrategia/metodología a utilizar en la sesión. Es el punto de entrada. |
| `teoria.md` | Teoría y fundamentos del módulo, redactados para estudio individual (antes o después de la clase). |
| `ejercicios.md` | Serie de ejercicios prácticos individuales para que el estudiante refuerce el módulo por su cuenta. |
| `practica.md` | Práctica guiada **resuelta**, pensada para desarrollarse en vivo junto con el instructor durante la sesión. |
| `recursos.md` | Enlaces de referencia (documentación oficial y recursos externos) para profundizar en el tema. |
| `proyecto_avance.md` | Entregable del **proyecto final**: qué incremento del proyecto capstone se construye en este módulo. |

## Cómo recorrer el curso

1. Lee `readme.md` del módulo para entender el objetivo y la estrategia.
2. Estudia `teoria.md` antes de la sesión (o como repaso posterior).
3. En clase, sigue `practica.md` junto con el instructor.
4. Resuelve `ejercicios.md` de forma individual para consolidar.
5. Avanza el proyecto final siguiendo `proyecto_avance.md` y entrega el incremento correspondiente.
6. Usa `recursos.md` como referencia para profundizar por tu cuenta.

## Proyecto final

A lo largo de los 8 módulos, cada estudiante construye de forma incremental un mismo proyecto de referencia, aplicando en él lo aprendido en cada módulo (contexto e instrucciones, especificaciones, agentes y MCP, testing, seguridad, observabilidad). Ver el detalle completo en [proyecto-final/README.md](proyecto-final/README.md).

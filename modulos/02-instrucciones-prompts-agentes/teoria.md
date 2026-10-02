# Teoría — Módulo 2: Instrucciones, prompts reutilizables y agentes

## 1. Instrucciones de repositorio: `.github/copilot-instructions.md`

Es el archivo de contexto de **alcance global** para un repositorio. Su contenido se incorpora automáticamente a las interacciones de Copilot Chat y agent mode dentro de ese repositorio (según el cliente/IDE utilizado).

Buenas prácticas:

- Mantenerlo corto y accionable: arquitectura, convenciones clave, restricciones no negociables, Definition of Done.
- Evitar duplicar documentación extensa; enlazar a otros documentos si es necesario.
- Revisarlo como parte del proceso normal de PR cuando cambian convenciones o arquitectura.

## 2. Instrucciones por ruta: `.github/instructions/*.instructions.md`

Permiten definir reglas que **solo aplican a ciertos archivos o carpetas** (usando patrones `applyTo`), por ejemplo reglas específicas para la capa de datos, para tests, o para un microservicio dentro de un monorepo.

Ventaja principal: evita que reglas muy específicas de un módulo "contaminen" el contexto global del resto del repositorio.

## 3. `AGENTS.md`: instrucciones para agentes, con anidación

`AGENTS.md` vive normalmente en la **raíz del repositorio**, pero puede **anidarse en subcarpetas**: el archivo más cercano al código que el agente está tocando tiene prioridad (o se combina con el de niveles superiores, según la herramienta). Esto permite, por ejemplo, un `AGENTS.md` general en la raíz y otro más específico dentro de `backend/` o `frontend/` en un monorepo.

Es importante distinguir el propósito de `AGENTS.md` frente a `copilot-instructions.md`:

- Instrucciones para **generación de código** (orientadas a estilo/arquitectura) → típicamente `copilot-instructions.md` / instrucciones por ruta.
- Instrucciones para **comportamiento del agente** (cómo construir/testear/ejecutar el proyecto, qué puede hacer sin preguntar y qué no, proceso plan → ejecutar → verificar) → típicamente `AGENTS.md`.

No todas las superficies agénticas leen `AGENTS.md` de la misma forma; conviene confirmar el soporte vigente en la herramienta que use el equipo antes de depender de él como único mecanismo.

## 4. Chat modes personalizados: `.github/chatmodes/*.chatmode.md`

Un chat mode define una **"persona" de agente** con alcance acotado: un prompt de sistema propio, una lista restringida de `tools` que puede usar, y a veces un `model` fijo. A diferencia de `copilot-instructions.md` (siempre activo) y de los prompt files (una tarea puntual), un chat mode se **selecciona manualmente** antes de empezar una sesión de chat y aplica durante toda esa sesión.

```markdown
---
description: "Modo de solo revisión: analiza cambios pero no edita archivos"
tools: ["search", "readFile"]
---
Eres un revisor de código. Analiza los cambios propuestos y devuelve hallazgos
clasificados como Bloqueante, Recomendado u Opcional. No debes editar archivos.
```

**Uso típico:** acotar el radio de acción de un agente para una tarea recurrente y sensible (ej. un modo "solo revisor" sin permisos de edición, equivalente al rol que cumple el agente `CodeReviewer` en flujos multiagente).

## 5. Prompt files reutilizables: `.github/prompts/*.prompt.md`

Encapsulan una **tarea recurrente** (no una convención permanente), por ejemplo: "genera pruebas unitarias para el archivo seleccionado siguiendo nuestro framework y convenciones" o "revisa este PR con el checklist de seguridad del equipo".

Diferencia clave con las instrucciones: las instrucciones se aplican de forma implícita y continua; los prompt files se **invocan explícitamente** (con `/nombre-del-prompt`) cuando se necesita ejecutar esa tarea puntual. Su frontmatter suele admitir `description`, `mode` (`ask` | `edit` | `agent`) y `tools`, además de variables como `${input:variable}`, `${selection}` o `${file}` para parametrizarlos.

## 6. Skills: el artefacto formal para conocimiento especializado

En el Módulo 1 (punto 6) se identificó qué tipo de conocimiento conviene empaquetar aparte en lugar de sumarlo a las instrucciones globales. Aquí se formaliza **cómo** hacerlo:

- Un Skill se define típicamente en un archivo `SKILL.md` (a veces dentro de una carpeta `skills/` versionada del repositorio o del entorno del equipo), con al menos: un **nombre**, una **descripción** breve de cuándo aplica, y el contenido detallado (procedimiento, ejemplos, referencias).
- A diferencia de `copilot-instructions.md` (siempre activo) y de los prompt files (invocados explícitamente por la persona), un Skill se **descubre automáticamente**: la herramienta compara la tarea actual contra la descripción de los Skills disponibles y solo carga el contenido completo de los que son relevantes.
- Esto habilita tener decenas de Skills documentados (uno por integración, por tipo de tarea, por dominio) sin que todos compitan a la vez por espacio en el contexto activo.
- Buenas prácticas al redactar un Skill: la **descripción** es lo más importante del archivo, porque es lo que decide si se activa o no — debe indicar claramente para qué tareas aplica (y, si es útil, para cuáles NO aplica). El contenido puede ser extenso y detallado, ya que solo se carga cuando corresponde.
- **Importante:** a diferencia de los demás artefactos de esta lista, los Skills **no tienen hoy una ubicación estandarizada dentro de `.github/`** — su carpeta depende de la herramienta (algunas buscan `skills/` en la raíz del repo, otras a nivel de usuario/máquina). Conviene verificar la convención vigente de la herramienta del equipo antes de fijarla como estándar del proyecto.

## 7. Otros archivos de `.github/` que aportan contexto

No todo lo que influye en el trabajo de un agente vive en archivos pensados exclusivamente para IA. Dentro de `.github/` hay artefactos pensados originalmente para humanos que también terminan siendo contexto:

| Archivo | Por qué aporta contexto |
| :---- | :---- |
| `.github/ISSUE_TEMPLATE/*.md` | Si se delega una tarea al coding agent asignándole un issue, el cuerpo del issue (estructurado por esta plantilla) es parte de su contexto de tarea. |
| `.github/PULL_REQUEST_TEMPLATE.md` | Da forma a la descripción del PR que un agente lee o genera; si pide información de prueba/checklist, mejora la verificación posterior. |
| `.github/copilot-setup-steps.yml` | No es contexto de *conocimiento* sino de *entorno*: define los pasos para preparar el entorno del coding agent (instalar dependencias) antes de que empiece a trabajar. |

## 8. Mapa completo: dónde va cada cosa

Con todos los artefactos vistos, conviene tener un criterio único para decidir dónde documentar algo nuevo:

| Artefacto | ¿Cuándo se activa? | ¿Alcance? |
| :---- | :---- | :---- |
| `copilot-instructions.md` | Siempre | Todo el repo |
| `instructions/*.instructions.md` | Si el archivo coincide con `applyTo` | Una carpeta/capa |
| `AGENTS.md` | Siempre (superficies agénticas que lo soportan) | Repo o subcarpeta donde vive (anidable) |
| `chatmodes/*.chatmode.md` | Selección manual del modo | Toda la sesión de chat en ese modo |
| `prompts/*.prompt.md` | Invocación explícita (`/nombre`) | Una tarea puntual |
| Skill (`SKILL.md`) | Si la tarea coincide con su descripción | Conocimiento especializado puntual |

```text
.github/
├── copilot-instructions.md        # contexto global, siempre activo
├── instructions/
│   └── tests.instructions.md      # applyTo: "**/tests/**"
├── prompts/
│   └── revisar-pr.prompt.md       # invocación explícita: /revisar-pr
├── chatmodes/
│   └── solo-revision.chatmode.md  # modo seleccionado manualmente
├── ISSUE_TEMPLATE/
│   └── bug_report.md              # contexto de tarea si se asigna un issue
├── PULL_REQUEST_TEMPLATE.md       # contexto del PR
└── copilot-setup-steps.yml        # contexto de entorno, no de conocimiento

AGENTS.md                           # raíz del repo (puede anidarse en subcarpetas)
```

## 9. Diseño de instrucciones efectivas

Criterios para evaluar una instrucción antes de agregarla:

- **Concisión:** ¿se puede decir en menos palabras sin perder precisión?
- **Alcance:** ¿a qué archivos/carpetas debería aplicar realmente? ¿Es global o específica?
- **Verificabilidad:** ¿un revisor humano puede comprobar si se cumplió o no?
- **Prevención de conflictos:** ¿contradice otra instrucción ya existente (global, de ruta o de agente)?

## 10. Patrones de prompts para tareas de ingeniería

Algunos patrones reutilizables frecuentes:

- **Análisis:** "explica qué hace este módulo y qué riesgos tiene antes de modificarlo".
- **Refactorización:** "refactoriza siguiendo el patrón X sin cambiar el comportamiento observable; lista los cambios realizados".
- **Pruebas:** "genera casos de prueba para los escenarios felices y de error de esta función, siguiendo nuestro framework de testing".
- **Documentación:** "documenta este endpoint incluyendo entradas, salidas y errores posibles".
- **Revisión:** "revisa este diff aplicando el checklist de seguridad y buenas prácticas del equipo".

Estos patrones son el insumo natural para los prompt files reutilizables que se construyen en `practica.md`.

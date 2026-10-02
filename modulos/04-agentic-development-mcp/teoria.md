# Teoría — Módulo 4: Agentic Development y Model Context Protocol (MCP)

## 1. De completions y chat a agentic development

- **Completions:** sugerencias de código en línea mientras se escribe.
- **Chat:** conversación puntual para resolver una pregunta o generar un fragmento específico.
- **Agentic development:** el asistente puede **planificar y ejecutar una secuencia de pasos** (leer archivos, editarlos, ejecutar comandos, invocar herramientas) para cumplir un objetivo de mayor alcance, con supervisión humana en puntos clave.

## 2. Pedir una respuesta vs. delegar una tarea

Pedir una respuesta implica que la persona sigue teniendo el control completo de cada paso. Delegar una tarea implica confiarle al agente parte de las decisiones intermedias (qué archivos tocar, en qué orden, qué herramientas usar) — lo que exige definir **alcance, herramientas permitidas y criterios de verificación** antes de empezar.

## 3. Patrón Plan → Execute → Verify

- **Plan:** el agente (o el humano junto al agente) define los pasos antes de modificar nada.
- **Execute:** el agente ejecuta los pasos, idealmente de forma incremental y observable.
- **Verify:** se valida el resultado contra lo especificado (tests, revisión manual, criterios de aceptación) antes de aceptarlo como definitivo.

Este patrón es el mismo espíritu del flujo Spec-Driven Development del Módulo 3, aplicado ahora a la ejecución.

## 4. Selección y uso de herramientas por el agente

Un agente puede tener acceso a herramientas como búsqueda en el repositorio, edición de archivos, terminal, o servidores MCP externos. El equipo debe decidir explícitamente qué herramientas están disponibles para cada contexto de trabajo, en línea con el principio de mínimo privilegio.

## 5. Model Context Protocol (MCP)

MCP es un **estándar abierto** para conectar asistentes de IA con herramientas y fuentes de contexto externas (repositorios, sistemas de gestión, bases de datos, documentación, automatización de navegador, etc.) de forma interoperable, sin que cada integración requiera código a medida.

## 6. GitHub MCP Server

Permite que un agente interactúe con repositorios, issues y pull requests de GitHub como parte de su flujo de trabajo (por ejemplo, consultar el estado de un PR o crear un issue), en lugar de que la persona tenga que hacerlo manualmente fuera del editor.

## 7. Otras integraciones conceptuales

Según disponibilidad y políticas de la organización, MCP puede conectar con documentación interna, sistemas de gestión de proyectos, bases de datos o automatización de navegador. La decisión de habilitar cada integración depende de riesgo, sensibilidad de los datos y valor real para el flujo de trabajo.

## 8. Permisos, secrets y mínimo privilegio

- Los servidores/herramientas MCP deben configurarse con el **mínimo alcance necesario** (allowlists de operaciones, no acceso de escritura si solo se necesita lectura).
- Las credenciales de los servidores MCP se gestionan como cualquier secreto de la organización: nunca hardcodeadas ni expuestas en el contexto del modelo.
- **Human-in-the-loop:** operaciones de alto impacto (escritura en producción, borrado, push, cambios sobre sistemas compartidos) requieren confirmación humana explícita.

## 9. Cuándo NO utilizar un agente

Un agente no es apropiado cuando:

- La tarea es ambigua y no se resolvió la ambigüedad primero (volver al Módulo 3).
- Las consecuencias de un error son difíciles de revertir y no hay forma de verificar el resultado antes de aplicarlo.
- No existe forma de acotar el alcance de lo que el agente puede tocar (archivos, sistemas, credenciales).

En esos casos, se reduce el alcance de la delegación o se vuelve a un flujo de chat/respuesta puntual con más supervisión.

**PROPUESTA DE FORMACIÓN**

# **GitHub Copilot** **Engineering Practices**

*Desarrollo de software asistido por IA, basado en especificaciones,*  
*contexto, agentes, observabilidad, calidad y gobernanza*

| Preparado para | \[Nombre del cliente\] |
| :---- | :---- |
| **Preparado por** | Novacomp |
| **Duración propuesta** | 20 horas |
| **Modalidad** | Presencial, virtual o híbrida |
| **Estado** | Versión para revisión |

Septiembre 2026

# **1\. Resumen ejecutivo**

La presente propuesta plantea una formación de nivel intermedio-avanzado para equipos de desarrollo que ya utilizan GitHub Copilot y requieren evolucionar desde un uso centrado principalmente en generación y asistencia de código hacia un modelo de ingeniería de software asistida por IA más estructurado, trazable, seguro y medible.

El programa integra prácticas de Context Engineering, personalización de GitHub Copilot, Spec-Driven Development con GitHub Spec Kit, desarrollo agéntico, Model Context Protocol (MCP), testing y code review asistidos por IA, seguridad y gobernanza, así como observabilidad tanto del uso de Copilot como de su impacto sobre el flujo de entrega de software.

| Enfoque de la formación El objetivo no es enseñar a “usar Copilot”, sino establecer prácticas para incorporarlo profesionalmente dentro del ciclo de vida de desarrollo de software (SDLC), conservando control humano, estándares técnicos y mecanismos de evaluación. |
| :---- |

# **2\. Justificación y oportunidad**

Cuando una organización ya ha alcanzado una adopción sostenida de GitHub Copilot, el siguiente nivel de madurez no consiste en aumentar el número de prompts o sugerencias aceptadas, sino en mejorar la calidad del contexto, estandarizar la forma de delegar trabajo a la IA, vincular requisitos con implementación y medir el efecto real sobre la ingeniería.

* Reducir la variabilidad en los resultados generados por IA mediante contexto, instrucciones y estándares compartidos.  
* Pasar de interacciones aisladas a flujos reproducibles de especificación, planificación, implementación y validación.  
* Incorporar capacidades agénticas y herramientas externas de forma controlada mediante MCP.  
* Fortalecer calidad, testing, seguridad y revisión humana del código generado o modificado con IA.  
* Medir adopción, actividad e impacto sin confundir volumen de uso con mejora real de productividad o calidad.

# **3\. Objetivo general**

Fortalecer las capacidades del equipo de desarrollo para utilizar GitHub Copilot como parte integral del SDLC, aplicando prácticas avanzadas de contexto, especificaciones, agentes, calidad, seguridad, observabilidad y gobernanza, con énfasis en resultados reproducibles y alineados con los estándares de ingeniería de la organización.

# **4\. Objetivos específicos**

* Diseñar y mantener contexto persistente para GitHub Copilot mediante instrucciones de repositorio, instrucciones específicas por ruta, archivos de agentes y prompts reutilizables.  
* Aplicar Spec-Driven Development para transformar necesidades de negocio en especificaciones, planes técnicos, tareas e implementación verificable.  
* Utilizar capacidades agénticas de Copilot de forma controlada, incluyendo selección de herramientas, delegación de tareas y verificación de resultados.  
* Extender el contexto y las herramientas disponibles a Copilot mediante MCP, aplicando principios de mínimo privilegio y control de acceso.  
* Aplicar IA a testing y code review sin sustituir el criterio técnico ni los controles de calidad.  
* Incorporar consideraciones de seguridad, gobernanza y uso responsable dentro del flujo de desarrollo asistido por IA.  
* Interpretar métricas de uso de Copilot y relacionarlas con métricas de ingeniería para evaluar impacto y oportunidades de mejora.

# **5\. Perfil de participantes y prerrequisitos**

La formación está diseñada para desarrolladores, líderes técnicos, arquitectos, DevOps/DevSecOps, QA automation y otros perfiles involucrados directamente en el ciclo de entrega de software.

**Prerrequisitos recomendados**

* Experiencia previa utilizando GitHub Copilot en actividades de desarrollo.  
* Conocimiento práctico de Git, pull requests y flujos de trabajo con repositorios.  
* Experiencia de desarrollo en al menos un stack tecnológico utilizado por la organización.  
* Acceso a un entorno de laboratorio con GitHub Copilot habilitado y permisos suficientes para las prácticas acordadas.

# **6\. Metodología**

El programa seguirá un enfoque práctico y progresivo. Cada concepto será vinculado con un escenario de ingeniería y aplicado sobre un repositorio de referencia o, cuando sea viable, sobre un proyecto representativo del cliente.

| Componente | Aplicación |
| :---- | :---- |
| **Concepto breve** | principios, riesgos, criterios de decisión y capacidades relevantes. |
| **Demostración guiada** | aplicación del concepto con GitHub Copilot y herramientas complementarias. |
| **Laboratorio** | ejercicio práctico ejecutado por los participantes. |
| **Discusión técnica** | comparación de alternativas, límites y decisiones arquitectónicas. |
| **Validación** | revisión del resultado y de los controles utilizados para verificarlo. |

# **7\. Estructura del curso**

| Módulo | Tema | Horas | Resultado principal |
| ----- | :---- | ----- | ----- |
| 1 | Copilot avanzado y Context Engineering | 2 | Construir contexto útil y persistente para el equipo. |
| 2 | Instrucciones, prompts reutilizables y agentes | 2 | Estandarizar comportamiento y tareas recurrentes. |
| 3 | Spec-Driven Development con GitHub Spec Kit | 3 | Convertir requisitos en especificaciones y trabajo ejecutable. |
| 4 | Agentic Development y MCP | 3 | Delegar tareas y conectar herramientas de forma controlada. |
| 5 | Testing y Code Review asistidos por IA | 2 | Elevar calidad y capacidad de verificación. |
| 6 | Seguridad y gobernanza | 2 | Establecer controles para desarrollo asistido por IA. |
| 7 | Observabilidad y métricas | 2 | Medir adopción e impacto sobre el delivery. |
| 8 | Laboratorio integrador end-to-end | 4 | Aplicar el flujo completo en una funcionalidad realista. |
| **TOTAL** |  |  | **20 horas** |

La duración podrá ajustarse de acuerdo con el nivel de profundidad requerido, el stack del cliente y el alcance de los laboratorios. La recomendación base es mantener las 20 horas para preservar el componente práctico y el laboratorio integrador.

# **8\. Contenido detallado**

## **Módulo 1\. Copilot avanzado y Context Engineering (2 h)**

**Propósito:** Evolucionar del prompt aislado hacia la construcción deliberada de contexto técnico que permita respuestas más consistentes, relevantes y alineadas con la arquitectura del proyecto.

**Contenidos principales**

* Del Prompt Engineering al Context Engineering: qué cambia y por qué.  
* Cómo Copilot utiliza el contexto del repositorio y del entorno de trabajo.  
* Qué información debe persistir: arquitectura, convenciones, restricciones, patrones, Definition of Done y estándares de testing.  
* Diseño de contexto mínimo, relevante y mantenible; riesgos de sobrecarga de instrucciones.  
* Separación entre contexto global, contexto por dominio y contexto específico de una tarea.

**Aplicación práctica:** Diseño del “AI Development Context” de un proyecto: arquitectura, estándares y criterios que deben guiar a Copilot.

## **Módulo 2\. Instrucciones, prompts reutilizables y agentes (2 h)**

**Propósito:** Estandarizar la interacción del equipo con Copilot mediante artefactos versionados y reutilizables que reduzcan variabilidad y hagan explícitas las reglas de ingeniería.

**Contenidos principales**

* Instrucciones de repositorio con \`.github/copilot-instructions.md\`.  
* Instrucciones específicas por ruta mediante \`.github/instructions/\*.instructions.md\`.  
* Uso de \`AGENTS.md\` y otras instrucciones orientadas a agentes cuando la superficie utilizada las soporte.  
* Prompt files reutilizables en \`.github/prompts/\*.prompt.md\`.  
* Diseño de instrucciones efectivas: concisión, alcance, verificabilidad y prevención de conflictos.  
* Patrones de prompts para análisis, refactorización, pruebas, documentación y revisión.

**Aplicación práctica:** Construcción de un paquete de instrucciones y prompts reutilizables para un repositorio de referencia.

## **Módulo 3\. Spec-Driven Development con GitHub Spec Kit (3 h)**

**Propósito:** Aplicar un flujo basado en especificaciones para mejorar trazabilidad, claridad y control antes de delegar la implementación a un asistente o agente de IA.

**Contenidos principales**

* Fundamentos de Spec-Driven Development y diferencias frente a “prompt-to-code”.  
* Introducción a GitHub Spec Kit y al CLI \`specify\`.  
* Constitución del proyecto: principios y reglas que gobiernan las decisiones posteriores.  
* Definición de la especificación: necesidades, alcance, historias y criterios de aceptación.  
* Clarificación de ambigüedades antes de diseñar la solución.  
* Plan técnico: arquitectura, stack, restricciones y decisiones de implementación.  
* Descomposición en tareas ejecutables y dependencias.  
* Análisis de consistencia entre especificación, plan y tareas.  
* Implementación guiada y convergencia contra lo especificado.  
* Aplicación en escenarios greenfield y brownfield.

**Aplicación práctica:** Partir de una necesidad funcional y recorrer constitution → specify → clarify → plan → tasks/analyze → implement, revisando los artefactos generados antes de ejecutar código.

## **Módulo 4\. Agentic Development y Model Context Protocol (MCP) (3 h)**

**Propósito:** Comprender cuándo delegar trabajo a agentes de Copilot y cómo extender sus capacidades con herramientas externas sin perder control, trazabilidad ni seguridad.

**Contenidos principales**

* Evolución de completions y chat hacia agentic development.  
* Diferencia entre solicitar una respuesta y delegar una tarea multi-step.  
* Patrón Plan → Execute → Verify para trabajo agéntico.  
* Selección y uso de herramientas por el agente.  
* Introducción a Model Context Protocol (MCP) como estándar para conectar herramientas y fuentes de contexto.  
* GitHub MCP Server y casos de uso con repositorios, issues y pull requests.  
* Integración conceptual con documentación, sistemas de gestión, bases de datos o automatización de navegador según disponibilidad.  
* Permisos, secrets, allowlists, mínimo privilegio y human-in-the-loop.  
* Cuándo NO utilizar un agente y cómo acotar el radio de acción.

**Aplicación práctica:** Resolver una tarea multiarchivo utilizando agent mode y, cuando el entorno lo permita, consultar o ejecutar una herramienta mediante MCP.

## **Módulo 5\. Testing y Code Review asistidos por IA (2 h)**

**Propósito:** Utilizar IA como mecanismo de ampliación del criterio de calidad, evitando confundir mayor volumen de tests o sugerencias con software correctamente validado.

**Contenidos principales**

* De criterios de aceptación a escenarios y casos de prueba.  
* Generación asistida de unit, integration y contract tests según el stack.  
* Identificación de edge cases, condiciones negativas y errores no cubiertos.  
* Mocks, fixtures y datos de prueba: beneficios y riesgos.  
* Uso de Copilot para revisión de pull requests y análisis de cambios.  
* Checklists de revisión: arquitectura, SOLID, seguridad, rendimiento, errores, mantenibilidad y observabilidad.  
* Comparación entre revisión automatizada y revisión humana.

**Aplicación práctica:** Analizar un Pull Request con fallas deliberadas y comparar hallazgos de Copilot, herramientas automáticas y revisión humana.

## **Módulo 6\. Seguridad, gobernanza y uso responsable (2 h)**

**Propósito:** Definir controles mínimos para que el uso de Copilot y de capacidades agénticas sea compatible con los requisitos de seguridad, privacidad y gobierno de la organización.

**Contenidos principales**

* Código generado por IA como código no confiable hasta ser verificado.  
* Gestión de secretos, credenciales y datos sensibles.  
* Dependencias, paquetes inexistentes y riesgos de supply chain.  
* Validación de entradas, autenticación, autorización y manejo seguro de errores.  
* Permisos de agentes y servidores MCP; minimización del alcance.  
* Separación de responsabilidades: Generate ≠ Validate ≠ Approve.  
* Controles humanos, políticas de repositorio y criterios para uso responsable.  
* Trazabilidad y documentación de decisiones asistidas por IA.

**Aplicación práctica:** Construcción de un checklist de gobernanza y seguridad para incorporar a la Definition of Done y a las instrucciones del repositorio.

## **Módulo 7\. Observabilidad y métricas (2 h)**

**Propósito:** Evaluar tanto la adopción de Copilot como su efecto sobre el delivery, evitando medir éxito únicamente por actividad o cantidad de código generado.

**Contenidos principales**

* Observabilidad del uso de Copilot: adopción, engagement, actividad y generación de código.  
* Métricas disponibles a nivel de organización/empresa mediante dashboards y APIs, según licenciamiento y permisos.  
* Dimensiones de análisis: feature, IDE, lenguaje, modelo, usuario y repositorio cuando estén disponibles.  
* Métricas del ciclo de pull requests y su lectura dentro del flujo de entrega.  
* Correlación con métricas de ingeniería: lead time, cycle time, throughput, time-to-merge, defectos, rework y change failure rate.  
* Diseño de un cuadro de mando para separar adopción, productividad, calidad y riesgo.  
* Observability by Design en el software producido: logging estructurado, métricas, trazas, correlation IDs, OpenTelemetry, health checks y SLI/SLO como parte de la especificación.

**Aplicación práctica:** Definir un conjunto mínimo de KPIs para evaluar el programa de Copilot y agregar requisitos de observabilidad a una especificación de software.

## **Módulo 8\. Laboratorio integrador end-to-end (4 h)**

**Propósito:** Consolidar los aprendizajes ejecutando un flujo completo sobre una funcionalidad realista, desde el requisito hasta el Pull Request y la evaluación de métricas y controles.

**Contenidos principales**

* Definición del requerimiento y criterios de aceptación.  
* Creación o actualización de contexto e instrucciones del repositorio.  
* Especificación y planificación con GitHub Spec Kit.  
* Descomposición del trabajo y delegación controlada al agente.  
* Implementación de la funcionalidad.  
* Generación y revisión de pruebas.  
* Validaciones de seguridad y observabilidad.  
* Creación/revisión del Pull Request.  
* Retrospectiva: qué delegó la IA, qué verificó el equipo y qué evidencia quedó disponible.

**Aplicación práctica:** Entrega de una funcionalidad pequeña pero completa aplicando el flujo Requirement → Spec → Plan → Tasks → Implement → Test → Secure → Observe → Review.

# **9\. Flujo integrador propuesto**

El curso utilizará un flujo común para conectar los módulos y evitar que se perciban como capacidades aisladas:

| 1\. Requirement | 2\. Spec Kit | 3\. Context & Instructions | 4\. Agent | 5\. Testing |
| :---: | :---: | :---: | :---: | :---: |
| **6\. Security** | **7\. Observability** | **8\. Pull Request** | **9\. Code Review** | **10\. Metrics & Retrospective** |

# **10\. Entregables y recursos para los participantes**

* Material de referencia utilizado durante la formación.  
* Repositorio o proyecto de laboratorio con ejercicios y ejemplos.  
* Plantilla base de \`.github/copilot-instructions.md\` y ejemplos de instrucciones por ruta.  
* Ejemplos de prompt files reutilizables para tareas de ingeniería.  
* Ejemplo de constitución y flujo de trabajo con GitHub Spec Kit.  
* Checklist de revisión de código asistido por IA.  
* Checklist de seguridad y gobernanza para desarrollo asistido por IA.  
* Propuesta de KPIs para observabilidad y medición de impacto de Copilot.

# **11\. Estrategia de evaluación**

Se recomienda una evaluación principalmente práctica, orientada a evidenciar que los participantes pueden aplicar los conceptos y no solamente reconocerlos.

| Componente | Peso sugerido | Evidencia |
| :---- | :---- | :---- |
| Laboratorios por módulo | 40% | Aplicación correcta de instrucciones, specs, testing, seguridad y métricas. |
| Laboratorio integrador | 50% | Flujo end-to-end con evidencia de verificación y controles. |
| Participación técnica | 10% | Análisis de riesgos, decisiones y discusión de alternativas. |

# **12\. Duración, modalidad y organización sugerida**

| Duración total | 20 horas |
| :---- | :---- |
| **Modalidad** | Presencial, virtual o híbrida |
| **Distribución sugerida** | 5 sesiones de 4 horas o 4 sesiones de 5 horas |
| **Enfoque** | Teórico-práctico, con aproximadamente 60% de aplicación y laboratorio |
| **Tamaño recomendado** | Hasta 20-25 participantes por grupo para facilitar acompañamiento práctico |

# **13\. Requerimientos del cliente para el laboratorio**

* Confirmar edición/plan de GitHub Copilot disponible para los participantes y políticas corporativas aplicables.  
* Definir IDE principal del grupo (por ejemplo, Visual Studio Code, Visual Studio o JetBrains) para adaptar las demostraciones.  
* Proveer o aprobar un repositorio de laboratorio. Se recomienda utilizar un proyecto representativo pero sin información sensible.  
* Confirmar si el uso de MCP está permitido en la organización y qué servidores/herramientas pueden habilitarse.  
* Confirmar permisos disponibles para visualizar métricas de Copilot a nivel de organización o empresa, si se desea realizar el laboratorio con datos reales.  
* Identificar el stack tecnológico predominante para adaptar ejemplos, testing y prácticas de observabilidad.

# **14\. Resultados esperados**

Al finalizar la formación, se espera que los participantes puedan:

* Diseñar contexto e instrucciones para obtener resultados más consistentes de Copilot.  
* Transformar necesidades en especificaciones estructuradas antes de implementar.  
* Delegar tareas a agentes con alcance, herramientas y criterios de verificación definidos.  
* Conectar Copilot con herramientas externas mediante MCP bajo controles adecuados.  
* Utilizar IA para ampliar la cobertura de testing y code review sin reemplazar la revisión humana.  
* Integrar seguridad, gobernanza y observabilidad dentro del flujo de desarrollo asistido por IA.  
* Definir métricas que permitan distinguir adopción de impacto real en la ingeniería.  
* Aplicar un flujo end-to-end repetible y transferible a proyectos reales de la organización.

# **15\. Consideraciones de alcance**

* La propuesta asume que los participantes ya conocen el uso básico de GitHub Copilot; no contempla una introducción extensa a completions, chat o instalación.  
* Las capacidades disponibles pueden variar según plan de GitHub Copilot, IDE, políticas de la organización y permisos del usuario.  
* Los ejemplos de MCP se ajustarán a las herramientas habilitadas por el cliente y no requerirán exposición de credenciales o datos sensibles.  
* La formación se orienta a prácticas de ingeniería y no sustituye las políticas formales de seguridad, privacidad, compliance o arquitectura del cliente.  
* El laboratorio podrá ser adaptado al stack del cliente una vez confirmados tecnologías, restricciones y nivel técnico del grupo.

# **16\. Referencias técnicas**

La estructura propuesta se apoya en capacidades y documentación oficial vigentes de GitHub, particularmente en los siguientes componentes:

* GitHub Spec Kit – Toolkit for Spec-Driven Development: https://github.com/github/spec-kit  
* GitHub Copilot – Custom instructions and prompt files: https://docs.github.com/en/copilot/concepts/prompting/response-customization  
* GitHub Copilot – Model Context Protocol (MCP): https://docs.github.com/en/copilot/concepts/context/mcp  
* GitHub Copilot – Usage metrics: https://docs.github.com/en/copilot/concepts/copilot-usage-metrics/copilot-metrics  
* GitHub REST API – Copilot usage metrics: https://docs.github.com/en/rest/copilot/copilot-usage-metrics

| Propuesta sujeta a ajuste Antes de impartir la formación se recomienda realizar una breve sesión de levantamiento con el cliente para confirmar stack tecnológico, versión/plan de Copilot, IDEs utilizados, políticas corporativas, disponibilidad de métricas y restricciones de MCP. Con esa información se puede adaptar el laboratorio sin alterar los objetivos del programa. |
| :---- |


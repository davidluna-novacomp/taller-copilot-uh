# Teoría — Módulo 7: Observabilidad y métricas

## 1. Dos observabilidades distintas (y complementarias)

Este módulo cubre dos cosas relacionadas pero diferentes:

1. **Observabilidad del uso de Copilot:** adopción, engagement, actividad y generación de código por parte del equipo.
2. **Observabilidad del software producido** (Observability by Design): logging, métricas, trazas y health checks del sistema que se está construyendo, con o sin ayuda de IA.

Confundirlas lleva a errores como "medir la calidad del producto por cuánto código sugiere Copilot" o "medir el uso de Copilot solo con métricas de rendimiento del sistema".

## 2. Observabilidad del uso de Copilot: adopción, engagement y actividad

- **Adopción:** cuántas personas/equipos usan Copilot de las que tienen licencia disponible.
- **Engagement:** con qué frecuencia y en qué contextos se usa (chat, completions, agent mode).
- **Actividad y generación de código:** volumen de sugerencias, aceptación, líneas generadas — útil como señal, pero **no** como medida directa de productividad o calidad.

## 3. Métricas disponibles a nivel de organización/empresa

Según licenciamiento y permisos, existen dashboards y APIs que exponen métricas agregadas de uso de Copilot a nivel de organización o empresa. El acceso a estos datos depende de roles administrativos y de las políticas del cliente (confirmar en sección 13 de la propuesta).

## 4. Dimensiones de análisis

Cuando están disponibles, las métricas pueden segmentarse por: feature (chat, completions, agent), IDE, lenguaje, modelo utilizado, usuario y repositorio. Esta segmentación ayuda a identificar dónde el uso está generando valor real y dónde no.

## 5. Métricas del ciclo de pull requests

Independientemente de Copilot, el ciclo de vida de un PR (tiempo abierto, tiempo hasta primera revisión, tiempo hasta merge, número de iteraciones) es una fuente valiosa de señales sobre el flujo de entrega, y es donde el efecto de la IA en velocidad y calidad se vuelve observable indirectamente.

## 6. Correlación con métricas de ingeniería

Para evaluar impacto real (no solo actividad), se recomienda correlacionar el uso de Copilot con métricas ya establecidas de ingeniería:

- **Lead time / cycle time:** tiempo desde que se define el trabajo hasta que se entrega.
- **Throughput:** cantidad de trabajo entregado en un período.
- **Time-to-merge:** tiempo que toma un PR en integrarse.
- **Defectos y rework:** errores detectados después de la entrega, retrabajo necesario.
- **Change failure rate:** proporción de cambios que causan incidentes o requieren rollback.

**Principio clave:** un aumento de actividad de Copilot que no se correlaciona con mejoras (o al menos estabilidad) en estas métricas es una señal de alerta, no de éxito.

## 7. Diseño de un cuadro de mando

Se recomienda separar explícitamente cuatro categorías para no mezclar señales de distinta naturaleza:

| Categoría | Pregunta que responde | Ejemplo de métrica |
| :---- | :---- | :---- |
| **Adopción** | ¿Se está usando la herramienta? | % de desarrolladores activos con Copilot |
| **Productividad** | ¿Se entrega más rápido sin sacrificar lo demás? | Lead time, throughput |
| **Calidad** | ¿El resultado es igual o mejor? | Defectos post-entrega, cobertura de tests |
| **Riesgo** | ¿Se introdujeron nuevos riesgos? | Hallazgos de seguridad, dependencias no verificadas |

## 8. Observability by Design en el software producido

Además de medir el uso de Copilot, el software que se construye con su ayuda debe incorporar observabilidad desde la especificación (Módulo 3), no como un agregado posterior:

- **Logging estructurado:** eventos con formato consistente y buscable.
- **Métricas:** contadores, duraciones, tasas de error por operación relevante.
- **Trazas y correlation IDs:** seguimiento de una solicitud a través de distintos componentes.
- **OpenTelemetry:** estándar abierto frecuentemente usado para instrumentar logging/métricas/trazas de forma interoperable.
- **Health checks y SLI/SLO:** indicadores de salud del sistema y objetivos de nivel de servicio definidos de antemano.

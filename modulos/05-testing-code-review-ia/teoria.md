# Teoría — Módulo 5: Testing y Code Review asistidos por IA

## 1. De criterios de aceptación a escenarios y casos de prueba

Cada criterio de aceptación de la especificación (Módulo 3) debería poder traducirse en uno o más casos de prueba concretos. Esto conecta directamente el trabajo de este módulo con el flujo de Spec-Driven Development: los tests son la forma de **verificar** lo que se especificó.

## 2. Generación asistida de unit, integration y contract tests

- **Unit tests:** validan una unidad de lógica de forma aislada (ej. `TaskService.create`).
- **Integration tests:** validan la interacción entre componentes reales (ej. endpoint + servicio + persistencia).
- **Contract tests:** validan que una interfaz (API, mensaje, evento) cumple el contrato esperado por quien la consume.

Copilot puede acelerar la escritura de estos tests, pero el criterio de **qué se debe probar** sigue siendo responsabilidad del equipo.

## 3. Identificación de edge cases, condiciones negativas y errores no cubiertos

Un riesgo frecuente es que la IA genere muchos tests del "camino feliz" y pocos de casos límite. Se recomienda pedir explícitamente: valores vacíos/nulos, límites de tamaño, entradas duplicadas, fallos de dependencias externas, condiciones de carrera si aplica.

## 4. Mocks, fixtures y datos de prueba

- **Beneficio:** permiten aislar la unidad bajo prueba y hacer los tests rápidos y deterministas.
- **Riesgo:** un mock mal diseñado puede ocultar comportamiento real (falsos positivos) o volver el test frágil ante refactors legítimos. La IA puede generar mocks demasiado específicos a la implementación actual; conviene revisarlos con ese criterio.

## 5. Uso de Copilot para revisión de pull requests

Copilot puede analizar un diff y señalar posibles problemas (estilo, errores comunes, falta de manejo de errores, código muerto). Es una **primera pasada**, no un reemplazo del revisor humano, especialmente para decisiones de diseño o impacto de negocio.

## 6. Checklists de revisión

Una checklist estructurada ayuda a que tanto Copilot como el revisor humano cubran las mismas dimensiones:

- **Arquitectura:** ¿respeta las capas y convenciones definidas?
- **SOLID:** ¿responsabilidades claras? ¿alto acoplamiento innecesario?
- **Seguridad:** ¿valida entradas? ¿expone datos sensibles?
- **Rendimiento:** ¿operaciones costosas evitables? ¿N+1 queries?
- **Errores:** ¿manejo consistente y centralizado?
- **Mantenibilidad:** ¿nombres claros? ¿complejidad razonable?
- **Observabilidad:** ¿hay logging/métricas mínimas para diagnosticar fallos? (se profundiza en el Módulo 7)

## 7. Revisión automatizada vs. revisión humana

| Dimensión | Fortaleza de la IA | Fortaleza del humano |
| :---- | :---- | :---- |
| Cobertura amplia y rápida de un checklist | Alta | Media |
| Detección de patrones conocidos de errores | Alta | Media |
| Juicio sobre impacto de negocio/arquitectura a largo plazo | Baja/Media | Alta |
| Conocimiento tácito del equipo/organización | Baja | Alta |

La combinación de ambas suele superar a cualquiera de las dos por separado, siempre que la revisión humana se mantenga como la que **aprueba** el cambio (ver Módulo 6, separación Generate ≠ Validate ≠ Approve).

# Proyecto en avance — Módulo 7: Observabilidad de TaskFlow

## Qué se construye en este módulo

Observabilidad mínima (logging estructurado + métricas + SLI/SLO) para "crear y listar tareas", más KPIs propios del proyecto/equipo.

## Tareas a entregar

1. Definir tus propios KPIs (adopción, productividad, calidad, riesgo) para tu forma de trabajar con Copilot durante el curso.
2. Agregar requisitos de observabilidad a la especificación de "crear y listar tareas" (Módulo 3), documentando el cambio.
3. Implementar logging estructurado mínimo (evento de intento, éxito y error) con correlation ID en el endpoint `POST /tasks`.
4. Definir un SLI y un SLO simple para al menos un endpoint.

## Checklist de aceptación

- [ ] Existen KPIs propios documentados en las 4 categorías (adopción, productividad, calidad, riesgo).
- [ ] La especificación fue actualizada con requisitos de observabilidad.
- [ ] El endpoint implementado genera logs estructurados verificables (no solo `print`/`console.log` sin estructura).
- [ ] Existe al menos un SLI/SLO definido para el proyecto.

## Conexión con el siguiente módulo

En el Módulo 8 (Laboratorio integrador) se aplicará el flujo completo —incluyendo contexto, especificación, agentes/MCP, testing, seguridad y esta observabilidad— sobre una funcionalidad nueva, de punta a punta.

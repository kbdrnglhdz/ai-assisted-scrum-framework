---
name: sprint_simulation
description: Simulación de un escenario de estrés de 3 días en un Sprint activo, realizando cambios reales en Jira.
---

# Skill: Simulación de Sprint (Stress Test)

Este skill permite simular un escenario de 3 días de alta presión en un sprint activo, generando bloqueos, errores y cambios de prioridad reales en Jira para evaluar la capacidad de respuesta del equipo.

## Requisitos Previos

- El proyecto debe tener un Sprint activo.
- Las historias de usuario deben tener tareas o estados claros (Opcional tu los puedes mover) (TO DO, IN PROGRESS, DONE).

## Flujo de Trabajo

### 1. Preparación
El agente solicita el `project_key`.
- Busca el tablero (board) asociado al proyecto usando `jira_get_agile_boards`.
- Identifica el sprint activo usando `jira_get_sprints_from_board(state='active')`.
- Obtiene las historias del sprint activo usando `jira_get_sprint_issues`.

### 2. Ejecución del Escenario (Batch)

#### Día 1: El Bloqueo Crítico
- Selecciona una historia en estado `IN PROGRESS`.
- Crea un issue de tipo `Blocker` o añade un comentario de bloqueo.
- Cambia el estado de la historia a `Blocked` (si existe la transición) o añade la etiqueta `blocked`.
- Añade un comentario: "⚠️ BLOQUEO: Se ha detectado una dependencia externa no resuelta con el equipo de Infraestructura."

#### Día 2: Deuda Técnica y Bugs
- Selecciona otra historia `IN PROGRESS` o `TO DO`.
- Crea un `Bug` vinculado a esa historia.
- Registra un `worklog` de 4h en una tarea para simular esfuerzo sin avance real.
- Añade un comentario: "🐞 BUG: Se ha encontrado un error crítico en la lógica de integración que requiere atención inmediata."

#### Día 3: Cambio de Prioridad (Scope Creep)
- Toma una historia del `Backlog` (o recientemente añadida) y la mueve al sprint activo.
- Opcionalmente, mueve una historia de `TO DO` de vuelta al `Backlog`.
- Añade un comentario: "📈 REPRIORIZACIÓN: Por petición de Stakeholders, se añade este requerimiento urgente al sprint actual."

### 3. Cierre y Reporte
El agente genera un resumen de todos los cambios realizados (IDs de tickets, comentarios añadidos, nuevos estados).

## Ejemplo de Uso
"Realiza una simulación de estrés de 3 días en el sprint activo del proyecto PROJ."
"Genera bloqueos y cambios reales en Jira para simular un escenario de crisis en el sprint."

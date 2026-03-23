---
name: daily_scrum_report
description: Generación de reportes de Daily Scrum para ver progresos, bloqueos críticos y análisis de riesgo del Sprint Goal.
---

# Skill: Daily Scrum Report

Este skill permite automatizar la generación de reportes diarios para el equipo de Scrum, identificando proactivamente riesgos y bloqueos que podrían impactar el compromiso del Sprint.

## Requisitos Previos

- El proyecto debe tener un Sprint activo en Jira.
- El agente debe tener acceso a las herramientas de `mcp-atlassian` (`jira_search`, `jira_get_sprint_issues`, etc.).

## Flujo de Trabajo

### 1. Descubrimiento de Contexto
- El agente identifica el `project_key`.
- Localiza el tablero (`jira_get_agile_boards`) e el sprint activo (`jira_get_sprints_from_board` con `state='active'`).
- Obtiene los metadatos del sprint (fecha inicio, fecha fin, objetivo).

### 2. Recopilación de Datos
- Lista todos los issues del sprint usando `jira_get_sprint_issues`.
- Para cada issue relevante:
    - Obtiene detalles (`jira_get_issue`).
    - Analiza el historial (`changelog`) si es necesario para ver rotación de estados.
    - Busca etiquetas como `blocked` o estados de flujo que indiquen impedimentos.
    - Revisa los comentarios recientes en busca de palabras clave: "bloqueo", "dependencia", "infraestructura", "externo", "esperando".

### 3. Análisis de Riesgo y Bloqueos
- **Progreso**: Compara el porcentaje de historias en `DONE` frente al tiempo transcurrido del sprint.
- **Bloqueos**:
    - **Internos**: Tareas en `IN PROGRESS` por más de 3 días sin cambios, o con comentarios sobre dudas técnicas.
    - **Externos**: Issues vinculados a otros proyectos o menciones a dependencias externas.
- **Sprint Goal**: Evalúa si el ritmo actual permite completar el objetivo definido en el sprint.

### 4. Generación del Reporte
El agente utiliza el template ubicado en `resources/report_template.md` para completar la información.

### 5. Almacenamiento
El reporte se guarda automáticamente en el directorio `docs/daily/` con el formato de nombre `[# Sprint]-YYYYMMDD.md`.
- Ejemplo: `docs/daily/[Sprint 1]-20260323.md`.

## Ejemplo de Uso
"Genera el reporte de la Daily para el proyecto CRM y dime si el Sprint Goal está en riesgo."
"Haz un análisis de bloqueos internos y externos del sprint actual de e-commerce."

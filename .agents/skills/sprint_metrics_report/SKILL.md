---
name: sprint_metrics_report
description: Genera un reporte de métricas del Sprint (defectos, WIP, Lead Time, Cycle Time) y lo guarda en docs/metrics.
---

# Skill: Sprint Metrics Report

Este skill automatiza la extracción y el cálculo de métricas de rendimiento y calidad para un Sprint activo, permitiendo un análisis basado en datos del flujo de trabajo.

## Requisitos Previos

- El proyecto debe tener un Sprint activo en Jira.
- Acceso a las herramientas de `mcp-atlassian`.

## Flujo de Trabajo

### 1. Contextualización
- Identificar el tablero (`jira_get_agile_boards`) e el sprint activo (`jira_get_sprints_from_board` con `state='active'`).
- Obtener el nombre del Sprint y la fecha actual para el nombrado del archivo.

### 2. Recolección de Datos
- Obtener todos los issues del sprint con `jira_get_sprint_issues`.
- Clasificar los issues en:
    - **Historias**: `issuetype` in ('Story', 'Task').
    - **Defectos**: `issuetype` = 'Bug'.
- Obtener métricas de SLA para cada issue completado (`Done`) usando `jira_get_issue_sla`.

### 3. Cálculo de Métricas
- **Defectos por Sprint**: Conteo total de issues de tipo 'Bug'.
- **Densidad de Defectos**: `Total Bugs` / `Total Stories`.
- **WIP (Work In Progress)**: Conteo de issues en estados que no sean 'To Do' ni 'Done'.
- **Lead Time Promedio**: Promedio del `lead_time` obtenido de `jira_get_issue_sla` para issues en 'Done'.
- **Cycle Time Promedio**: Promedio del `cycle_time` obtenido de `jira_get_issue_sla` para issues en 'Done'.

### 4. Generación y Almacenamiento
- Utilizar `resources/metrics_report_template.md`.
- Guardar el reporte Markdown en `docs/metrics/[# Sprint] - metrics-YYYYMMDD.md`.
- Generar un archivo CSV con el **mismo nombre** que el reporte (`.csv`) en la misma carpeta, formateado para su fácil importación acumulativa en Excel.

## Ejemplo de Uso
"Genera el reporte de métricas para el Sprint 1 del proyecto de Pagos."
"¿Cuál es el Lead Time promedio de este Sprint?"

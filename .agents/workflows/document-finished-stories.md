---
description: Documentar las historias terminadas del Sprint activo en Confluence.
---

Este workflow automatiza la recopilación de historias de usuario terminadas y métricas del Sprint activo para su documentación en Confluence en el espacio KBD.

## Pasos del Workflow

### 1. Identificar el Contexto del Sprint
- Obtener el tablero y el sprint activo usando `jira_get_agile_boards` e `jira_get_sprints_from_board(state='active')`.
- Identificar el ID del Sprint y su nombre.

### 2. Recopilar Historias Terminadas
- Listar todos los issues del sprint con `jira_get_sprint_issues`.
- Filtrar aquellos cuyo estado sea `Done` o equivalente (según el workflow del proyecto).
- Para cada historia terminada, extraer:
    - `key` (ID del ticket)
    - `summary` (Resumen)
    - `description` (Descripción, si es relevante)
    - `resolutiondate` (Fecha de resolución)

### 3. Calcular Métricas de Rendimiento
- Para las historias en `Done`, obtener métricas de SLA usando `jira_get_issue_sla`.
- Calcular:
    - **Total Historias Terminadas**.
    - **Total Bugs Identificados** en el sprint.
    - **Lead Time Promedio** de las historias terminadas.
    - **Cycle Time Promedio** de las historias terminadas.

### 4. Generar Borrador de Documentación
- Crear un archivo Markdown local en `docs/sprints/[Sprint Name] - Documentation Draft.md` con la siguiente estructura:
    - Título: Reporte de Cierre de Sprint - [Nombre del Sprint]
    - Sección de Métricas (Tabla con los cálculos anteriores).
    - Listado de Historias de Usuario Terminadas (ID, Resumen, Enlace a Jira).
    - Resumen de Valor Entregado.

### 5. Revisión del Usuario
- Notificar al usuario con la ruta del archivo generado para su revisión.
- Esperar aprobación o ajustes.

### 6. Publicar en Confluence
- Una vez aprobado, utilizar `confluence_create_page` o `confluence_update_page`:
    - **Space**: 'KBD'
    - **Title**: 'Sprint Documentation - [Nombre del Sprint]'
    - **Content**: El contenido del borrador revisado (convertido a formato compatible).

// turbo
3. Ejecutar la recolección de datos y generación del borrador.

---
name: sprint_creation
description: Creación de un Sprint con historias que cumplen con el DoR (dor-audit-pass).
---

# Skill: Creación de Sprint (Sprint Master)

Este skill permite automatizar la creación de un sprint en Jira utilizando historias de usuario que han pasado satisfactoriamente la auditoría de Definition of Ready (DoR).

## Flujo de Trabajo

### 1. Búsqueda de Historias Listas
Busca en Jira todas las historias que tengan la etiqueta `dor-audit-pass`.
- Utiliza `jira_search` con el JQL: `labels = "dor-audit-pass"`.

### 2. Confirmación del Usuario
Presenta la lista de historias encontradas al usuario y permite que este elija cuáles incluir en el nuevo sprint.
- Muestra el ID y el Resumen (Summary) de cada historia.

### 3. Identificación del Board
Para crear un sprint, se requiere el ID del Tablero (Board).
- Utiliza `jira_get_agile_boards` para identificar el tablero correspondiente al proyecto.

### 4. Creación del Sprint
Solicita al usuario un nombre para el Sprint (ej. "Sprint 1") y utiliza `jira_create_sprint`.
- Parámetros requeridos: `board_id`, `name`, `start_date`, `end_date`.
- Por defecto, sugiere una duración de 2 semanas a partir de la fecha actual.

### 5. Asignación de Historias
Una vez creado el sprint, añade las historias seleccionadas utilizando `jira_add_issues_to_sprint`.

## Ejemplo de Uso
"Crea un sprint con las historias que ya están listas."
"Busca qué historias tienen dor-audit-pass y prepárame un nuevo sprint."

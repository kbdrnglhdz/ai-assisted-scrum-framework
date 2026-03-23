---
name: user_story_audit
description: Auditoría de Historias de Usuario basándose en la Definición de Listo (DoR) e INVEST.
---

# Skill: Auditoría de Historias de Usuario (Audit HU)

Este skill permite realizar una revisión crítica de una Historia de Usuario para asegurar que cumple con los estándares de calidad necesarios antes de entrar a desarrollo.

## Flujo de Trabajo

### 1. Localización de la Historia de Usuario
Para auditar una historia, debes buscarla en el siguiente orden de prioridad:

1.  **Jira (MCP Atlassian)**:
    - Si el usuario proporciona un ID (ej: PROJ-123), utiliza `jira_get_issue`.
    - Si el usuario proporciona palabras clave, utiliza `jira_search` con un JQL adecuado.
2.  **Carpeta Local**:
    - Si no se encuentra en Jira o no hay conexión, busca archivos `.md` en `/home/orangelc/Documents/antigravity/Planificador de tareas personal/user-stories/`.

### 2. Ejecución de la Auditoría (DoR)
Evalúa la historia contra los siguientes criterios (basados en INVEST):

- **[I] Independiente**: ¿Puede ser completada sin depender estrictamente de otras historias en el mismo sprint?
- **[N] Negociable**: ¿Deja espacio para la discusión técnica o está demasiado cerrada?
- **[V] Valiosa**: ¿Es claro el beneficio para el usuario final o el negocio?
- **[E] Estimable**: ¿Tiene suficiente información para que el equipo técnico dé un peso?
- **[S] Small (Pequeña)**: ¿Es lo suficientemente pequeña para terminarse en un solo sprint?
- **[T] Testeable**: ¿Tiene criterios de aceptación claros y verificables en el formato Given-When-Then?

### 3. Generación del Reporte
Presenta los resultados al usuario con el siguiente formato:

```markdown
# Reporte de Auditoría: [ID/Nombre de la HU]

## Resumen Ejecutivo
[Puntaje general o conclusión rápida: LISTA / NO LISTA / PARCIALMENTE LISTA]

## Evaluación INVEST
| Criterio | Estado | Observaciones |
| :--- | :--- | :--- |
| Independiente | [✅/⚠️/❌] | [Comentario] |
| Negociable | [✅/⚠️/❌] | [Comentario] |
| Valiosa | [✅/⚠️/❌] | [Comentario] |
| Estimable | [✅/⚠️/❌] | [Comentario] |
| Pequeña | [✅/⚠️/❌] | [Comentario] |
| Testeable | [✅/⚠️/❌] | [Comentario] |

## Recomendaciones de Mejora
- [Lista de acciones concretas para que la historia cumpla el DoR]
```

### 4. Actualización de Etiquetas en Jira
Si la historia auditada proviene de Jira, **DEBES** actualizar el ticket con la etiqueta correspondiente:
- **dor-audit-pass**: Si el Resumen Ejecutivo es "LISTA".
- **dor-audit-fail**: Si el Resumen Ejecutivo es "NO LISTA" o "PARCIALMENTE LISTA".

Utiliza `jira_update_issue` para añadir la etiqueta sin sobrescribir las existentes.

## Recursos Adicionales
- Plantilla de checklist detallada: `resources/dor_checklist.md`

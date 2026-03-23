---
name: audit_dod
description: Auditoría de la Definición de Terminado (DOD) para Historias de Usuario basándose en descripción, etiquetas y adjuntos.
---

# Skill: Auditoría de Definición de Terminado (Audit DOD)

Este skill permite verificar si una Historia de Usuario (HU) en Jira cumple con los criterios necesarios para ser considerada "Terminada" (Done).

## Flujo de Trabajo

### 1. Obtención de Información de la HU
Utiliza el ID de la historia (ej: PP-123) para obtener todos los detalles necesarios:
- **`jira_get_issue`**: Para la descripción y etiquetas.
- **`jira_get_issue_images`** y **`jira_download_attachments`**: Para buscar evidencia visual o documentos (ej: reportes de cobertura, capturas de pantalla de pruebas).
- **`jira_get_comments`**: Para verificar si hubo una revisión de código (Code Review) o discusiones técnicas.

### 2. Criterios de Auditoría (DOD Standard)
Evalúa los siguientes puntos buscando evidencia en el ticket:

1.  **Criterios de Aceptación (AC)**: ¿Se han cumplido todos los criterios definidos en la HU? (Ver descripción).
2.  **Pruebas Unitarias**: ¿Hay mención de pruebas unitarias o adjuntos con reportes de cobertura (idealmente >80%)?
3.  **Code Review**: ¿Hay comentarios indicando que el código fue revisado o etiquetas como `peer-reviewed`?
4.  **Documentación**: ¿Se ha actualizado la documentación técnica o el manual de usuario (si aplica)?
5.  **Pruebas de Integración/QA**: ¿Hay evidencia de que se probó en un entorno de QA o integración?
6.  **Seguridad**: ¿Se menciona algún escaneo de vulnerabilidades o cumplimiento de estándares de seguridad?

### 3. Generación del Reporte de Auditoría (DOD)
Presenta los resultados al usuario con el siguiente formato:

```markdown
# Reporte de Auditoría DOD: [ID de la HU]

## Estado de Calidad
[ESTADO: CUMPLE / NO CUMPLE / EN PROGRESO]

## Checklist de Verificación
| Criterio | Evidencia Encontrada | Estado |
| :--- | :--- | :--- |
| Criterios de Aceptación | [Breve descripción de la evidencia] | [✅/⚠️/❌] |
| Pruebas Unitarias (>80%) | [Referencia a comentario o adjunto] | [✅/⚠️/❌] |
| Code Review | [Mención de revisores o comentarios] | [✅/⚠️/❌] |
| Documentación | [Link o descripción de actualización] | [✅/⚠️/❌] |
| Pruebas de Integración | [Evidencia de QA] | [✅/⚠️/❌] |
| Seguridad | [Check de seguridad] | [✅/⚠️/❌] |

## Bloqueos o Pendientes
- [Lista de elementos que faltan para cumplir el DOD]

## Veredicto Final
[Recomendación: ¿Debe el Scrum Master/PO aceptar la historia?]
```

### 4. Actualización de Etiquetas en Jira
Una vez finalizada la auditoría, actualiza el ticket en Jira con:
- **`dod-audit-pass`**: Si el estado es "CUMPLE".
- **`dod-audit-fail`**: Si el estado es "NO CUMPLE" o faltan evidencias críticas.

Utiliza `jira_update_issue` para añadir la etiqueta.

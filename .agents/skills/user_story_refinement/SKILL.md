---
name: user_story_refinement
description: Refina una Historia de Usuario para que cumpla con el DoR e INVEST, basándose en la auditoría de user-story-audit.
---

# Skill: Refinamiento de Historias de Usuario (Refine HU)

Este skill permite tomar una Historia de Usuario (HU) existente y mejorarla para que cumpla con los estándares de calidad (INVEST y DoR).

## Flujo de Trabajo

### 1. Localización y Auditoría Inicial
Sigue el mismo proceso que el skill `user_story_audit` para localizar la historia (Jira o Carpeta Local).
Antes de refinar, realiza mentalmente una auditoría INVEST para identificar los puntos débiles (Independence, Negotiable, Valuable, Estimable, Small, Testable).

### 2. Proceso de Refinamiento
Aplica las siguientes mejoras según los hallazgos:

- **Independiente**: Si la historia tiene dependencias fuertes, sugiere dividirla o clarificar las pre-condiciones.
- **Negociable**: Asegúrate de que no contenga detalles de implementación excesivos que limiten la discusión técnica.
- **Valiosa**: Reelabora la descripción para que el beneficio de negocio/usuario sea evidente.
- **Estimable y Pequeña**: Si la historia es muy grande (Epic), sepárala en historias más pequeñas.
- **Testeable**: **OBLIGATORIO** incluir Criterios de Aceptación claros en formato Gherkin (Dado que... Cuando... Entonces...).

### 3. Generación del Archivo de Revisión
Una vez refinada la historia, **DEBES** crear un archivo local para revisión:
- **Ubicación**: `/home/orangelc/Documents/antigravity/Planificador de tareas personal/docs/user-stories/[ID-TICKET]-refined.md`
- **Contenido**: El contenido completo de la historia refinada.

### 4. Presentación de Resultados
Muestra al usuario:
1.  Un resumen de los cambios realizados (qué se mejoró y por qué).
2.  Un bloque de código con la comparativa entre la versión original y la refinada.
3.  El link al nuevo archivo de revisión `[ID-TICKET]-refined.md`.

### 5. Actualización (Bajo Aprobación)
Si el usuario aprueba los cambios tras revisar the archivo, procede a:
- Actualizar el ticket en Jira usando `jira_update_issue`. **DEBES** añadir la etiqueta `refined`.
- O actualizar el archivo local original.


## Recursos Adicionales
- Criterios DoR: `/home/orangelc/Documents/antigravity/Planificador de tareas personal/.agents/skills/user_story_audit/resources/dor_checklist.md`
- Plantillas de Refinamiento: `resources/refinement_templates.md`

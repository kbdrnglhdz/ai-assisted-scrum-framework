# Checklist Detallada: Definición de Terminado (DOD)

Esta checklist sirve como guía interna para el agente durante la ejecución del skill `audit_dod`.

## 1. Funcionalidad y Calidad
- [ ] La funcionalidad implementada coincide con los Criterios de Aceptación.
- [ ] No existen bugs abiertos de severidad Alta o Media vinculados a esta tarea.
- [ ] Se han realizado pruebas de regresión básicas.

## 2. Código y Técnica
- [ ] Pruebas unitarias ejecutadas con éxito (Cobertura mínima recomendada: 80%).
- [ ] El código sigue las guías de estilo del proyecto.
- [ ] Code Review aprobado por al menos un par (evidencia en comentarios o etiquetas).
- [ ] No hay secretos (hardcoded credentials) en el código o en los adjuntos.

## 3. Despliegue y Operaciones
- [ ] La tarea ha sido desplegada en el entorno de Staging/QA.
- [ ] Se ha verificado la integración con componentes dependientes.

## 4. Documentación y Cumplimiento
- [ ] Documentación en el código (Docstrings, Javadoc) actualizada.
- [ ] README o documentación del sistema actualizada si hubo cambios arquitectónicos.
- [ ] Cumplimiento de criterios de accesibilidad (si aplica UI).

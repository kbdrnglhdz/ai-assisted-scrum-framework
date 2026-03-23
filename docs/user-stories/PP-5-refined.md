# Historia de Usuario Refinada: PP-5

**ID Original**: PP-5
**Título Refinado**: Gestión CRUD de Tareas en el Repositorio

## Descripción
**Como** usuario del planificador
**quiero** poder registrar, modificar y eliminar mis tareas
**para** mantener mi lista de pendientes organizada, actualizada y confiable.

---

## Criterios de Aceptación (Gherkin)

### Escenario 1: Registro exitoso de una nueva tarea
- **Dado que** me encuentro en la pantalla principal del repositorio
- **Cuando** ingreso un título de tarea (ej: "Comprar leche") y presiono "Guardar"
- **Entonces** la tarea debe aparecer al inicio de la lista con estado "Pendiente"
- **Y** se debe mostrar un mensaje de confirmación "Tarea guardada exitosamente".

### Escenario 2: Edición del título o descripción de una tarea
- **Dado que** tengo una tarea existente llamada "Proyecto X"
- **Cuando** selecciono la opción "Editar" y cambio el nombre a "Proyecto X - Fase 1"
- **Entonces** el sistema debe actualizar la información en la base de datos
- **Y** la lista de tareas debe reflejar el nuevo nombre inmediatamente.

### Escenario 3: Intento de registro sin título (Validación)
- **Dado que** intento crear una nueva tarea
- **Cuando** dejo el campo "Título" vacío y presiono "Guardar"
- **Entonces** el sistema no debe permitir el registro
- **Y** debe mostrar un error de validación indicando que "El título es obligatorio".

### Escenario 4: Eliminación de una tarea con confirmación
- **Dado que** selecciono una tarea específica para eliminar
- **Cuando** presiono el botón "Eliminar" y confirmo la acción en el modal emergente
- **Entonces** la tarea debe ser removida permanentemente del listado
- **Y** no debe ser recuperable mediante la interfaz estándar.

---

## Notas Técnicas
- **Estado Inicial**: Todas las tareas nuevas deben crearse por defecto con el estado `Pendiente`.
- **Persistencia**: Los cambios deben sincronizarse con el backend (local o API).

## Auditoría INVEST (Post-Refinamiento)
- **I (Independiente)**: ✅
- **N (Negociable)**: ✅ (Criterios claros pero permiten libertad de UI)
- **V (Valiosa)**: ✅
- **E (Estimable)**: ✅ (Los escenarios acotan el esfuerzo)
- **S (Small)**: ✅ (Cubre lo básico de una entidad)
- **T (Testeable)**: ✅ (Escenarios Gherkin listos para automatizar)

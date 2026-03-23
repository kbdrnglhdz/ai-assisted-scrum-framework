# Tareas Técnicas: PP-5 Gestión CRUD de Tareas

Esta es la propuesta de desglose técnico para la historia **PP-5**, utilizando el stack **Java, Spring Boot, Spring Cloud, Flyway, MySQL**.

## 1. Persistencia y Datos

### [DB] Migración Flyway para tabla `tasks`
- **Descripción**: Crear script SQL `V1__create_tasks_table.sql` con los campos: `id` (PK, auto_increment), `title` (VARCHAR(255), NOT NULL), `status` (VARCHAR(50), DEFAULT 'PENDIENTE'), `created_at` (TIMESTAMP), `updated_at` (TIMESTAMP).
- **DoD**: Script ejecutado sin errores y esquema validado en MySQL.

### [MODEL] Entidad Task y Repositorio JPA
- **Descripción**: Crear la entidad `@Entity Task` con sus anotaciones de JPA y la interfaz `TaskRepository` que extienda de `JpaRepository`.
- **DoD**: Entidad mapeada correctamente; el repositorio permite realizar operaciones básicas (save, find, delete).

## 2. Lógica de Negocio

### [SERVICE] Implementación de TaskService
- **Descripción**: Crear `TaskService` e `TaskServiceImpl`. Definir métodos:
    - `saveTask(TaskDTO)`: Debe validar que el título no esté vacío.
    - `updateTask(Long id, TaskDTO)`: Debe verificar que la tarea exista antes de actualizar.
    - `deleteTask(Long id)`: Eliminación por ID.
    - `getTasks()`: Obtener todas las tareas.
- **DoD**: Todos los métodos implementados y probados con JUnit 5/Mockito (cobertura > 80%).

## 3. Capa API (REST)

### [API] REST Controller para Gestión de Tareas
- **Descripción**: Crear `TaskController` con los siguientes mapeos:
    - `POST /api/v1/tasks` (Crear)
    - `GET /api/v1/tasks` (Listar)
    - `PUT /api/v1/tasks/{id}` (Actualizar)
    - `DELETE /api/v1/tasks/{id}` (Eliminar)
- **DoD**: Endpoints funcionales probados con MockMvc. Manejo de excepciones adecuado (404 Not Found, 400 Bad Request).

## 4. Pruebas y Calidad

### [TEST] Pruebas de Integración de Extremo a Extremo
- **Descripción**: Crear `TaskIntegrationTest` usando `@SpringBootTest`.
- **DoD**: El flujo completo de creación, edición y eliminación funciona correctamente interactuando con la base de datos (con H2 o Testcontainers).

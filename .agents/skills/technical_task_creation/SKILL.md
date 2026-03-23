---
name: technical_task_creation
description: Crea las tareas técnicas de una historia de usuario basándose en un stack tecnológico específico.
---

# Skill: Creación de Tareas Técnicas (Technical Tasks)

Este skill permite desglosar una Historia de Usuario (HU) en tareas técnicas concretas necesarias para su implementación, siguiendo un stack tecnológico definido.

## Flujo de Trabajo

### 1. Análisis de la Historia de Usuario
- Lee la historia de usuario, sus criterios de aceptación y cualquier documentación técnica relacionada.
- Identifica los componentes que se verán afectados (Base de datos, API, lógica de negocio, integraciones).

### 2. Selección del Stack Tecnológico
- Por defecto, utiliza el stack definido en `resources/java_spring_stack.md` a menos que el usuario especifique otro.
- El stack incluye: Java, Spring Boot, Spring Cloud, Flyway, MySQL.

### 3. Generación de Tareas Técnicas
Para cada componente identificado en el análisis, genera tareas siguiendo este esquema:

- **Persistencia (MySQL & Flyway)**:
    - Diseño de tablas y relaciones.
    - Creación de scripts de migración Flyway (`V[VERSION]__[NAME].sql`).
- **Capa de Datos (Spring Data JPA)**:
    - Creación/Modificación de Entidades JPA.
    - Creación de Repositorios.
- **Lógica de Negocio (Spring Boot Services)**:
    - Definición de interfaces de servicio.
    - Implementación de la lógica de negocio y validaciones.
- **Comunicación entre Microservicios (Spring Cloud)**:
    - Creación de Clientes Feign o integración con otros servicios.
    - Configuración en Config Server o registro en Discovery Service (Eureka).
- **API (Spring Web / Controllers)**:
    - Creación de DTOs (Request/Response).
    - Implementación de REST Controllers con sus respectivos endpoints y mapeos.
- **Pruebas y Calidad**:
    - Pruebas Unitarias (JUnit 5, Mockito).
    - Pruebas de Integración (MockMvc, Testcontainers).
    - Verificación de cobertura.

### 4. Formato de Salida
Presenta las tareas al usuario en una lista numerada, agrupadas por categorías. Cada tarea debe tener:
1.  **Título conciso**.
2.  **Descripción breve** de lo que se debe hacer.
3.  **Definición de Hecho (DoD)** para esa tarea específica.

### 5. Registro en Jira/Local
- Si el usuario aprueba las tareas, procede a crearlas como sub-tareas en Jira (si aplica) o en el archivo de la historia de usuario local.

## Recursos
- Plantilla Java/Spring: `resources/java_spring_stack.md`

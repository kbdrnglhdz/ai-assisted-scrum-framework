# Template: Java/Spring Technical Stack

Este recurso define las tareas estándar para una implementación utilizando el stack:
- **Lenguaje**: Java 17+
- **Framework**: Spring Boot 3+
- **Cloud**: Spring Cloud (Feign, Eureka, Config)
- **Base de Datos**: MySQL 8
- **Migraciones**: Flyway

## Tareas de Referencia

### [DB] Migración de Base de Datos
- **Acción**: Crear script `V[TIMESTAMP]__descripción.sql` en `src/main/resources/db/migration`.
- **DoD**: El script se ejecuta correctamente y las tablas/columnas coinciden con el diseño.

### [MODEL] Capa de Persistencia
- **Acción**: Crear Entidad `@Entity` y `@Repository` (Spring Data JPA).
- **DoD**: La entidad mapea correctamente a la tabla y los tests de repositorio pasan.

### [SERVICE] Lógica de Negocio
- **Acción**: Implementar `@Service` con las reglas de negocio necesarias.
- **DoD**: Lógica validada mediante pruebas unitarias con Mockito (cobertura > 80%).

### [CLIENT] Integración Cloud (opcional)
- **Acción**: Definir `@FeignClient` para comunicación síncrona o `@StreamListener` para asíncrona.
- **DoD**: El cliente compila y tiene manejo de errores/circuit breaker (Resilience4j).

### [API] Endpoint REST
- **Acción**: Crear `@RestController` y DTOs necesarios.
- **DoD**: Swagger/OpenAPI actualizado y endpoint probado con MockMvc.

### [TEST] Pruebas de Integración
- **Acción**: Crear test de integración completo usando `@SpringBootTest`.
- **DoD**: El flujo de punta a punta (Controller -> Service -> DB) funciona correctamente en un entorno controlado (H2 o Testcontainers).

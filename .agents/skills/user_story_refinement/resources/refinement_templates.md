# Plantillas de Refinamiento de Historias de Usuario

Utiliza estas estructuras para asegurar que la HU refinada sea completa y clara.

---

## Plantilla General (Usuario Final)
**Título**: [Como <perfil>, quiero <funcionalidad>, para <beneficio>]

**Descripción**:
[Contexto breve sobre por qué esta historia es importante y qué problema resuelve.]

**Criterios de Aceptación (Gherkin)**:
- **Escenario 1**: [Título del escenario]
  - **Dado que** [contexto inicial]
  - **Cuando** [acción realizada]
  - **Entonces** [resultado esperado]
- **Escenario 2**: [Título del escenario]
  - **Dado que** [contexto inicial]
  - **Cuando** [acción realizada]
  - **Entonces** [resultado esperado]

**Notas de Diseño / UX**:
- [Referencia a mockups o comportamiento de UI]

**Dependencias**:
- [Lista de tickets relacionados o pre-requisitos técnicos]

---

## Plantilla Técnica / Backend
**Título**: [Implementar <endpoint/servicio/lógica> para <objetivo>]

**Descripción**:
[Detalle técnico de lo que se debe construir, incluyendo contratos de API si aplica.]

**Criterios de Aceptación**:
- **Escenario**: [Validación de éxito]
  - **Dado que** el servicio está activo
  - **Cuando** se recibe una petición [<MÉTODO> <URL>] con [PAYLOAD]
  - **Entonces** se debe retornar un código [Status Code] y el cuerpo [Response Body]
- **Escenario**: [Manejo de errores]
  - **Dado que** [condición de error]
  - **Cuando** se solicita [...]
  - **Then** el sistema debe manejarlo con [...]

**Notas Técnicas**:
- [Tablas de BD afectadas, migraciones, seguridad]

---

## Plantilla de Investigación / Spike
**Título**: [Investigar <tecnología/enfoque> para <decisión>]

**Descripción**:
[El problema que estamos tratando de resolver y por qué necesitamos investigación.]

**Criterios de Aceptación (Definición de Salida)**:
- [ ] Documento con los hallazgos en Confluence/Docs.
- [ ] Recomendación clara de "Go/No-Go" o comparación de alternativas.
- [ ] (Si aplica) Prueba de concepto funcional.

# Día 4: La Calidad como Hábito (DoD y Documentación)

# Sesión 4: Terminando lo Terminado
## De "Copiar y Pegar" a "Auditoría de Evidencias"
**Duración:** 2 Horas
**Facilitador:** Antigravity (Tu Scrum Master AI)

---
# El Problema del "Casi Terminado"
Llega la Sprint Review y el equipo dice: "Está listo, solo falta subirlo". Esa es la mayor mentira de Scrum. El SM suele pasar horas revisando si realmente se cumplió el **DoD**.

> [!CAUTION]
> Una historia sin evidencia de DoD no está terminada; es una "Deuda Técnica" disfrazada.
<!-- slide -->
# El SM "Documentador Manual" (Sin Agente IA)
**¿Cómo pierdes el jueves por la tarde?**
*   **Perseguir la Evidencia:** "¿Dónde está el screenshot de las pruebas?" "¿Subiste el PDF a Jira?"
*   **Redacción de Reportes:** Copiar y pegar el resumen de cada historia terminada en un Word o Confluence.
*   **Criterio Subjetivo:** El SM decide si está "Done" basándose en la buena fe del equipo, no en datos.
*   **Burocracia:** 2 horas llenando la página de Confluence antes de la Review.

### Resultado:
Terminas exhausto y con una Review que no muestra el valor real.
<!-- slide -->
# El SM "Auditor de Calidad" (Con Agente IA)
Delegas la verificación a la skill **`audit_dod`** y el workflow **`/document-finished-stories`**:

1.  **`audit_dod`**: El Agente busca automáticamente evidencias en adjuntos y comentarios. Si no hay pruebas, el ticket no pasa a `Done`.
2.  **Transparencia:** Tú no eres el "malo" que rechaza el ticket; es la regla auditada por la IA.

> [!TIP]
> El SM 2.0 ya no "pregunta" si está hecho, **presenta la prueba** de que está hecho.
<!-- slide -->
# Documentación en Segundos
¿Por qué escribir en Confluence lo que ya está en Jira?

Con el flujo **`/document-finished-stories`**:
*   **Acción:** El Agente recopila métricas, descripciones y resultados del Sprint.
*   **Resultado:** Crea automáticamente la página en **Confluence (Espacio KBD)** con el formato corporativo.

### El Contraste:
De 2 horas de "carpintería" de texto a **1 comando** de ejecución.
<!-- slide -->
# La Sprint Review Estratégica
**Sin IA:** Te enfocas en explicar "qué se hizo".
**Con IA:** 

*   **Enfoque:** El Agente ya documentó el "qué". 
*   **Valor:** El SM usa la Review para hablar del **Impacto de Negocio** y el **Product Goal**.

> [!IMPORTANT]
> Liberas a tu cerebro de la carga de "recordar detalles" para enfocarte en "inspirar a los Stakeholders".
<!-- slide -->
# Práctica: Auditoría de Evidencias
**Tarea 1:** Ejecutar `audit_dod` sobre una historia marcada como terminada.
**Tarea 2:** Identificar qué evidencias faltan según el criterio INVEST.
**Tarea 3:** Ejecutar `/document-finished-stories` y revisar la página generada en Confluence.

**Pregunta para el grupo:**
¿Cómo cambiaría la confianza de tus Stakeholders si cada historia terminada incluyera una auditoría de calidad generada por IA?

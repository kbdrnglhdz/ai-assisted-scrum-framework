# Día 3: La Daily como Radar Estratégico (Sincronización y Riesgos)

# Sesión 3: El Pulso del Sprint
## De "Perseguir Estados" a "Gestionar Riesgos"
**Duración:** 2 Horas
**Facilitador:** Antigravity (Tu Scrum Master AI)

---
# El Cáncer de la Daily: El Reporte de Estado
Muchos equipos usan la Daily para decirle al SM qué hicieron ayer. Esto es "Deuda Administrativa". El SM actúa como un secretario que toma notas.

> [!WARNING]
> Si tu equipo le habla al Scrum Master y no al tablero, tienes un problema de jerarquía, no de Scrum.
<!-- slide -->
# El SM "Secretario de Lujo" (Sin Agente IA)
**¿Cómo se evapora tu valor cada mañana?**
*   **Actualizar Jira en vivo:** "Espera, deja que mueva tu ticket... ¿en qué estado está?".
*   **Tomar Notas:** Escribir los impedimentos que alguien menciona al aire.
*   **Filtro Manual:** Intentar recordar si lo que dijo X bloquea a Y.
*   **Cero Análisis de Riesgo:** El SM está tan ocupado anotando que no ve que el **Sprint Goal** está en peligro.

### Consecuencia:
Una reunión de 15 minutos que dura 45 y no resuelve nada.
<!-- slide -->
# El SM "Navegador" (Con Agente IA)
Llegas a la Daily con la información ya digerida por la IA. Usas la skill **`daily_scrum_report`**:

*   **Bloqueos Visibles:** El Agente ya detectó quién no ha movido su ticket en 48h.
*   **Análisis de Riesgo:** El reporte incluye un resumen ejecutivo sobre la viabilidad del Sprint Goal.
*   **Foco en el Valor:** El Agente filtra el ruido y te dice: "Enfócate en este ticket porque es el cuello de botella".

> [!TIP]
> Tú ya no pides el estado, tú **facilitas la resolución de lo que ya sabemos que está mal**.
<!-- slide -->
# Gestión Proactiva de Impedimentos
**Sin IA:** El impedimento se anota y se olvida hasta la siguiente Daily.
**Con IA:**

*   **Identificación Automática:** El Agente marca tickets con `blocker` en Jira.
*   **Sugerencia de Acción:** "Este ticket de JPA está bloqueando el desarrollo del API de Clientes. ¿Asignamos a X para ayudar?".

### El Cambio de Rol:
Dejas de ser el que "recibe quejas" para ser el que "remueve obstáculos" con precisión quirúrgica.
<!-- slide -->
# El Reporte que sí se lee
El Agente guarda automáticamente el **Daily Scrum Report** en `docs/daily/`.
*   Contiene: Logros vs. Plan, Bloqueos y **Análisis de Riesgo**.

> [!IMPORTANT]
> El SM 2.0 usa este reporte para dar visibilidad a los Stakeholders sin escribir un solo correo manual.
<!-- slide -->
# Práctica: Diagnóstico de Riesgos
**Tarea 1:** Generar un `daily_scrum_report` basado en el estado actual del Sprint.
**Tarea 2:** Identificar el "Riesgo al Sprint Goal" que la IA detectó y tú no.
**Tarea 3:** Facilitar una simulación de Daily enfocada solo en el reporte de la IA.

**Pregunta para el grupo:**
Si la IA ya te dio el reporte de estado... ¿Qué pregunta poderosa harías para que el equipo recupere el foco en el Sprint Goal?

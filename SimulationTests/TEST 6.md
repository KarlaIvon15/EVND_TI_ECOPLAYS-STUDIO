## TEST 6 — Trigger bitácora

- **Nombre:** Auditoría de cambios
- **Descripción:** Actualiza un jugador y verifica el trigger.
- **Objetivo:** Validar que el trigger registre en bitácora.
  
**Consulta:**
  
UPDATE jugadores SET nickname = 'TestCambio' WHERE id_jugador = 1;

**Criterios de aprobación:**

* Se inserta registro en `bitacora`
* Guarda operación UPDATE

- **Estatus:** Aprobado 
- **Evidencia:** Registro en bitácora

  ![Evidencia Test 6](TEST/TEST%206.png)
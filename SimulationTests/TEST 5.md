## TEST 5 — Inserción de sesión con visualización

- **Nombre:** Registro de partida
- **Descripción:** Inserta una nueva partida y la consulta.
- **Objetivo:** Validar inserción directa en tabla.
  
**Consulta:**
  
INSERT INTO partidas (id_jugador, fecha_inicio, fecha_fin, duracion_segundos, puntos_totales) VALUES (2, NOW(), NOW(), 25, 12);

**Criterios de aprobación:**

* Registro insertado correctamente
* Consulta muestra el último registro

- **Estatus:** Aprobado 
- **Evidencia:** Nueva partida visible

![TEST 5](TEST%205.png)

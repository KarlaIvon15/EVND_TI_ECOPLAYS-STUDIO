## TEST 4 — Jugadores con más de 20 puntos

- **Nombre:** Consulta con agregación
- **Descripción:** Suma los puntos por jugador y filtra los mayores a 20.
- **Objetivo:** Validar uso de GROUP BY y HAVING.
  
**Consulta:**

SELECT id_jugador, SUM(puntos_totales) AS puntos_acumulados FROM partidas GROUP BY id_jugador HAVING puntos_acumulados > 20;

**Criterios de aprobación:**

* Se agrupan correctamente los datos
* Solo aparecen jugadores con más de 20 puntos

- **Estatus:** Aprobado 
- **Evidencia:** Lista filtrada correctamente

![TEST 4](TEST%204.png)

## TEST 3 — Última partida del jugador 2

- **Nombre:** Consulta última partida del jugador 2
- **Descripción:** Obtiene la última partida registrada del jugador.
- **Objetivo:** Validar ordenamiento y filtrado correcto.
  
**Consulta:**
  
SELECT * FROM partidas WHERE id_jugador = 2 ORDER BY fecha_fin DESC LIMIT 1;

**Criterios de aprobación:**

* Retorna solo un registro
* Es la partida más reciente

- **Estatus:** Aprobado 
- **Evidencia:** Registro con fecha más reciente
  
  ![TEST 3](TEST%203.png)

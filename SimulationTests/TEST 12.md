## TEST 12 — CONSULTA COMPLEJA

- **Nombre:** JOIN multitabla
- **Descripción:** Consulta que une varias tablas del sistema.
- **Objetivo:** Validar relaciones entre tablas.
    
  **Consulta:**
  
SELECT j.nickname,p.id_pedido,c.total,t.estado AS estado_transaccion FROM jugadores j JOIN pedido p ON j.id_jugador = p.id_adulto JOIN compras c ON p.id_pedido = c.id_pedido JOIN transaccion t ON c.id_compra = t.id_compra ORDER BY c.total DESC;

**Criterios de aprobación:**

  * Datos coherentes
  * JOIN correcto
  
- **Estatus:** Aprobado
- **Evidencia:** Resultado con múltiples tablas

![Evidencia Test 12](TEST/TEST%2012.png)

## TEST 2 — Compra con error (rollback)

- **Nombre:** Compra inválida con rollback
- **Descripción:** Se intenta realizar una compra con un ID inexistente.
- **Objetivo:** Validar que la transacción haga rollback ante error.
   
 **Consulta:**
  
CALL comprar_producto(999, 'Paypal', 2, 1, NOW());

**Criterios de aprobación:**

- No se insertan datos en ninguna tabla
- Se ejecuta rollback automáticamente
- Se muestra error controlado

- **Estatus:** Aprobado 
- **Evidencia:** No hay registros nuevos en compras

  ![TEST 2](TEST%202.png)

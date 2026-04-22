## TEST 1 — Compra válida de producto

- **Nombre:** Compra válida de producto  
- **Descripción:** Se ejecuta el procedimiento `comprar_producto` con datos existentes para simular una compra real.  
- **Objetivo:** Validar que el procedimiento registre correctamente la compra, detalle y transacción.  

 **Consulta:**
  
  CALL comprar_producto(1, 'Paypal', 2, 2, NOW());

**Criterios de aprobación:**

-  Se inserta un registro en `compras`
-  Se inserta el detalle en `detalle_compra`
-  Se genera una transacción válida
-  No hay errores

- **Estatus:** Aprobado 
- **Evidencia:** Registro exitoso en tablas relacionadas
  
 ![TEST 1](TEST%201.png)

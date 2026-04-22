## Transacciones

Las **transacciones** fueron implementadas en la base de datos de **EcoAventura** para garantizar la integridad y consistencia de los datos durante operaciones críticas, especialmente en procesos relacionados con:

- Registro de compras  
- Generación de pedidos  
- Inserción de detalles de compra  
- Relación entre múltiples tablas  

---

## ¿Por qué se implementaron?

En el sistema existen procesos donde intervienen múltiples tablas al mismo tiempo, por ejemplo:

- compras  
- detalle_compra  
- pedido  
- transaccion  

Si alguna de estas operaciones falla y no se controla, se podrían generar datos inconsistentes como:

- Compras sin productos  
- Pedidos sin relación con compras  
- Registros incompletos  

Por ello, se implementaron **transacciones** para asegurar que todas las operaciones se ejecuten correctamente o no se ejecute ninguna.

---

## Funcionamiento

Las transacciones se aplican principalmente dentro de los procedimientos almacenados:

- `generar_compras`  
- `generar_pedidos`  
- `nueva_compra_con_pedido`  

### Flujo de una transacción

1. **START TRANSACTION**
   - Inicia el proceso de registro

2. **Ejecución de operaciones**
   - Inserción en `pedido`  
   - Inserción en `compras`  
   - Inserción en `detalle_compra`  
   - Relación con productos  

3. **Validación**
   - Se verifica que todas las operaciones se ejecutaron correctamente  

4. **COMMIT**
   - Si todo es correcto → se guardan los cambios  

5. **ROLLBACK**
   - Si ocurre un error → se revierten todos los cambios  

---

## Ejemplo aplicado en EcoAventura

En el procedimiento `generar_compras`:

- Se selecciona un adulto  
- Se genera una compra  
- Se insertan múltiples productos en `detalle_compra`  

 Todo esto ocurre dentro de una transacción.

**Escenario:**

- Si falla la inserción de un producto  
 Se ejecuta **ROLLBACK**  
 No se guarda la compra  

---

En el procedimiento `generar_pedidos`:

- Se crea un pedido  
- Se relaciona con compras  

 También controlado por transacción.

---

En el procedimiento `nueva_compra_con_pedido`:

- Se integran múltiples operaciones:
  - Crear pedido  
  - Registrar compra  
  - Insertar detalles  

 Es el mejor ejemplo de uso de transacciones en el sistema.

---

## Resultado

Gracias a la implementación de transacciones:

- Se evita la existencia de compras sin detalle  
- Se garantiza que pedidos y compras estén correctamente relacionados  
- Se mantiene la integridad de los datos  
- Se asegura consistencia en procesos complejos  

---

## Conclusión

Las transacciones permiten:

- Controlar operaciones críticas del sistema  
- Evitar inconsistencias en la base de datos  
- Garantizar que los datos sean confiables  
- Simular un entorno real de manejo de información  


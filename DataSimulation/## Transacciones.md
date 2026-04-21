## Transacciones

Las **transacciones** fueron implementadas para garantizar la integridad de los datos durante operaciones críticas como:

- Registro de compras  
- Inserción de pedidos  
- Relación entre múltiples tablas  

### Funcionalidad

Permiten que:

- Si una operación falla → se ejecuta un **ROLLBACK**  
- Solo se guarda información completa → **COMMIT**  

### Resultado

Se evita que existan:

- Compras sin detalle  
- Pedidos incompletos  

 Esto garantiza la coherencia e integridad de los datos.

---
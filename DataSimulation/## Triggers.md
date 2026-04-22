## Triggers

En la base de datos de **EcoAventura** se implementaron **36 triggers**, los cuales permiten automatizar procesos y garantizar la integridad de la información en tiempo real.

Cada tabla del sistema (excepto la tabla de bitácora) cuenta con **3 triggers principales**:

- AFTER INSERT  
- AFTER UPDATE  
- AFTER DELETE  

Esto asegura que cualquier cambio en los datos sea controlado y registrado automáticamente.

---

## ¿Por qué se implementaron?

Los triggers fueron diseñados para:

- Mantener consistencia entre tablas relacionadas  
- Registrar automáticamente cambios importantes  
- Evitar errores por omisión de procesos manuales  
- Simular el comportamiento dinámico del videojuego  

---

## Funcionamiento General

Cada tipo de trigger cumple una función específica dentro del sistema:

### AFTER INSERT
**¿Qué hace?**  
Se ejecuta después de insertar un nuevo registro.

**Uso en EcoAventura:**  
- Registrar nuevas acciones del jugador  
- Generar entradas en la bitácora  
- Mantener sincronización entre tablas relacionadas  

**Resultado:**  
Cada nuevo dato queda automáticamente registrado y controlado.

---

### AFTER UPDATE
**¿Qué hace?**  
Se ejecuta después de modificar un registro existente.

**Uso en EcoAventura:**  
- Detectar cambios en datos importantes  
- Actualizar estados (ejemplo: compras, pedidos)  
- Registrar modificaciones en la bitácora  

**Resultado:**  
Se mantiene un seguimiento completo de los cambios realizados.

---

### AFTER DELETE
**¿Qué hace?**  
Se ejecuta después de eliminar un registro.

**Uso en EcoAventura:**  
- Registrar eliminaciones  
- Evitar pérdida de trazabilidad  
- Mantener historial de datos eliminados  

**Resultado:**  
Se conserva evidencia de los datos eliminados mediante la bitácora.

---

## Ejemplo de Aplicación

En una tabla como **compras**:

- AFTER INSERT → Registra una nueva compra en la bitácora  
- AFTER UPDATE → Actualiza cambios en el estado de la compra  
- AFTER DELETE → Guarda el registro eliminado para auditoría  

---

## Relación con la Bitácora

Todos los triggers están conectados con la tabla de **bitácora**, la cual:

- Almacena los cambios realizados  
- Registra tipo de operación (INSERT, UPDATE, DELETE)  
- Guarda información relevante del registro afectado  

Esto permite tener un control completo del sistema.

---

## Conclusión

Los triggers permiten:

- Automatizar procesos sin intervención del usuario  
- Mantener integridad y coherencia de los datos  
- Registrar todos los cambios en tiempo real  
- Simular un sistema dinámico y controlado  

Gracias a la implementación de los **36 triggers**, la base de datos garantiza un manejo seguro, automatizado y confiable de la información.

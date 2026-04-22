## Índices

En la base de datos de **EcoAventura** se implementaron **15 índices optimizados**, diseñados para mejorar el rendimiento de las consultas, reducir tiempos de respuesta y mantener la integridad del sistema.

Durante su implementación, se eliminaron índices redundantes y duplicados, priorizando el uso de **índices compuestos** para optimizar recursos.

---

## Lista de Índices

1. idx_compras_adulto_fecha  
2. idx_detalle_compra  
3. idx_detalle_producto  
4. idx_partidas_jugador  
5. idx_clasificacion_recoleccion  
6. idx_clasificacion_tipo  
7. idx_productos_tipo  
8. idx_basura_tipo  
9. idx_usuarios_correo  
10. idx_jugador_usuario  
11. idx_partida_jugador_fecha  
12. idx_recoleccion_partida  
13. idx_pedido_adulto  
14. idx_transaccion_pedido  
15. idx_compras_pedido  

---

## Descripción de Cada Índice

### 1. idx_compras_adulto_fecha
**¿Por qué se implementó?**  
Para optimizar consultas de compras por usuario y por fecha.

**¿Cómo funciona?**  
Es un índice compuesto sobre (`id_adulto`, `fecha_compra`).

**Resultado:**  
Permite consultas rápidas de historial de compras y reemplaza índices simples redundantes.

---

### 2. idx_detalle_compra
**¿Por qué se implementó?**  
Para acceder rápidamente a los productos dentro de una compra.

**¿Cómo funciona?**  
Indexa la columna `id_compra`.

**Resultado:**  
Mejora la eficiencia al consultar detalles de compra.

---

### 3. idx_detalle_producto
**¿Por qué se implementó?**  
Para facilitar consultas por producto en compras.

**¿Cómo funciona?**  
Indexa la columna `id_producto`.

**Resultado:**  
Optimiza análisis de productos vendidos.

---

### 4. idx_partidas_jugador
**¿Por qué se implementó?**  
Para acelerar consultas de partidas por jugador.

**¿Cómo funciona?**  
Indexa `id_jugador`.

**Resultado:**  
Permite generar rankings y estadísticas rápidamente.

---

### 5. idx_clasificacion_recoleccion
**¿Por qué se implementó?**  
Para mejorar consultas relacionadas con recolección.

**¿Cómo funciona?**  
Indexa `id_recoleccion`.

**Resultado:**  
Acelera análisis de actividad ecológica.

---

### 6. idx_clasificacion_tipo
**¿Por qué se implementó?**  
Para clasificar residuos por tipo de forma eficiente.

**¿Cómo funciona?**  
Indexa `tipo_clasificado`.

**Resultado:**  
Optimiza consultas sobre clasificación de basura.

---

### 7. idx_productos_tipo
**¿Por qué se implementó?**  
Para mejorar el rendimiento en la tienda del juego.

**¿Cómo funciona?**  
Indexa la columna `tipo`.

**Resultado:**  
Permite búsquedas rápidas de productos.

---

### 8. idx_basura_tipo
**¿Por qué se implementó?**  
Para consultas frecuentes sobre tipos de basura.

**¿Cómo funciona?**  
Indexa `id_tipo`.

**Resultado:**  
Mejora la lógica de clasificación dentro del juego.

---

### 9. idx_usuarios_correo
**¿Por qué se implementó?**  
Para optimizar el proceso de autenticación.

**¿Cómo funciona?**  
Indexa el campo `correo`.

**Resultado:**  
Permite búsquedas rápidas en login.

---

### 10. idx_jugador_usuario
**¿Por qué se implementó?**  
Para relacionar usuarios con jugadores.

**¿Cómo funciona?**  
Indexa `id_usuario`.

**Resultado:**  
Facilita consultas entre ambas entidades.

---

### 11. idx_partida_jugador_fecha
**¿Por qué se implementó?**  
Para consultas por sesiones de juego.

**¿Cómo funciona?**  
Índice compuesto (`id_jugador`, `fecha_inicio`).

**Resultado:**  
Optimiza consultas por historial de partidas.

---

### 12. idx_recoleccion_partida
**¿Por qué se implementó?**  
Para vincular recolecciones con partidas.

**¿Cómo funciona?**  
Indexa `id_partida`.

**Resultado:**  
Mejora el rendimiento en mecánicas del juego.

---

### 13. idx_pedido_adulto
**¿Por qué se implementó?**  
Para consultar pedidos por usuario.

**¿Cómo funciona?**  
Indexa `id_adulto`.

**Resultado:**  
Acceso rápido a pedidos realizados.

---

### 14. idx_transaccion_pedido
**¿Por qué se implementó?**  
Para relacionar transacciones con pedidos.

**¿Cómo funciona?**  
Indexa `id_pedido`.

**Resultado:**  
Optimiza consultas financieras.

---

### 15. idx_compras_pedido
**¿Por qué se implementó?**  
Para vincular compras con pedidos.

**¿Cómo funciona?**  
Indexa `id_pedido`.

**Resultado:**  
Permite consultas eficientes del flujo de compra.

---

## Conclusión

Los índices permiten:

- Optimizar el rendimiento de consultas  
- Reducir tiempos de respuesta  
- Mejorar la eficiencia del sistema  
- Soportar grandes volúmenes de datos  

Gracias a la implementación de estos **15 índices optimizados**, la base de datos de mantiene un equilibrio entre rendimiento, eficiencia y escalabilidad, fundamental para un entorno de videojuego dinámico.

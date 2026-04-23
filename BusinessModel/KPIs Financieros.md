Esta estructura permite analizar el comportamiento de compra y calcular los KPIs definidos.

---

##3. KPIs de Monetización

Los siguientes indicadores permiten evaluar el rendimiento financiero, comercial y de uso del videojuego.

---

### KPIs Financieros

#### 1. Ingresos Totales
Mide el total de dinero generado por el videojuego.  
**Fórmula:**  
`SUM(precio)`  
**Fuente:** tabla `compras`  

---

#### 2. Recaudación Mensual
Analiza la evolución de ingresos a lo largo del tiempo.  
**Fórmula:**  
`SUM(precio) GROUP BY MONTH(fecha)`  
**Fuente:** tabla `compras`  

---

#### 3. Ingresos por Método de Pago
Identifica qué métodos de pago son más utilizados.  
**Fórmula:**  
`SUM(precio) GROUP BY metodo_pago`  
**Fuente:** tabla `compras`  

---

#### 4. Producto que Genera Más Dinero
Determina qué producto es más rentable.  
**Fórmula:**  
`SUM(precio) GROUP BY producto ORDER BY DESC`  
**Fuente:** tablas `compras` y `productos`  

---

### KPIs de Ventas

#### 5. Producto Más Vendido
Identifica el contenido más adquirido.  
**Fórmula:**  
`COUNT(producto_id) GROUP BY producto_id`  

---

#### 6. Frecuencia de Compra por Usuario
Mide el promedio de compras por jugador.  
**Fórmula:**  
`COUNT(compras) / COUNT(usuarios)`  

---

#### 7. Top Clientes
Identifica los usuarios con mayor gasto.  
**Fórmula:**  
`SUM(precio) GROUP BY usuario_id ORDER BY DESC`  

---

### KPIs del Juego

#### 8. Jugador con Mayor Puntaje
Identifica al usuario con mejor rendimiento.  
**Fórmula:**  
`MAX(puntaje)`  

---

#### 9. Jugadores por Encima del Promedio
Cantidad de jugadores con rendimiento superior al promedio.  
**Fórmula:**  
`puntaje > AVG(puntaje)`  

---

#### 10. Jugadores Activos
Número de usuarios que interactúan regularmente.  
**Fórmula:**  
`COUNT(DISTINCT usuario_id)`  


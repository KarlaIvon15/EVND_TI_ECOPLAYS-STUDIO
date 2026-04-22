## Funciones

En la base de datos de **EcoAventura** se implementaron **7 funciones**, las cuales encapsulan cálculos clave relacionados con el rendimiento de los jugadores y el análisis del comportamiento dentro del sistema.

### Lista de Funciones

1. eficiencia_jugador  
2. fecha_random  
3. nivel_jugador  
4. promedio_puntos_jugador  
5. total_compras_usuario  
6. total_gastado_usuario  
7. total_puntos_jugador  

---

## Descripción de Cada Función

### 1. eficiencia_jugador
**¿Por qué se implementó?**  
Para medir el desempeño del jugador dentro del videojuego.

**¿Cómo funciona?**  
Calcula la relación entre acciones correctas (por ejemplo, clasificaciones acertadas) y el total de intentos.

**Resultado:**  
Devuelve un valor que representa qué tan eficiente es el jugador.

---

### 2. fecha_random
**¿Por qué se implementó?**  
Para generar datos de prueba más realistas en el sistema.

**¿Cómo funciona?**  
Retorna una fecha aleatoria dentro de un rango determinado.

**Resultado:**  
Permite simular eventos (compras, partidas, etc.) en diferentes momentos del tiempo.

---

### 3. nivel_jugador
**¿Por qué se implementó?**  
Para representar el progreso del jugador en el videojuego.

**¿Cómo funciona?**  
Calcula el nivel en función de los puntos acumulados.

**Resultado:**  
Devuelve el nivel actual del jugador, permitiendo clasificar su avance.

---

### 4. promedio_puntos_jugador
**¿Por qué se implementó?**  
Para analizar el rendimiento promedio de los jugadores.

**¿Cómo funciona?**  
Calcula el promedio de puntos obtenidos en las partidas jugadas.

**Resultado:**  
Permite evaluar la consistencia del jugador.

---

### 5. total_compras_usuario
**¿Por qué se implementó?**  
Para conocer la actividad de compra de cada usuario.

**¿Cómo funciona?**  
Cuenta el número total de compras realizadas por un usuario.

**Resultado:**  
Devuelve la cantidad de compras registradas.

---

### 6. total_gastado_usuario
**¿Por qué se implementó?**  
Para analizar el impacto económico dentro del sistema.

**¿Cómo funciona?**  
Suma el total de dinero gastado por un usuario en compras.

**Resultado:**  
Devuelve el monto total invertido por el usuario.

---

### 7. total_puntos_jugador
**¿Por qué se implementó?**  
Para conocer el rendimiento acumulado del jugador.

**¿Cómo funciona?**  
Suma todos los puntos obtenidos en las partidas.

**Resultado:**  
Devuelve el total de puntos del jugador, útil para rankings.

---

## Conclusión

Las funciones permiten:

- Centralizar cálculos importantes del sistema  
- Facilitar consultas complejas  
- Mejorar la eficiencia y organización del código  
- Obtener métricas en tiempo real del videojuego  

Gracias a estas funciones, la base de datos de no solo almacena información, sino que también proporciona análisis directo del comportamiento de los jugadores y usuarios.

## Consultas SQL
### Consulta 1 — Total de dinero generado

- **Nombre:** Total de dinero generado
- **Descripción:**
- Suma todos los valores de la columna total y devuelve el ingreso global del sistema.
- **Objetivo:** Obtiene la suma total de todos los ingresos registrados en la tabla compras.

 ![Consulta 1](QueriesVies/consulta%201.png)

### Consulta 2 — Producto más vendido

- **Nombre:** Producto más vendido
- **Descripción:** 
- Une detalle_compra con productos.
- Suma las cantidades vendidas por producto.
- Ordena de mayor a menor y obtiene el top 1
- **Objetivo:** Identifica el producto con mayor cantidad de unidades vendidas.

![Consulta 2](QueriesVies/consulta%202.png)

### Consulta 3 — Jugador con más puntos

- **Nombre:** Jugador con más puntos
- **Descripción:** 
- Suma los puntos de cada jugador.
- Ordena de mayor a menor.
- Retorna el jugador con más puntos.
- **Objetivo:**Obtiene el jugador con mayor cantidad de puntos acumulados.

![Consulta 3](QueriesVies/consulta%203.png)
  
### Consulta 4 — Recaudación mensual

- **Nombre:** Recaudación mensual
- **Descripción:** 
- Formatea la fecha en año-mes.
- Agrupa los ingresos por mes.
- Permite análisis de tendencias.
- **Objetivo:** Calcula los ingresos agrupados por mes.

![Consulta 4](QueriesVies/consulta%204.png)

### Consulta 5 — Total de pedidos por adulto

- **Nombre:** Total de pedidos por adulto
- **Descripción:** 
- Relaciona adultos con usuarios.
- Cuenta pedidos por adulto.
- Útil para identificar clientes frecuentes.
- **Objetivo:** Cuenta la cantidad de pedidos realizados por cada usuario adulto.

![Consulta 5](QueriesVies/consulta%205.png)

### Consulta 6 — Ingresos por método de pago

- **Nombre:** Ingresos por método de pago
- **Descripción:** 
- Agrupa por método de pago.
- Suma los montos de cada uno.
- Permite analizar preferencias de pago.
- **Objetivo:** Muestra cuánto dinero se ha generado por cada método de pago.

![Consulta 6](QueriesVies/consulta%206.png)

  ### Consulta 7 — Jugadores arriba del promedio

- **Nombre:** Jugadores arriba del promedio
- **Descripción:** 
- Calcula el promedio de puntos.
- Filtra jugadores con rendimiento superior.
- Usa subconsulta anidada.
- **Objetivo:** Obtiene jugadores cuyos puntos totales superan el promedio general.

![Consulta 7](QueriesVies/consulta%207.png)

  ### Consulta 8 — Subconsulta correlacionada (jugadores activos)

- **Nombre:** Subconsulta correlacionada
- **Descripción:** 
- Cuenta partidas por jugador.
- Filtra jugadores con más de 3 partidas.
- Ejemplo de subconsulta correlacionada.
- **Objetivo:** Obtiene jugadores que han jugado más de 3 partidas.

![Consulta 8](QueriesVies/consulta%208.png)

  ### Consulta 9 — Top clientes

- **Nombre:** Top clientes
- **Descripción:** 
- Suma el gasto total por cliente.
- Ordena de mayor a menor.
- Retorna los 5 mejores clientes.
- **Objetivo:** Muestra los 5 clientes con mayor gasto total.

![Consulta 9](QueriesVies/consulta%209.png)

  ### Consulta 10 — Producto que genera más dinero

- **Nombre:** Producto que genera más dinero
- **Descripción:** 
- Calcula ingresos por producto (cantidad × precio).
- Ordena de mayor a menor.
- Retorna el producto más rentable.
- **Objetivo:** Identifica el producto que más ingresos genera.

![Consulta 10](QueriesVies/consulta%2010.png)

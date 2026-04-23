# EVND_TI_ECOPLAYS-STUDIO 

## ECO PLAYS ESTUDIO - IDENTIDAD GRÁFICA

La identidad gráfica de **ECO PLAYS ESTUDIO** busca transmitir valores de sostenibilidad, educación ambiental, conciencia ecológica e innovación. Cada elemento visual está diseñado para resonar con la audiencia, destacando la importancia del reciclaje y la participación activa de los jugadores en la preservación de nuestro planeta a través de experiencias digitales lúdicas.

|    ![Imagen 1](https://github.com/KarlaIvon15/EVND_TI_ECOPLAYS-STUDIO/blob/main/Presentacion/Logo%20Empresa.png)    |    ![Imagen 2](https://github.com/KarlaIvon15/EVND_TI_ECOPLAYS-STUDIO/blob/main/Presentacion/LogoJuego.png)    |
| :-------------------------------: | :----------------------------------: |
|           Logo Empresa        |          Logo Juego          |

## DESCRIPCIÓN

Se busca implementar una serie de videojuegos educativos que funcionen como herramientas de aprendizaje interactivo. El enfoque principal es la gamificación del reciclaje, permitiendo que los usuarios comprendan el ciclo de vida de los residuos mientras se divierten en mundos diseñados con estética Pixel Art.

## PLANTEAMIENTO DEL PROBLEMA

Actualmente, existe una falta de conciencia y educación práctica sobre la gestión de residuos sólidos en las etapas tempranas del desarrollo. A pesar de la disponibilidad de información teórica, los métodos tradicionales de enseñanza suelen ser pasivos y poco atractivos para las nuevas generaciones. Esto genera una desconexión entre el conocimiento del reciclaje y la ejecución real de hábitos sostenibles, lo que contribuye al incremento de la contaminación ambiental a nivel global.

## PROPUESTA DE SOLUCIÓN

Desarrollar una plataforma de videojuegos educativos bajo el sello de **EcoPlays Estudio**, específicamente el título **EcoAventura**. La solución utiliza la gamificación para transformar el aprendizaje del reciclaje en una experiencia inmersiva y divertida. Mediante mecánicas de simulación y una estética visual atractiva (Pixel Art), los jugadores pueden experimentar las consecuencias de sus acciones ambientales en un entorno controlado, reforzando la retención del conocimiento y fomentando un cambio de comportamiento en el mundo real.

## OBJETIVO GENERAL

Diseñar y desarrollar videojuegos educativos interactivos que promuevan la cultura del reciclaje y la sostenibilidad ambiental, utilizando mecánicas de juego para sensibilizar a la población juvenil sobre el cuidado del medio ambiente.

## OBJETIVOS ESPECÍFICOS

* **Desarrollar** una interfaz intuitiva y atractiva mediante estética Pixel Art que facilite la interacción del usuario con los conceptos de sostenibilidad.
* **Implementar** mecánicas de juego que simulen de forma precisa el proceso de clasificación de residuos (orgánicos, inorgánicos, papel, vidrio, etc.).
* **Evaluar** el nivel de aprendizaje y concienciación adquirido por los usuarios tras interactuar con las dinámicas educativas del estudio.
* **Establecer** un flujo de documentación técnica y gráfica que permita la escalabilidad de futuros proyectos educativos dentro del estudio.
*
## Diagrama Equipo

![Diagrama Ecoaventura](Presentacion/diagrama%20ecoaventura_Mesa%20de%20trabajo%201.png)
El trabajo se desarrolló de manera colaborativa, siguiendo los lineamientos del proyecto integrador del curso y promoviendo la participación activa de todos los integrantes del equipo.

## DIAGRAMA DE GANNT
![Diagrama Gantt](Presentacion/GANTT_Mesa%20de%20trabajo%201.jpg)

### Tabla de colaboradores con enlaces a sus perfiles

| Nombre                          | Rol                          | GitHub |
|---------------------------------|------------------------------|--------|
| Erandy Belen Morales Mendoza    | Gestor de Comunidad   | [@Erandymm](https://github.com/Erandymm) |
| Karla Ivon Vargas Tavera        | Director General / Diseñador Líder   | [@KarlaIvon15](https://github.com/KarlaIvon15) |
| Karol Janeth Gonzalez Vargas    | Director de Arte   | [@Karol-JanethGV](https://github.com/Karol-JanethGV) |
| Avry Salas Hernandez            | Programador Líder   | [@Avryl-Salas](https://github.com/Avryl-Salas) |
| Daniel Gómez Hernández          | Documentación, Logística y Administración   | [@DanielGOMHER](https://github.com/DanielGOMHER) |

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

#### Recaudación Mensual
Analiza la evolución de ingresos a lo largo del tiempo.  
**Fórmula:**  
`SUM(precio) GROUP BY MONTH(fecha)`  
**Fuente:** tabla `compras`  

---

#### Ingresos por Método de Pago
Identifica qué métodos de pago son más utilizados.  
**Fórmula:**  
`SUM(precio) GROUP BY metodo_pago`  
**Fuente:** tabla `compras`  

---

#### Producto que Genera Más Dinero
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

#### Frecuencia de Compra por Usuario
Mide el promedio de compras por jugador.  
**Fórmula:**  
`COUNT(compras) / COUNT(usuarios)`  

---

#### Top Clientes
Identifica los usuarios con mayor gasto.  
**Fórmula:**  
`SUM(precio) GROUP BY usuario_id ORDER BY DESC`  

---

### KPIs del Juego

#### Jugador con Mayor Puntaje
Identifica al usuario con mejor rendimiento.  
**Fórmula:**  
`MAX(puntaje)`  

---

#### Jugadores por Encima del Promedio
Cantidad de jugadores con rendimiento superior al promedio.  
**Fórmula:**  
`puntaje > AVG(puntaje)`  

---

#### Jugadores Activos
Número de usuarios que interactúan regularmente.  
**Fórmula:**  
`COUNT(DISTINCT usuario_id)`  

---
##  Pruebas de Simulación

Se documentan 12 pruebas diseñadas para validar el correcto funcionamiento del sistema de base de datos. Estas pruebas verifican la ejecución de procedimientos almacenados, consultas SQL, triggers, restricciones de integridad y transacciones, asegurando que los datos se gestionen de manera consistente, segura y sin errores ante distintos escenarios (tanto correctos como fallidos).

* [TEST 1](SimulationTests/TEST%201.md)
* [TEST 2](SimulationTests/TEST%202.md)
* [TEST 3](SimulationTests/TEST%203.md)
* [TEST 4](SimulationTests/TEST%204.md)
* [TEST 5](SimulationTests/TEST%205.md)
* [TEST 6](SimulationTests/TEST%206.md)
* [TEST 7](SimulationTests/TEST%207.md)
* [TEST 8](SimulationTests/TEST%208.md)
* [TEST 9](SimulationTests/TEST%209.md)
* [TEST 10](SimulationTests/TEST%2010.md)
* [TEST 11](SimulationTests/TEST%2011.md)
* [TEST 12](SimulationTests/TEST%2012.md)

---
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


# Visualizacion de resultados : Dashboard 

Los KPIs fueron diseñados para facilitar la interpretación de los datos mediante herramientas de visualización como Power BI o Navicat BI, permitiendo la construcción de dashboards claros, dinámicos y útiles para la toma de decisiones.

---

## KPIs Definidos

### KPIs Financieros

#### 1. Ingresos Totales
- **Descripción:** Mide el total de dinero generado por el sistema.
- **Objetivo:** Evaluar el rendimiento económico general.

#### 4. Recaudación Mensual
- **Descripción:** Muestra la evolución de los ingresos mes a mes.
- **Objetivo:** Identificar tendencias de crecimiento o disminución.

#### 6. Ingresos por Método de Pago
- **Descripción:** Analiza qué métodos de pago son más utilizados.
- **Objetivo:** Determinar la preferencia de pago de los usuarios.

#### 10. Producto que Genera Más Dinero
- **Descripción:** Identifica el producto más rentable.
- **Objetivo:** Optimizar estrategias comerciales.

---

### KPIs de Ventas

#### 2. Producto Más Vendido
- **Descripción:** Muestra el producto con mayor número de ventas.
- **Objetivo:** Identificar la demanda del mercado.

#### 9. Top Clientes
- **Descripción:** Identifica los clientes que más ingresos generan.
- **Objetivo:** Detectar clientes valiosos.

#### 5. Pedidos por Adulto
- **Descripción:** Mide la frecuencia de compra de clientes adultos.
- **Objetivo:** Analizar hábitos de consumo.

---

### KPIs del Juego

#### 3. Jugador con Más Puntos
- **Descripción:** Identifica al jugador con mejor rendimiento.
- **Objetivo:** Evaluar desempeño individual.

#### 7. Jugadores Arriba del Promedio
- **Descripción:** Mide cuántos jugadores superan el promedio de puntos.
- **Objetivo:** Analizar el nivel general de desempeño.

#### 8. Jugadores Activos
- **Descripción:** Identifica usuarios que siguen participando activamente.
- **Objetivo:** Medir la actividad y retención.

---

# Uso Responsable de IA Generativa 
En este proyecto se utilizó la Inteligencia Artificial como una herramienta de apoyo para optimizar el desarrollo, mejorar la organización de ideas y facilitar  la generación de contenido. Su uso se realizó de manera responsable, asegurando que todas las aportaciones fueran revisadas, adaptadas y validadas por los integrantes del equipo.

La IA no sustituyó el trabajo humano, sino que funcionó como un complemento para agilizar procesos, resolver dudas técnicas y mejorar la calidad del proyecto. Cada integrante hizo uso consciente de estas herramientas, manteniendo la autoría y comprensión total de los resultados obtenidos.

## Evidencia de uso de IA por integrante

- Integrante 1  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Avryl%20Salas%20Hernández/PROMPTS%20Avryl%20Salas.pdf))

- Integrante 2  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Daniel%20Gómez%20Hernández/PROMPTS%20Daniel%20Gómez.pdf))

- Integrante 3  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Erandy%20Belen%20Morales%20Mendoza/PROMPTS%20Erandy%20Belen%20.pdf))

- Integrante 4  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Karla%20Ivon%20Vargas%20Tavera/PROMPTS%20Karla%20Ivon.pdf))

- Integrante 5  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Karol%20Janeth%20Gónzales%20Vargas/PROMPTS%20Karol%20Janeth.pdf).)

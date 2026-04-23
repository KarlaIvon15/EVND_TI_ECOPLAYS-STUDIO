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
### Tabla de colaboradores con enlaces a sus perfiles

| Nombre                          | Rol                          | GitHub |
|---------------------------------|------------------------------|--------|
| Erandy Belen Morales Mendoza    | Gestor de Comunidad   | [@Erandymm](https://github.com/Erandymm) |
| Karla Ivon Vargas Tavera        | Director General / Diseñador Líder   | [@KarlaIvon15](https://github.com/KarlaIvon15) |
| Karol Janeth Gonzalez Vargas    | Director de Arte   | [@Karol-JanethGV](https://github.com/Karol-JanethGV) |
| Avry Salas Hernandez            | Programador Líder   | [@Avryl-Salas](https://github.com/Avryl-Salas) |
| Daniel Gómez Hernández          | Documentación, Logística y Administración   | [@DanielGOMHER](https://github.com/DanielGOMHER) |

---
# Modelado de Datos y Representación

---

## Modelo Entidad-Relación (MER - Visio)

El Modelo Entidad-Relación (MER) fue diseñado utilizando Microsoft Visio, permitiendo representar de manera conceptual la estructura del sistema del videojuego EcoAventura.

Este modelo identifica las entidades principales del sistema, sus atributos y las relaciones entre ellas, proporcionando una visión clara de cómo interactúan los datos dentro del videojuego.

### Entidades principales identificadas

- Usuarios  
- Jugadores  
- Adultos  
- Productos  
- Compras  
- Detalle_compra  
- Pedido  
- Transacción  
- Partidas  
- Recolección  
- Clasificación  
- Basura  
- Tipos_basura  

Estas entidades reflejan tanto la lógica del juego (partidas, recolección, clasificación) como la lógica de negocio (compras, productos, pagos).

---

### Relaciones relevantes

- Un usuario puede ser jugador o adulto  
- Un adulto puede realizar múltiples compras  
- Una compra se relaciona con un pedido y una transacción  
- Un jugador participa en múltiples partidas  
- Una partida genera múltiples eventos de recolección  
- Cada recolección se clasifica en tipos de basura  

---

### Justificación del MER

El MER permite separar claramente:
- La lógica del videojuego (gamificación)
- La lógica de monetización (compras, pagos)

Esto es fundamental para evitar inconsistencias y garantizar escalabilidad del sistema.

Además, el modelo observado en el diagrama incluye vistas, funciones y triggers, lo que demuestra un diseño avanzado orientado a análisis de datos y automatización.

---

## Modelo Relacional (MR - Navicat)

El Modelo Relacional fue implementado en MySQL utilizando Navicat, traduciendo el MER en tablas estructuradas con claves primarias, foráneas e índices.

De acuerdo con el diccionario de datos generado en Navicat, la base de datos cuenta con:

- **16 tablas**
- **11 vistas**
- **19 funciones almacenadas** 

---

### Estructura del modelo relacional

El sistema se divide en tres módulos principales:

#### Módulo del juego
- Jugadores  
- Partidas  
- Recoleccion  
- Clasificacion  
- Basura  
- Tipos_basura  

#### Módulo de monetización
- Productos  
- Compras  
- Detalle_compra  
- Pedido  
- Transaccion  

#### Módulo de usuarios
- Usuarios  
- Adultos  
- Licencia_juego  

---

### Características técnicas

- Uso de claves primarias autoincrementales  
- Integridad referencial mediante claves foráneas  
- Índices para optimización de consultas  
- Triggers para auditoría (bitácora)  
- Funciones para automatización de procesos  

---

### Justificación del MR

El modelo relacional evita redundancias y asegura que cada dato dependa únicamente de su clave primaria.

Además, la inclusión de vistas como:
- Ingresos_mensuales  
- Ranking_jugadores  


---

##  Schema NoSQL (MongoDB)

Como complemento al modelo relacional, se diseñó un esquema NoSQL orientado a análisis y flexibilidad de datos.

Se implementaron tres colecciones clave solicitadas:

---

### Colección: valoraciones

```json
{
  "_id": "val_001",
  "id_usuario": 12,
  "nickname": "EcoPlayer",
  "calificacion": 5,
  "comentario": "El juego es muy educativo y divertido",
  "fecha": "2026-04-19",
  "nivel_alcanzado": 8
}

{
  "_id": "ticket_001",
  "id_usuario": 12,
  "tipo": "soporte",
  "descripcion": "Error al cargar nivel 3",
  "estado": "abierto",
  "prioridad": "media",
  "fecha_creacion": "2026-04-19",
  "fecha_resolucion": null
}
{
  "_id": "promo_001",
  "nombre": "Descuento lanzamiento",
  "descripcion": "20% de descuento en versión completa",
  "tipo": "descuento",
  "valor": 20,
  "fecha_inicio": "2026-04-01",
  "fecha_fin": "2026-04-30",
  "activo": true
} ```


```
# Construcción de la Base de Datos (SQL y NoSQL)

## Descripción General

La construcción de la base de datos para el proyecto **EcoAventura** se desarrolló mediante un enfoque híbrido, integrando tecnologías **SQL (modelo relacional)** y **NoSQL (modelo no relacional)**.  

Esta decisión permite aprovechar las fortalezas de ambos enfoques, garantizando la **integridad**, **escalabilidad** y **flexibilidad** en la gestión de la información del sistema.

---

## Base de Datos Relacional (SQL)

La base de datos relacional fue diseñada para estructurar la información crítica del sistema, asegurando consistencia y control mediante reglas bien definidas.

### Justificación

Se optó por el modelo relacional debido a la necesidad de:

- Mantener la **integridad referencial** entre entidades clave como usuarios, compras, productos y transacciones.
- Garantizar la **consistencia de los datos** mediante restricciones.
- Facilitar consultas complejas mediante el uso de **JOINs** y relaciones estructuradas.

### Implementación 

- Se definieron **tablas estructuradas** con tipos de datos adecuados.
- Se implementaron:
  - **Llaves primarias (PRIMARY KEY)** para identificación única.
  - **Llaves foráneas (FOREIGN KEY)** para mantener relaciones.
- Se añadieron restricciones como:
  - `NOT NULL`
  - `ENUM` para valores controlados (ej. métodos de pago)
- Se desarrollaron **procedimientos almacenados** para automatizar:
  - Generación de compras
  - Registro de partidas

### Beneficios

- Alta confiabilidad en los datos.
- Reducción de redundancia.
- Estructura clara y organizada.

---

## Base de Datos NoSQL

La base de datos NoSQL se implementó para gestionar información flexible y de alto volumen, especialmente aquella que no requiere una estructura rígida.

### Justificación

Se eligió este modelo debido a:

- La necesidad de manejar datos **semi-estructurados o no estructurados**.
- Mejor rendimiento en operaciones de **lectura y escritura masiva**.
- Capacidad de **escalabilidad horizontal**.

### Implementación

- Uso de **colecciones** en lugar de tablas.
- Almacenamiento en formato **documento (JSON)**.
- Aplicado principalmente en:
  - Bitácoras
  - Historial de eventos

### Beneficios

- Flexibilidad en el esquema de datos.
- Mayor velocidad en operaciones específicas.
- Adaptabilidad ante cambios del sistema.

---

## Integración SQL + NoSQL

La integración de ambos modelos permite:

- Utilizar **SQL** para datos estructurados y críticos.
- Utilizar **NoSQL** para datos dinámicos y de gran volumen.

Este enfoque híbrido permite construir un sistema más **robusto, eficiente y escalable**, alineado con las necesidades del proyecto.

---
# Simulación de Datos 

Este documento describe la implementación de los componentes clave de lógica dentro de la base de datos del videojuego educativo **EcoAventura**, cumpliendo con los requerimientos del punto 3 de la rúbrica.

---

## Procedimientos Almacenados

Los **procedimientos almacenados** fueron implementados para simular el comportamiento real dentro del videojuego, automatizando la generación de datos relacionados con:

- Compras realizadas por adultos  
- Partidas jugadas por los jugadores  
- Clasificación de basura dentro del juego  
- Recolección de residuos  
- Registro de usuarios  

### Funcionalidad

Estos procedimientos permiten:

- Generar grandes volúmenes de datos de forma controlada  
- Mantener coherencia lógica entre entidades (usuario → compra → detalle)  
- Simular escenarios reales del videojuego educativo  

### Ejemplo

`generar_compras` asegura que:

- Existe un adulto  
- Se genera una compra válida  
- Se insertan productos relacionados  

Esto cumple con la generación de datos mediante procedimientos garantizando coherencia en el sistema.

---
## Funciones

Las **funciones** fueron diseñadas para encapsular cálculos clave del sistema, principalmente relacionados con:

- Rendimiento del jugador  
- Progreso dentro del videojuego  
- Análisis de compras  

### Funcionalidad

Permiten:

- Reutilizar lógica sin duplicarla  
- Obtener métricas en tiempo real  
- Facilitar consultas más complejas  

### Ejemplo

`nivel_jugador` calcula el progreso del usuario en base a sus puntos.

 Esto aporta:

- Lógica clara  
- Mejor organización del sistema  
- Análisis de datos simulados  

---
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
## Triggers

Los **triggers** fueron implementados para automatizar procesos y mantener consistencia en la base de datos sin intervención manual.

### Uso

Se utilizan para:

- Registrar cambios (bitácora implícita)  
- Mantener sincronización entre tablas  
- Actualizar estados automáticamente  

### Ejemplo

`actualizar_estado_compra`:

- Cambia el estado de una compra dependiendo de su avance  

 Esto aporta:

- Automatización  
- Control del sistema  
- Coherencia en tiempo real  

---
## Índices

Los **índices** fueron implementados mediante:

- Claves primarias  
- Claves foráneas  
- Restricciones únicas  

### Beneficios

Permiten:

- Acceso rápido a los datos  
- Optimización de consultas  
- Integridad referencial entre tablas  

### Ejemplo de relaciones

- `adultos → usuarios`  
- `compras → adultos`  
- `detalle_compra → compras`  

 Esto mejora:

- Rendimiento  
- Consistencia del sistema  

---

## Conclusión

La implementación de procedimientos almacenados, funciones, transacciones, triggers e índices permite simular un entorno real dentro del videojuego **EcoAventura**, asegurando:

- Coherencia lógica  
- Integridad de los datos  
- Automatización de procesos  
- Alto rendimiento en consultas

---

##Modelo de Comercialización - EcoAventura

---

## Contexto del Videojuego

**Nombre:** EcoAventura  

EcoAventura es un videojuego educativo dirigido a niños de entre 6 y 12 años, cuyo objetivo principal es fomentar la conciencia ambiental a través del juego. El jugador se desenvuelve en un entorno urbano representado como un laberinto contaminado, donde deberá recolectar distintos tipos de residuos y clasificarlos correctamente en contenedores de reciclaje.

El videojuego combina mecánicas de exploración, toma de decisiones y aprendizaje interactivo, permitiendo que los usuarios desarrollen habilidades relacionadas con el cuidado del medio ambiente. Además, busca generar un impacto positivo en la educación ambiental desde edades tempranas mediante dinámicas lúdicas y accesibles.

El juego estará disponible principalmente en PC, con posibilidad de expansión a dispositivos móviles. Su diseño está enfocado en ser intuitivo, atractivo y educativo, integrando elementos visuales llamativos y niveles progresivos de dificultad.

---

## Modelo de Negocio

### Tipo de modelo:
**Pago único + Microtransacciones**

---

### Descripción

EcoAventura implementa un modelo híbrido que combina accesibilidad con generación de ingresos sostenibles.

El videojuego contará con un pago único  con el objetivo de atraer una mayor cantidad de jugadores. 

Adicionalmente, se ofrecerá una versión completa mediante un pago único accesible de $130.00 asi como la personalización del personaje  con skins.
---

### Justificación del modelo de monetización

El  pago único fue seleccionado debido a que el videojuego está dirigido a un público infantil, donde es importante garantizar accesibilidad sin comprometer la experiencia del usuario.

Este enfoque equilibra la sostenibilidad económica del proyecto con la responsabilidad educativa del videojuego.

---

### Propuesta de valor

EcoAventura es un videojuego educativo que promueve la conciencia ecológica en niños mediante una experiencia interactiva, combinando entretenimiento y aprendizaje.

---

### Segmento de clientes

- Niños de 6 a 12 años  
- Padres de familia  u Adultos 
- Instituciones educativas  

---

### Canales de distribución

- Plataformas digitales 
- Integración en entornos educativos  

---

### Estrategia de promoción

- Redes sociales  
- Videos demostrativos  
- Campañas educativas  

---

### Fuentes de ingreso

Modelo de pago único: El videojuego se comercializa mediante un pago inicial que otorga acceso completo al contenido base.
Monetización adicional mediante microtransacciones: Se ofrecen compras dentro del juego, principalmente de elementos cosméticos (skins), que permiten la personalización del personaje sin impactar el equilibrio del juego.

---

### Representación en la Base de Datos

El modelo de monetización está respaldado por la estructura de la base de datos, la cual permite gestionar jugadores, productos y transacciones.

**Tablas involucradas:**

- `jugadores`: almacena la información de los jugadores  
- `productos`: contiene los elementos disponibles para compra  
- `compras`: registra las transacciones realizadas  
- `metodos_pago`: define los tipos de pago disponibles  

**Relaciones clave:**

- Un usuario puede realizar múltiples compras  
- Cada compra está asociada a un producto  
- Cada compra utiliza un método de pago  

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
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Karla%20Ivon%20Vargas%20Tavera/PROMPTS%20Karla%20Ivon.pdf)

- Integrante 5  
  [Ver evidencia]([Ver evidencia](Prompting/PROMPTS%20IA/Karol%20Janeth%20Gónzales%20Vargas/PROMPTS%20Karol%20Janeth.pdf)

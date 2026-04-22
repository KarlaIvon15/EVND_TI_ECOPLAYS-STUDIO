# EVND_TI_ECOPLAYS-STUDIO
Es repositorio es un ejemplo de como se estructura la documentacion.

##Diagrama Equipo

![Diagrama Ecoaventura](Presentacion/diagrama%20ecoaventura_Mesa%20de%20trabajo%201.png)

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


# EVND_TI_ECOPLAYS-STUDIO
Es repositorio es un ejemplo de como se estructura la documentacion.

##Diagrama Equipo

![Diagrama Ecoaventura](Presentacion/diagrama%20ecoaventura_Mesa%20de%20trabajo%201.png)

# Modelado de Datos y Representación

---

## 1. Modelo Entidad-Relación (MER - Visio)

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

## 2. Modelo Relacional (MR - Navicat)

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

##  3. Schema NoSQL (MongoDB)

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



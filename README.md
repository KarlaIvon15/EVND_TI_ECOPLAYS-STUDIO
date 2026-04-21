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
}


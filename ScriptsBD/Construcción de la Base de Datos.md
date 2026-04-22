#   Construcción de la Base de Datos (SQL y NoSQL)

## Descripción General

La construcción de la base de datos para el proyecto **EcoAventura** se realizó utilizando un enfoque híbrido, integrando tecnologías **SQL (relacional)** y **NoSQL (no relacional)**. Esta decisión permite aprovechar las fortalezas de ambos modelos para garantizar integridad, escalabilidad y flexibilidad en el manejo de la información.

---

## Base de Datos Relacional (SQL)

La base de datos relacional fue diseñada para estructurar la información crítica del sistema, asegurando consistencia y control mediante reglas bien definidas.

### Justificación

Se utilizó un modelo relacional debido a la necesidad de:

* Mantener **integridad referencial** entre entidades clave como usuarios, compras, productos y transacciones.
* Garantizar la **consistencia de los datos** mediante el uso de restricciones.
* Facilitar consultas complejas mediante **JOINs** y relaciones bien definidas.

###  Implementación

* Se definieron **tablas estructuradas** con tipos de datos adecuados para cada atributo.
* Se implementaron:

  * **Llaves primarias (PRIMARY KEY)** para identificar registros de manera única.
  * **Llaves foráneas (FOREIGN KEY)** para mantener relaciones entre tablas.
* Se añadieron **restricciones** como:

  * `NOT NULL`
  * `ENUM` para valores controlados (ej. métodos de pago)
* Se desarrollaron **procedimientos almacenados** para automatizar procesos como:

  * Generación de compras
  * Registro de partidas

### Beneficios

* Alta confiabilidad en los datos.
* Reducción de redundancia.
* Estructura clara y organizada.

---

## Base de Datos NoSQL

La base de datos NoSQL se implementó para manejar información más flexible y de alto volumen, especialmente aquella que no requiere una estructura rígida.

### Justificación

Se eligió NoSQL debido a:

* La necesidad de almacenar datos **semi-estructurados o no estructurados**.
* Mejor rendimiento en operaciones de **lectura/escritura masiva**.
* Escalabilidad horizontal para futuras expansiones del sistema.

### Implementación

* Uso de **colecciones** en lugar de tablas.
* Almacenamiento de datos en formato tipo **documento (JSON)**.
* Ideal para:

  * Bitácoras
  * Historial de eventos

### Beneficios

* Flexibilidad en el esquema de datos.
* Mayor velocidad en operaciones específicas.
* Adaptabilidad a cambios del sistema sin afectar la estructura general.

---

##  Integración SQL + NoSQL

El uso conjunto de ambas tecnologías permite:

* Utilizar **SQL** para datos críticos y estructurados.
* Utilizar **NoSQL** para datos dinámicos y de gran volumen.

Esto genera un sistema más robusto, eficiente y preparado para escenarios reales, garantizando un sistema sólido, eficiente y escalable, alineado con las necesidades del proyecto.

---

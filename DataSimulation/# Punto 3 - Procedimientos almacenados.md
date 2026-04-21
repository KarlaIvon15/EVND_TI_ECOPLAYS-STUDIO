# Punto 3 - Implementación de Lógica en Base de Datos  

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
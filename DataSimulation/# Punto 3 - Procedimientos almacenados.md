
## Procedimientos Almacenados

En la base de datos se implementaron **12 procedimientos almacenados**, los cuales permiten simular el comportamiento real del videojuego, automatizando procesos clave y garantizando coherencia entre las entidades.

### Lista de Procedimientos:

1. clasificar_basura  
2. comprar_producto  
3. generar_clasificaciones  
4. generar_compras  
5. generar_licencias  
6. generar_partidas  
7. generar_pedidos  
8. generar_recolecciones  
9. nueva_compra_con_pedido  
10. registrar_usuario  
11. test_transaccion  
12. top_jugadores  

---

## Descripción de Cada Procedimiento

### 1. clasificar_basura
**¿Por qué se implementó?**  
Para simular la mecánica principal del juego: la correcta clasificación de residuos.

**¿Cómo funciona?**  
Recibe datos de basura generada y la asigna a una categoría (orgánica, inorgánica, reciclable, etc.).

**Resultado:**  
Se generan registros de clasificación que impactan el desempeño del jugador.

---

### 2. comprar_producto
**¿Por qué se implementó?**  
Para representar el sistema de tienda dentro del videojuego.

**¿Cómo funciona?**  
Registra una compra asociando un adulto, productos y método de pago.

**Resultado:**  
Se crea una compra válida dentro del sistema con su respectivo detalle.

---

### 3. generar_clasificaciones
**¿Por qué se implementó?**  
Para poblar la base de datos con datos de prueba sobre clasificación de basura.

**¿Cómo funciona?**  
Genera múltiples registros de clasificaciones de forma automática.

**Resultado:**  
Simulación de actividad constante de jugadores clasificando residuos.

---

### 4. generar_compras
**¿Por qué se implementó?**  
Para simular el comportamiento de compras dentro del juego.

**¿Cómo funciona?**  
- Selecciona un adulto existente  
- Genera una compra  
- Inserta productos relacionados  

**Resultado:**  
Datos consistentes de compras con relaciones completas.

---

### 5. generar_licencias
**¿Por qué se implementó?**  
Para gestionar el acceso de jugadores al videojuego.

**¿Cómo funciona?**  
Crea licencias vinculadas a jugadores.

**Resultado:**  
Control del acceso y uso del sistema.

---

### 6. generar_partidas
**¿Por qué se implementó?**  
Para simular sesiones de juego.

**¿Cómo funciona?**  
Crea partidas asociadas a jugadores con datos como puntaje o duración.

**Resultado:**  
Historial de partidas para análisis de rendimiento.

---

### 7. generar_pedidos
**¿Por qué se implementó?**  
Para representar solicitudes de compra dentro del sistema.

**¿Cómo funciona?**  
Genera pedidos relacionados con compras.

**Resultado:**  
Simulación del flujo completo de compra (pedido → transacción).

---

### 8. generar_recolecciones
**¿Por qué se implementó?**  
Para modelar la recolección de basura dentro del juego.

**¿Cómo funciona?**  
Genera registros de recolección vinculados a tipos de basura.

**Resultado:**  
Datos que representan la actividad ecológica del jugador.

---

### 9. nueva_compra_con_pedido
**¿Por qué se implementó?**  
Para integrar el proceso completo de compra en un solo procedimiento.

**¿Cómo funciona?**  
Ejecuta múltiples operaciones:
- Genera pedido  
- Registra compra  
- Relaciona productos  

**Resultado:**  
Transacción completa y consistente en una sola ejecución.

---

### 10. registrar_usuario
**¿Por qué se implementó?**  
Para permitir el alta de nuevos usuarios en el sistema.

**¿Cómo funciona?**  
Inserta los datos del usuario validando información básica.

**Resultado:**  
Usuarios correctamente registrados en la base de datos.

---

### 11. test_transaccion
**¿Por qué se implementó?**  
Para validar el correcto funcionamiento de transacciones.

**¿Cómo funciona?**  
Ejecuta operaciones controladas con manejo de errores (rollback en caso necesario).

**Resultado:**  
Garantiza la integridad de los datos.

---

### 12. top_jugadores
**¿Por qué se implementó?**  
Para obtener rankings dentro del juego.

**¿Cómo funciona?**  
Consulta y ordena jugadores según su rendimiento o puntuación.

**Resultado:**  
Listado de los mejores jugadores del sistema.

---

## Conclusión

Nuestros procedimientos almacenados permiten:

- Automatizar procesos clave del videojuego  
- Simular escenarios reales de uso  
- Mantener integridad y coherencia en los datos  
- Generar grandes volúmenes de información para pruebas  


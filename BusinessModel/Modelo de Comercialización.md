#Modelo de Comercialización - EcoAventura

---

## 1. Contexto del Videojuego

**Nombre:** EcoAventura  

EcoAventura es un videojuego educativo dirigido a niños de entre 6 y 12 años, cuyo objetivo principal es fomentar la conciencia ambiental a través del juego. El jugador se desenvuelve en un entorno urbano representado como un laberinto contaminado, donde deberá recolectar distintos tipos de residuos y clasificarlos correctamente en contenedores de reciclaje.

El videojuego combina mecánicas de exploración, toma de decisiones y aprendizaje interactivo, permitiendo que los usuarios desarrollen habilidades relacionadas con el cuidado del medio ambiente. Además, busca generar un impacto positivo en la educación ambiental desde edades tempranas mediante dinámicas lúdicas y accesibles.

El juego estará disponible principalmente en PC, con posibilidad de expansión a dispositivos móviles. Su diseño está enfocado en ser intuitivo, atractivo y educativo, integrando elementos visuales llamativos y niveles progresivos de dificultad.

---

## 2. Modelo de Negocio

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

Modelo de pago único:
El videojuego se comercializa mediante un pago inicial que otorga acceso completo al contenido base.
Monetización adicional mediante microtransacciones:
Se ofrecen compras dentro del juego, principalmente de elementos cosméticos (skins), que permiten la personalización del personaje sin impactar el equilibrio del juego.

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

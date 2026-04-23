# Schema MongoDB – Microtransacciones (EcoAventura)

Este documento define el esquema de validación para la colección `microtransacciones` en MongoDB, utilizado para gestionar las compras dentro del videojuego EcoAventura.

---

## Descripción

El sistema de microtransacciones permite registrar:

- Compras realizadas por los usuarios  
- Productos adquiridos dentro del juego  
- Información de pago (transacciones)  

Este modelo utiliza una estructura NoSQL desnormalizada, donde toda la información se almacena en un solo documento para mejorar el rendimiento.

---

## Estructura del Documento

Cada documento en la colección `microtransacciones` contiene:

- `usuario_id`: ID del usuario  
- `jugador_id`: ID del jugador (opcional)  
- `fecha`: Fecha de la compra  
- `estado`: Estado de la compra  
- `metodo_pago`: Método de pago  
- `total`: Monto total  
- `items`: Lista de productos comprados  
- `transaccion`: Información del pago  

---

## Creación de la Colección con Validación

```js
db.createCollection("microtransacciones", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["usuario_id", "fecha", "total", "estado", "metodo_pago", "items"],
      properties: {

        usuario_id: {
          bsonType: "int",
          description: "ID del usuario que realiza la compra"
        },

        jugador_id: {
          bsonType: "int",
          description: "ID del jugador (opcional)"
        },

        fecha: {
          bsonType: "date",
          description: "Fecha de la transacción"
        },

        estado: {
          enum: ["pendiente", "completado", "cancelado"],
          description: "Estado de la compra"
        },

        metodo_pago: {
          enum: ["tarjeta", "paypal", "google_play", "apple_pay"],
          description: "Método de pago"
        },

        total: {
          bsonType: "double",
          minimum: 0,
          description: "Monto total de la compra"
        },

        items: {
          bsonType: "array",
          minItems: 1,
          items: {
            bsonType: "object",
            required: ["producto_id", "nombre", "cantidad", "precio"],
            properties: {

              producto_id: {
                bsonType: "int"
              },

              nombre: {
                bsonType: "string"
              },

              tipo: {
                enum: ["skin", "moneda", "powerup", "suscripcion"]
              },

              cantidad: {
                bsonType: "int",
                minimum: 1
              },

              precio: {
                bsonType: "double",
                minimum: 0
              },

              subtotal: {
                bsonType: "double",
                minimum: 0
              }
            }
          }
        },

        transaccion: {
          bsonType: "object",
          required: ["estado", "monto"],
          properties: {

            id_transaccion: {
              bsonType: "int"
            },

            estado: {
              enum: ["exitoso", "fallido", "pendiente"]
            },

            monto: {
              bsonType: "double"
            },

            fecha: {
              bsonType: "date"
            }
          }
        }
      }
    }
  }
});
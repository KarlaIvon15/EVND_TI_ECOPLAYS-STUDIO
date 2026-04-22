## TEST 10 — Nickname duplicado

- **Nombre:** Validación de unicidad
- **Descripción:** Inserta nickname repetido.
- **Objetivo:** Validar restricción UNIQUE.
    
  **Consulta:**
  
INSERT INTO jugadores (id_usuario, nickname) VALUES (1, 'RegiTrr21');

**Criterios de aprobación:**

* Error de duplicado
* No inserción

- **Estatus:** Aprobado 
- **Evidencia:** Error SQL

![Evidencia Test 10](TEST/TEST%2010.png)

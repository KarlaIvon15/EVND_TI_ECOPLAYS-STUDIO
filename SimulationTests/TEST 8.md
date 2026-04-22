## TEST 8 — Recolección inválida

- **Nombre:** Error por clave foránea
- **Descripción:** Inserta datos inválidos en recolección.
- **Objetivo:** Validar restricciones FK.
    
  **Consulta:**
  
INSERT INTO recoleccion VALUES (NULL, 1, 99, NOW());

**Criterios de aprobación:**

* Error de integridad
* No se inserta registro

- **Estatus:** Aprobado 
- **Evidencia:** Error SQL

![Evidencia Test 8](TEST/TEST%208.png)
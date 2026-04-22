## TEST 7 — Recolección válida

- **Nombre:** Registro de recolección
- **Descripción:** Inserta una recolección válida.
- **Objetivo:** Validar integridad referencial.
  
  **Consulta:**
  
INSERT INTO recoleccion (id_partida, id_basura, fecha_recoleccion) VALUES (1, 2, NOW());

**Criterios de aprobación:**

* Inserción exitosa
* Datos correctos

- **Estatus:** Aprobado 
- **Evidencia:** Registro visible

![TEST 7](TEST%207.png)

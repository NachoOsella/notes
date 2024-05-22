## [[nivelación/Lab. Computación/Nivelación/Módulo 2|Módulo 2]]
# Formas Normales

La Normalización es el proceso mediante el cual se transforman datos
complejos a un conjunto de estructuras de datos más pequeñas, que
además de ser más simples y estables, son más fáciles de mantener. Es decir, es un proceso de refinamiento de las estructuras de la base de datos para mejorar la velocidad a la que los datos puedan accederse, así como mejorar su integridad.

La Normalización implica los siguientes procesos:

- Debe asegurar que los registros de cada tabla cuentan con un identificador único.
- Debe asegurar que cada campo representa una sola pieza de dato.
- Eliminar información redundante de las tablas. Cada registro de la base de datos deberá contener datos únicos. Cada dato deberá almacenarse en un solo lugar.
- Eliminar los campos de repetición de grupos.
- Debe asegurar que en los campos no se almacenen datos originados por cálculos.
---
# Tipos de Tablas

- **Tablas Maestras o Fijas**
    Aquellas que por su contenido se le realizan operaciones de Altas, Bajas y Modificaciones de sus atributos con muy poca frecuencia. 
    Por ejemplo Tablas de Proveedores, Clientes, Alumnos, Profesores, etc.
    
- **Tablas de Movimientos o Transacciones**
    Las que por su contenido se le agregan permanentemente registros como resultado de las transacciones diarias y que se relacionan con otras tablas como las fijas y auxiliares. 
    Por ejemplo: Facturación, Cobranzas, etc.
    
- **Tablas Auxiliares**
    Son las que por lo general contienen pocos campos y que sirven para evitar redundancia en las tablas Fijas o de Movimientos.
    
- **Tablas Históricas**  
    Contienen backup de datos de las Bases de Datos, estos se realizan en forma periódica, según las características del sistema. 
    Por ejemplo: todos los años se crean históricos de facturación de manera que podamos iniciar el nuevo año con la tabla de facturación vacía.
---
## [[nivelación/Lab. Computación/Nivelación/Módulo 4|Módulo 4]]

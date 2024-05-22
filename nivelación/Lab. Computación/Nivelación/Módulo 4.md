## [[nivelación/Lab. Computación/Nivelación/Módulo 3|Módulo 3]]
# Integridad de Datos

El término integridad de datos se refiere a la corrección, exactitud y coherencia de los datos en una base de datos. Cuando los contenidos de una base de datos se modifican al agregar, eliminar registros o modificar datos, la integridad de los datos almacenados puede verse afectada de muchas maneras diferentes:

- Pueden añadirse datos no válidos a la base de datos, tales como un pedido que especifica un producto no existente.
- Pueden modificarse datos existentes tomando un valor incorrecto, como por ejemplo si se reasigna un vendedor a una oficina no existente.
- Los cambios pueden ser aplicados parcialmente, como por ejemplo si se añade un pedido de un producto sin ajustar la cantidad disponible para vender.
- Los cambios en la base de datos pueden perderse debido a un error del sistema, a un fallo en el suministro de energía o a errores humanos.

---

### Integridad del Dominio

<aside>
💡 La integridad de dominio (o columna) especifica un conjunto de valores de datos que son válidos para una columna y determina si se permiten valores nulos. La integridad de dominio se suele implementar mediante el uso del tipo de datos, el intervalo de los valores posibles permitidos en una columna, etc.

</aside>

### Integridad de Entidad

<aside>
💡 La integridad de entidad (o tabla) requiere que todas las filas de una tabla tengan un identificador exclusivo, conocido como clave principal.

</aside>

### Integridad Referencial

<aside>
💡 La integridad referencial asegura que siempre las relaciones entre los registros de tablas relacionadas sean válidas y que no se eliminen ni modifiquen accidentalmente datos relacionados. Ayuda a garantizar que la información contenida en una tabla se corresponda con la información contenida en la tabla relacionada.

</aside>
---

# Data Manipulation Lenguaje

## 1.0 Introducción

### 1.1 Objetivo de la Unidad
El objetivo de la unidad se centra en brindar las herramientas necesarias para realizar operaciones básicas de manimpulación de datos dentro de una base de datos, usando sentencias de SQL.

### 1.2 Importancia de DML
El DML es una parte fundamental de SQL ya que permite realizar operaciones de inserción, actualización eliminación y consulta de datos en una base de datos.

### 1.3 Principales Sentencias DML
1. `SELECT`: Permite realizar consultas a la base de datos.
2. `INSERT`: Permite agregar nuevos registros a la base de datos.
3. `UPDATE`: Permite actualizar registros existentes en la base de datos.
4. `DELETE`: Permite eliminar registros de la base de datos.

---
## 2.0 Sentencia INSERT
La sentencia `INSERT` es utilizada para agregar nuevos registros a una tabla de la base de datos. Se especifican los valores que se desean insertar en las columnas de la tabla. Se pueden insertar uno o varios registros en una sola sentencia. Cada vez que se quiera agregar un nuevo registro a una tabla, se debe usar la sentencia `INSERT`.
### 2.1 Sintaxis
```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

### 2.2 Ejemplo Práctico
```sql
INSERT INTO clientes (nombre, apellido, edad)
VALUES ('Juan', 'Perez', 35);
```
---
## 3.0 Sentencia UPDATE
La sentencia `UPDATE` es utilizada para modificar los valores de una o varias columnas de uno o varios registros en una tabla de la base de datos. Se especifican las columnas que se desean modificar y los nuevos valores que se desean asignar a esas columnas. Se debe especificar una condición que indique los registros que se desean modificar.

### 3.1 Sintaxis
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
### 3.2 Ejemplo Práctico
```sql
UPDATE clientes
SET edad = 40
WHERE nombre = 'Juan';
```
---
## 4.0 Sentencia DELETE
La sentencia `DELETE` es utilizada para eliminar uno o varios registros de una tabla de la base de datos. Se especifica una condición que indique los registros que se desean eliminar. Si no se especifica una condición, se eliminarán todos los registros de la tabla.

### 4.1 Sintaxis
```sql
DELETE FROM table_name
WHERE condition;
```

### 4.2 Ejemplo Práctico
```sql
DELETE FROM clientes
WHERE nombre = 'Juan';
```
---
## 5.0 Sentencia SELECT
La sentencia `SELECT` es utilizada para recuperar datos de una o mas tablas en la base de datos. Es la sentencia más utilizada en SQL, permite especificar las columnas que se desean recuperar, las tablas de las cuales se desean recuperar los datos y las condiciones que deben cumplir los registros a recuperar. Se emplea para consultar y visualizar los datos almacenados en una base de datos, tambien se utiliza para realizar análisis y obtener información específica de la base de datos.

### 5.1 Sintaxis
```sql
SELECT [ DISTINCT | ALL ] lista_columnas
FROM lista_tablas
WHERE condición
GROUP BY lista_columnas
HAVING condición
ORDER BY lista_columnas [ ASC | DESC ]
```

- `SELECT`: Lista de columnas que se desean recuperar.
- `FROM`: Tabla o tablas de las cuales se desean recuperar los datos.
- `WHERE`: Condición que deben cumplir los registros a recuperar.
- `GROUP BY`: Agrupar los registros por una o más columnas.
- `HAVING`: Condición que deben cumplir los grupos de registros.
- `ORDER BY`: Ordenar los registros recuperados.
- `DISTINCT`: Elimina los registros duplicados.
- `ALL`: Incluye todos los registros, por defecto.

> [!tip] Mas utilizados:
> Los comandos `SELECT`, `FROM` , `WHERE` y `ORDER BY` son los más utilizados en SQL.

### 5.2 Ejemplo Práctico
```sql
SELECT [ DISTINCT ] nombre, apellido
FROM clientes
WHERE edad > 30
GROUP BY nombre
HAVING apellido = 'Perez'
ORDER BY nombre ASC;
```

### 5.3

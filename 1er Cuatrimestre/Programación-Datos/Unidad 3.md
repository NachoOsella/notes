# CONSULTAS SQL

## 1.0 Introducción
### 1.1 Consultas
Una consulta es una pregunta o solicitud de información que se hace a una base de datos. Las consultas se escriben en un lenguaje específico de consulta, como SQL, y permiten recuperar y manipular datos almacenados en una o más tablas de la base de datos. Las consultas se utilizan en una amplia variedad de aplicaciones, desde la recuperación de información básica hasta la generación de informes complejos y la actualización de datos.

### 1.2 Importancia del SELECT
La instrucción SELECT es una de las más importantes en SQL, ya que se utiliza para recuperar datos de una o más tablas de la base de datos. La instrucción SELECT se utiliza en casi todas las consultas SQL, ya que permite especificar qué datos se deben recuperar, cómo se deben filtrar, ordenar los datos y cómo se deben agrupar y resumir los datos.

---
## 2.0 Clausulas de la sentencia SELECT
### 2.1 Lista de columnas
La lista de columnas que se desean mostrar en la consulta. Esta lista está seperada por comas, recupera y muestra los datos de las columnas especificadas en la lista. Si se desea recuperar todas las columnas de una tabla, se puede utilizar el asterisco (*) en lugar de una lista de columnas.

### 2.2 DISTINCT | ALL
La cláusula `DISTINCT` es una función que se utiliza para eliminar las filas duplicadas. Esto quiere decir que si se tiene una tabla con filas duplicadas, la cláusula `DISTINCT` se encargará de mostrar solo una fila de cada conjunto de filas duplicadas. Por otro lado, la cláusula `ALL` se utiliza para mostrar todas las filas, incluyendo las filas duplicadas(es la opción por defecto).

### 2.3 INTO NuevaTabla
La cláusula `INTO` es propia de SQL SERVER y permite definir la creación de una nuva tabla a partir de los resultados de una consulta. La nueva tabla se crea con la estructura y los datos de la consulta. Es utlizado para crear tablas temporales o tablas de respaldo.

### 2.4 FROM lista de tablas
Esta cláusula especifica el nombre de la tabla o tablas de las que se desean recuperar los datos. Si se desea recuperar datos de más de una tabla, se debe especificar el nombre de cada tabla separado por comas.

### 2.5 WHERE condición
La cláusula `WHERE` se utiliza para filtrar los datos recuperados de una o más tablas. La condición especificada en la cláusula WHERE se evalúa para cada fila de la tabla y solo se muestran las filas que cumplan con la condición. La condición puede ser una expresión lógica que compara una columna con un valor o una expresión.

### 2.6 GROUP BY lista de columnas
Se utiliza para agrupar los resultados de una consulta en base a uno o más columnas.  

### 2.7 HAVING condición
Esta cláusula se utiliza para filtrar los resultados de una consulta que se han agrupado utilizando la cláusula GROUP BY. La condición especificada en la cláusula HAVING se evalúa para cada grupo de filas y solo se muestran los grupos que cumplan con la condición. La condición puede ser una expresión lógica que compara una columna con un valor o una expresión.

### 2.8 ORDER BY lista de columna
La cláusula `ORDER BY` se utiliza para ordenar los resultados de una consulta en base a una o más columnas. La cláusula ORDER BY se puede utilizar para ordenar los resultados en orden ascendente (ASC) o descendente (DESC).

---
## 3.0 Condiciones de Busqueda con WHERE
### 3.1 Operadores de comparación

### 3.2 Operadores LIKE y patrones de búsqueda

### 3.3 Test de Rango con BETWEEN

### 3.4 Test de Pertenencia a un conjunto con IN

### 3.5 Test de Valor nulo con IS NULL

### 3.6 Operador NOT


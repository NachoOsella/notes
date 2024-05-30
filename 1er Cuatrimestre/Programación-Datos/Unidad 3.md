# CONSULTAS SQL

## 1.0 Introducción
### 1.1 Consultas
Una consulta es una pregunta o solicitud de información que se hace a una base de datos. Las consultas se escriben en un lenguaje específico de consulta, como SQL, y permiten recuperar y manipular datos almacenados en una o más tablas de la base de datos. Las consultas se utilizan en una amplia variedad de aplicaciones, desde la recuperación de información básica hasta la generación de informes complejos y la actualización de datos.

### 1.2 Importancia del SELECT
La instrucción SELECT es una de las más importantes en SQL, ya que se utiliza para recuperar datos de una o más tablas de la base de datos. La instrucción SELECT se utiliza en casi todas las consultas SQL, ya que permite especificar qué datos se deben recuperar, cómo se deben filtrar, ordenar los datos y cómo se deben agrupar y resumir los datos.

---
## 2.0 Cláusulas de la Sentencia SELECT
### 2.1 Lista de Columnas
La lista de columnas que se desean mostrar en la consulta. Esta lista está separada por comas, recupera y muestra los datos de las columnas especificadas en la lista. Si se desea recuperar todas las columnas de una tabla, se puede utilizar el asterisco (*) en lugar de una lista de columnas.

### 2.2 DISTINCT | ALL
La cláusula `DISTINCT` es una función que se utiliza para eliminar las filas duplicadas. Esto quiere decir que si se tiene una tabla con filas duplicadas, la cláusula `DISTINCT` se encargará de mostrar solo una fila de cada conjunto de filas duplicadas. Por otro lado, la cláusula `ALL` se utiliza para mostrar todas las filas, incluyendo las filas duplicadas (es la opción por defecto).

### 2.3 INTO Nueva Tabla
La cláusula `INTO` es propia de SQL SERVER y permite definir la creación de una nueva tabla a partir de los resultados de una consulta. La nueva tabla se crea con la estructura y los datos de la consulta. Es utilizada para crear tablas temporales o tablas de respaldo.

### 2.4 FROM Lista de Tablas
Esta cláusula especifica el nombre de la tabla o tablas de las que se desean recuperar los datos. Si se desea recuperar datos de más de una tabla, se debe especificar el nombre de cada tabla separado por comas.

### 2.5 WHERE Condición
La cláusula `WHERE` se utiliza para filtrar los datos recuperados de una o más tablas. La condición especificada en la cláusula WHERE se evalúa para cada fila de la tabla y solo se muestran las filas que cumplan con la condición. La condición puede ser una expresión lógica que compara una columna con un valor o una expresión.

### 2.6 GROUP BY Lista de Columnas
Se utiliza para agrupar los resultados de una consulta en base a una o más columnas. La agrupación permite realizar cálculos agregados en cada grupo de datos.

### 2.7 HAVING Condición
Esta cláusula se utiliza para filtrar los resultados de una consulta que se han agrupado utilizando la cláusula GROUP BY. La condición especificada en la cláusula HAVING se evalúa para cada grupo de filas y solo se muestran los grupos que cumplan con la condición. La condición puede ser una expresión lógica que compara una columna con un valor o una expresión.

### 2.8 ORDER BY Lista de Columnas
La cláusula `ORDER BY` se utiliza para ordenar los resultados de una consulta en base a una o más columnas. La cláusula ORDER BY se puede utilizar para ordenar los resultados en orden ascendente (ASC) o descendente (DESC).

---
## 3.0 Condiciones de Búsqueda con WHERE
### 3.1 Operadores de Comparación
Los operadores de comparación se utilizan para comparar valores en la cláusula WHERE. Los operadores más comunes son:
- `=`: Igual a.
- `<>` o `!=`: Diferente de.
- `<`: Menor que.
- `>`: Mayor que.
- `<=`: Menor o igual que.
- `>=`: Mayor o igual que.

### 3.2 Operadores LIKE y Patrones de Búsqueda
El operador `LIKE` se utiliza para buscar un patrón específico en una columna. Los patrones de búsqueda pueden incluir:
- `%`: Cualquier secuencia de caracteres.
- `_`: Un solo carácter.
- `[ ]`: Cualquier carácter dentro de los corchetes.
- `[^ ]`: Cualquier carácter que no esté dentro de los corchetes.

### 3.3 Test de Rango con BETWEEN
La cláusula `BETWEEN` se utiliza para seleccionar valores dentro de un rango especificado. La sintaxis es:
```sql
WHERE columna BETWEEN valor1 AND valor2
```

### 3.4 Test de Pertenencia a un Conjunto con IN
La cláusula `IN` se utiliza para comprobar si un valor está en un conjunto de valores especificados. La sintaxis es:
```sql
WHERE columna IN (valor1, valor2, ...)
```

### 3.5 Test de Valor Nulo con IS NULL
La condición `IS NULL` se utiliza para comprobar si un valor es NULL. La sintaxis es:
```sql
WHERE columna IS NULL
```

### 3.6 Operador NOT
El operador `NOT` se utiliza para invertir el resultado de una condición. Por ejemplo:
```sql
WHERE columna NOT IN (valor1, valor2, ...)
```

---
## 4.0 Condiciones de Búsqueda Compuestas
### 4.1 Operador AND
El operador `AND` se utiliza para combinar múltiples condiciones en la cláusula WHERE. Todas las condiciones deben ser verdaderas para que la fila sea seleccionada.
```sql
WHERE condición1 AND condición2
```

### 4.2 Operador OR
El operador `OR` se utiliza para combinar múltiples condiciones en la cláusula WHERE. Al menos una de las condiciones debe ser verdadera para que la fila sea seleccionada.
```sql
WHERE condición1 OR condición2
```

### 4.3 Combinación de Condiciones con Paréntesis
Se pueden combinar condiciones complejas utilizando paréntesis para agrupar condiciones.
```sql
WHERE (condición1 AND condición2) OR condición3
```

---
## 5.0 Consultas Compuestas
### 5.1 UNION
El operador `UNION` se utiliza para combinar los resultados de dos o más consultas SELECT. Cada consulta debe tener el mismo número de columnas, y las columnas correspondientes deben tener tipos de datos compatibles.
```sql
SELECT columna1, columna2 FROM tabla1
UNION
SELECT columna1, columna2 FROM tabla2
```

### 5.2 EXCEPT
El operador `EXCEPT` se utiliza para devolver las filas que están en la primera consulta pero no en la segunda. Las consultas deben tener el mismo número de columnas y tipos de datos compatibles.
```sql
SELECT columna1, columna2 FROM tabla1
EXCEPT
SELECT columna1, columna2 FROM tabla2
```

### 5.3 INTERSECT
El operador `INTERSECT` se utiliza para devolver las filas que están presentes en ambas consultas. Las consultas deben tener el mismo número de columnas y tipos de datos compatibles.
```sql
SELECT columna1, columna2 FROM tabla1
INTERSECT
SELECT columna1, columna2 FROM tabla2
```

---
## 6.0 Combinación de Tablas
### 6.1 INNER JOIN
El `INNER JOIN` devuelve las filas cuando hay una coincidencia en ambas tablas. Es el tipo de join más común.
```sql
SELECT columnas
FROM tabla1
INNER JOIN tabla2 ON tabla1.columna = tabla2.columna
```

### 6.2 LEFT JOIN
El `LEFT JOIN` devuelve todas las filas de la tabla de la izquierda y las filas coincidentes de la tabla de la derecha. Si no hay coincidencia, las filas de la derecha tendrán valores NULL.
```sql
SELECT columnas
FROM tabla1
LEFT JOIN tabla2 ON tabla1.columna = tabla2.columna
```

### 6.3 RIGHT JOIN
El `RIGHT JOIN` devuelve todas las filas de la tabla de la derecha y las filas coincidentes de la tabla de la izquierda. Si no hay coincidencia, las filas de la izquierda tendrán valores NULL.
```sql
SELECT columnas
FROM tabla1
RIGHT JOIN tabla2 ON tabla1.columna = tabla2.columna
```

---
## 7.0 Funciones Incorporadas
### 7.1 Funciones para el Manejo de Cadenas
Funciones comunes incluyen `CONCAT`, `SUBSTRING`, `LENGTH`, `UPPER`, `LOWER`, etc. Estas funciones permiten manipular cadenas de texto.

### 7.2 Funciones Matemáticas
Funciones comunes incluyen `AVG`, `SUM`, `MIN`, `MAX`, `COUNT`, etc. Estas funciones permiten realizar cálculos matemáticos sobre los datos.

### 7.3 Funciones para el Uso de Fechas y Horas
Funciones comunes incluyen `NOW`, `DATE_ADD`, `DATEDIFF`, `YEAR`, `MONTH`, `DAY`, etc. Estas funciones permiten manipular y realizar cálculos sobre fechas y horas.

---
## 8.0 Conclusión
### 8.1 Resumen de la Importancia de las Consultas en SQL
Las consultas en SQL son fundamentales para interactuar con bases de datos relacionales. Permiten recuperar, filtrar, ordenar, agrupar y resumir datos, lo que es esencial para el análisis y la gestión de la información.

### 8.2 Aplicaciones Prácticas
Las consultas SQL se utilizan en una amplia variedad de aplicaciones prácticas, desde la generación de informes y análisis de datos hasta la integración de datos en aplicaciones y la gestión diaria de bases de datos empresariales.


## 📊 Unidad 1: Resumir Datos en SQL

### Funciones de Agregación

SQL ofrece funciones para resumir datos, ideales para análisis:

- **SUM(column)**: Calcula el total de una columna.
- **AVG(column)**: Computa el promedio de una columna.
- **MIN(column)**: Encuentra el valor más pequeño.
- **MAX(column)**: Encuentra el valor más grande.
- **COUNT(*)**: Cuenta el número total de filas.
- **COUNT(column)**: Cuenta valores no NULL en una columna.
- **COUNT(DISTINCT column)**: Cuenta valores únicos.

**Ejemplo:**

```sql
SELECT SUM(pre_unitario) AS total_price FROM articulos;
```

### Consultas Agrupadas (GROUP BY)

El cláusula `GROUP BY` agrupa datos por columnas para producir subtotales.

**Ejemplo:**

```sql
SELECT vendor_id, SUM(invoice_total) AS total_sales 
FROM invoices 
GROUP BY vendor_id;
```

### Filtrar Grupos (HAVING)

El cláusula `HAVING` filtra grupos basados en condiciones, después de la agregación.

**Ejemplo:**

```sql
SELECT vendor_id, SUM(invoice_total) AS total_sales 
FROM invoices 
GROUP BY vendor_id 
HAVING SUM(invoice_total) > 1000;
```

### Combinar Resultados (UNION y UNION ALL)

- **UNION**: Combina resultados y elimina duplicados.
- **UNION ALL**: Combina resultados incluyendo duplicados.

Ambos requieren el mismo número de columnas con tipos de datos compatibles.

**Ejemplo:**

```sql
SELECT column1 FROM table1 
UNION 
SELECT column1 FROM table2;
```

### Vistas

Las vistas son tablas virtuales creadas desde consultas SQL, útiles para simplificar consultas complejas o restringir acceso.

- **Creación**: `CREATE VIEW view_name AS SELECT ...`
- **Modificación**: `ALTER VIEW view_name AS SELECT ...`
- **Eliminación**: `DROP VIEW view_name`

### Tablas Temporales

Las tablas temporales se usan para almacenamiento a corto plazo:

- Locales: `#table_name` (específicas de la sesión).
- Globales: `##table_name` (disponibles para todas las sesiones).

**Ejemplo:**

```sql
CREATE TABLE #temp (id INT, name VARCHAR(50));
INSERT INTO #temp SELECT id, name FROM customers;
SELECT * FROM #temp;
```

### Consejo:

> Cuando uses `COUNT(*)`, es eficiente ya que no verifica valores NULL, pero `COUNT(column_name)` ignora NULLs. Elige según tus necesidades.

---

## 🔍 Unidad 2: Subconsultas en SQL

### Introducción

Una subconsulta es una consulta anidada dentro de otra sentencia SQL, típicamente en las cláusulas WHERE, HAVING o SELECT. Debe estar entre paréntesis y retorna una sola columna de datos. No puede usar UNION ni ORDER BY, pero puede referenciar columnas de la consulta principal.

### Subconsultas en la Cláusula WHERE

#### Prueba de Comparación

Usa operadores de comparación para comparar un valor con el resultado único de una subconsulta.

**Ejemplo:**

```sql
SELECT cod_articulo, descripcion, pre_unitario 
FROM articulos 
WHERE pre_unitario < (SELECT AVG(pre_unitario) FROM articulos);
```

#### Prueba de Pertenencia (IN/NOT IN)

Verifica si un valor pertenece o no a un conjunto retornado por una subconsulta.

**Ejemplo:**

```sql
SELECT * FROM clients 
WHERE client_id IN (SELECT client_id FROM purchases WHERE year(purchase_date) = 2024);
```

#### Prueba de Existencia (EXISTS/NOT EXISTS)

Verifica si una subconsulta retorna filas.

**Ejemplo:**

```sql
SELECT * FROM clients 
WHERE EXISTS (SELECT 1 FROM purchases 
              WHERE purchases.client_id = clients.client_id 
              AND year(purchase_date) = 2024);
```

#### Pruebas Cuantificadas (ANY/ALL)

- **ANY**: Retorna verdadero si al menos una comparación es verdadera.
- **ALL**: Retorna verdadero solo si todas las comparaciones son verdaderas.

**Ejemplo:**

```sql
SELECT * FROM products 
WHERE price < ANY (SELECT price FROM competitor_products);
```

### Subconsultas en la Cláusula HAVING

Filtra grupos basados en una condición que involucra una subconsulta.

**Ejemplo:**

```sql
SELECT vendor_id, SUM(invoice_total) AS total_sales 
FROM invoices 
GROUP BY vendor_id 
HAVING SUM(invoice_total) > (SELECT AVG(total_sales) 
                            FROM (SELECT vendor_id, SUM(invoice_total) AS total_sales 
                                  FROM invoices 
                                  GROUP BY vendor_id) AS subquery);
```

### Subconsultas en la Cláusula SELECT

Usadas para retornar columnas adicionales calculadas.

**Ejemplo:**

```sql
SELECT product_id, product_name, 
       (SELECT AVG(rating) FROM reviews 
        WHERE product_id = p.product_id) AS avg_rating 
FROM products p;
```

### Tablas Derivadas

Subconsultas en la cláusula FROM actúan como tablas temporales.

**Ejemplo:**

```sql
SELECT * FROM (SELECT client_id, SUM(purchase_amount) AS total_purchases 
               FROM purchases 
               GROUP BY client_id) AS client_purchases 
WHERE total_purchases > 1000;
```

### Subconsultas en UPDATE y DELETE

Usadas en la cláusula WHERE para especificar condiciones basadas en resultados de subconsultas.

**Ejemplo:**

```sql
UPDATE products 
SET price = price * 1.1 
WHERE category IN (SELECT category FROM categories WHERE discount_eligible = 1);
```

### Consejo:

> Las subconsultas pueden hacer tus consultas más legibles y modulares. Sin embargo, pueden afectar el rendimiento, así que optimízalas cuidadosamente.

---

## ⚙️ Unidad 3: Programación en SQL Server con Transact SQL

### Visión General de Transact SQL

Transact SQL (TSQL) extiende SQL estándar con características de programación como variables, declaraciones de control de flujo y bucles, permitiendo el desarrollo completo de aplicaciones de base de datos.

### Variables

Las variables locales almacenan un solo valor de datos y se usan en lotes y scripts.

- **Declaración**: `DECLARE @variable_name data_type [= value]`
- **Inicialización**: Usando `SET` o `SELECT`

**Ejemplo:**

```sql
DECLARE @count INT;
SET @count = (SELECT COUNT(*) FROM customers);
```

### Declaraciones de Control de Flujo

#### IF/ELSE

Ejecuta código basado en condiciones.

**Ejemplo:**

```sql
IF EXISTS (SELECT 1 FROM customers WHERE customer_id = 1)
    PRINT 'Customer exists'
ELSE
    PRINT 'Customer does not exist'
```

#### WHILE

Bucle mientras una condición sea verdadera.

**Ejemplo:**

```sql
DECLARE @i INT = 1;
WHILE @i <= 10
BEGIN
    PRINT @i;
    SET @i = @i + 1;
END
```

#### CASE

Proporciona lógica condicional para retornar diferentes valores.

**Ejemplo:**

```sql
SELECT product_id, price,
    CASE
        WHEN price < 100 THEN 'Low'
        WHEN price BETWEEN 100 AND 500 THEN 'Medium'
        ELSE 'High'
    END AS price_category
FROM products;
```

### Procedimientos Almacenados

Bloques de código SQL precompilados que realizan operaciones en la base de datos.

- **Creación**: `CREATE PROCEDURE procedure_name AS ...`
- **Ejecución**: `EXEC procedure_name`
- **Modificación**: `ALTER PROCEDURE procedure_name AS ...`
- **Eliminación**: `DROP PROCEDURE procedure_name`

**Ejemplo:**

```sql
CREATE PROC GetCustomerCount AS SELECT COUNT(*) FROM customers;
EXEC GetCustomerCount;
```

### Funciones Definidas por el Usuario

Tres tipos:

1. **Escalar**: Retorna un solo valor.
2. **De tabla de múltiples declaraciones**: Retorna una tabla vía múltiples declaraciones.
3. **De tabla en línea**: Retorna una tabla vía un solo SELECT.

**Ejemplo (función escalar):**

```sql
CREATE FUNCTION GetAveragePrice()
RETURNS DECIMAL(10,2)
AS
BEGIN
    RETURN (SELECT AVG(price) FROM products);
END
```

### Triggers

Procedimientos automáticos que se ejecutan en respuesta a eventos DML (INSERT, UPDATE, DELETE).

- **Tipos**: AFTER, INSTEAD OF
- Usa tablas virtuales `inserted` y `deleted` para acceder a datos nuevos/eliminados.

**Ejemplo:**

```sql
CREATE TRIGGER CheckStock ON orders AFTER INSERT
AS
BEGIN
    IF (SELECT quantity FROM inserted) > (SELECT stock FROM products WHERE product_id = (SELECT product_id FROM inserted))
        ROLLBACK TRANSACTION
END
```

### Manejo de Errores

Usa bloques `TRY...CATCH` para manejar errores.

**Ejemplo:**

```sql
BEGIN TRY
    INSERT INTO customers (name) VALUES ('New Customer');
END TRY
BEGIN CATCH
    PRINT ERROR_MESSAGE();
END CATCH
```

### Características Adicionales

- **Encriptación**: `WITH ENCRYPTION` para asegurar código.
- **Anidamiento**: Los procedimientos almacenados pueden llamarse hasta 32 niveles.

### Consejo:

> Siempre maneja errores de manera elegante en tus procedimientos y funciones para hacer tus aplicaciones de base de datos más robustas.

---
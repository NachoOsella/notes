### Resumen Unidad 1

#### 1. Introducción
SQL (Structured Query Language) es un lenguaje de programación diseñado para gestionar y manipular bases de datos relacionales. Es fundamental para la administración de datos, permitiendo realizar operaciones como la creación, actualización, recuperación y eliminación de datos. Su importancia radica en su capacidad para interactuar con bases de datos de manera eficiente y estandarizada.

---
#### 2. ¿Qué es SQL?
SQL es un lenguaje estándar para el manejo de bases de datos relacionales. Sus características principales incluyen:
- **Definición y manipulación de datos**: Permite definir estructuras de datos (tablas) y manipular los datos contenidos en ellas.
- **Origen y estandarización**: SQL fue desarrollado en los años 70 por IBM y posteriormente estandarizado por ISO y ANSI.
- **Diferencias entre motores de bases de datos**: Diversos sistemas de gestión de bases de datos (DBMS) como MySQL, PostgreSQL, SQL Server y Oracle utilizan SQL con ligeras variaciones.

---
#### 3. Usos de SQL
SQL se utiliza para diversas operaciones en bases de datos:
- **Definición de datos**: Crear y modificar estructuras de datos (tablas, índices, etc.).
- **Recuperación de datos**: Consultas para extraer información específica.
- **Manipulación de datos**: Inserción, actualización y eliminación de datos.
- **Control de acceso**: Gestión de permisos y seguridad para acceder a los datos.
- **Compartición de información**: Facilita la generación de reportes y vistas compartidas.
- **Integridad de datos**: Asegura la consistencia y precisión de los datos mediante restricciones y reglas.

---
#### 4. Beneficios de SQL
SQL ofrece múltiples beneficios, entre ellos:
- **Independencia de los proveedores**: SQL es un estándar, lo que permite su uso en diferentes DBMS.
- **Portabilidad**: Los datos pueden trasladarse entre diferentes sistemas sin grandes modificaciones.
- **Fundamento relacional**: Basado en el modelo relacional, que es intuitivo y matemáticamente sólido.
- **Sintaxis similar al inglés**: Fácil de aprender y entender.
- **Consultas interactivas ad hoc**: Permite crear consultas específicas en tiempo real.
- **Múltiples vistas de datos**: Ofrece diferentes perspectivas de los mismos datos para diferentes usuarios.
- **Definición dinámica de datos**: Flexibilidad para modificar la estructura de la base de datos sin afectar los datos existentes.
- **Arquitectura cliente/servidor**: SQL es compatible con la arquitectura cliente/servidor, facilitando su uso en redes.

---
#### 5. SQL Server
SQL Server es un sistema de gestión de bases de datos desarrollado por Microsoft. Está diseñado para soportar una arquitectura cliente/servidor, donde el cliente envía solicitudes al servidor que procesa y devuelve los resultados.

- **Arquitectura cliente-servidor**: El servidor gestiona las bases de datos y procesa las consultas, mientras que los clientes interactúan con los datos a través de aplicaciones.
- **Aplicaciones cliente**: Programas que permiten a los usuarios interactuar con SQL Server, como herramientas de administración y aplicaciones de negocio.
- **Modelos de almacenamiento de datos**: 
  - **OLTP (Online Transaction Processing)**: Diseñado para la gestión de transacciones rápidas y frecuentes.
  - **OLAP (Online Analytical Processing)**: Optimizado para consultas complejas y análisis de datos.

---
#### 6. Objetos de SQL Server
| **Objeto**                     | **Descripción**                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------- |
| **Tablas**                     | Estructuras fundamentales que almacenan datos en filas y columnas.                              |
| **Vistas**                     | Consultas almacenadas que proporcionan diferentes perspectivas de los datos.                    |
| **Funciones**                  | Subprogramas que realizan cálculos y devuelven un valor.                                        |
| **Procedimientos almacenados** | Secuencias de comandos SQL predefinidas que se almacenan y pueden ser ejecutadas repetidamente. |
| **Disparadores**               | Mecanismos que se activan automáticamente en respuesta a ciertos eventos en la base de datos.   |
| **Índices**                    | Estructuras que mejoran el rendimiento de las consultas.                                        |
| **Reglas**                     | Condiciones que aseguran la integridad de los datos.                                            |
| **Restricciones**              | Reglas aplicadas a las columnas de las tablas para garantizar la validez de los datos.          |
| **Valores predeterminados**    | Valores asignados automáticamente a las columnas si no se especifica otro valor.                |

---
#### 7. Transact-SQL (T-SQL)
Transact-SQL (T-SQL) es una extensión de SQL desarrollada por Microsoft para SQL Server. T-SQL incluye características adicionales como:
- **Programación procedimental**: Permite el uso de estructuras de control de flujo como bucles y condiciones.
- **Manejo de errores**: Funciones avanzadas para la gestión de errores y excepciones.
- **Operaciones avanzadas**: Capacidad para realizar operaciones más complejas como el manejo de transacciones y la ejecución de procedimientos almacenados.

---
#### 8. Tipos de Sentencias SQL
- **DDL (Data Definition Language)**: Sentencias para la definición de estructuras de datos, como `CREATE`, `ALTER` y `DROP`.
- **DML (Data Manipulation Language)**: Sentencias para la manipulación de datos, como `INSERT`, `UPDATE` y `DELETE`.
- **DCL (Data Control Language)**: Sentencias para el control de acceso y permisos, como `GRANT` y `REVOKE`.
- **TCL (Transaction Control Language)**: Sentencias para el control de transacciones, como `COMMIT` y `ROLLBACK`.
- **Sentencias de programación:** Sentencias para la programación de procedimientos almacenados, funciones y disparadores.

---
#### 9. Sentencias de Definición de Datos

##### 9.1. Creación de Tablas
Para crear una tabla en SQL, se utiliza la sentencia `CREATE TABLE` seguida del nombre de la tabla y la definición de las columnas. Un ejemplo de creación de tabla sería:
```SQL
CREATE TABLE nombre_tabla
(nom_col1 tipo_dato [IDENTITY(inicio,incremento)][NULL|NOT NULL],
 nom_col2  tipo_dato,
 nom_col_n tipo_dato
 [CONSTRAINT nombre_constraint PRIMARY KEY(nom_col1)],
 [CONSTRAINT nombre_constraint FOREIGN KEY (nom_col2)
REFERENCES tabla2 (nombre_columna_tabla2)]
)
```
**Donde:**
- `CREATE TABLE` es la sentencia utilizada para crear una tabla.
- `nom_col` es utilizado para crear una columna dentro de la tabla, y `tipo_dato` para especificar el tipo de dato que utilizará la columna.
- `[CONSTRAINT nombre_constraint PRIMARY KEY(nom_col1)]`. Es utilizado para crear una clave primaria dentro de la tabla. `nombre_constraint` es usado para darle un nombre a la restricción. Y `PRIMARY KEY` es utilizado para indicar que la columna `nom_col1` será la clave primaria.
- `[CONSTRAINT nombre_constraint FOREIGN KEY (nom_col2) REFERENCES tabla2 (nombre_columna_tabla2)]`. Es utilizado para crear una clave foránea dentro de la tabla. `nombre_constraint` es usado para darle un nombre a la restricción. `FOREIGN KEY` es utilizado para indicar que la columna `nom_col2` será la clave foránea. `REFERENCES tabla2 (nombre_columna_tabla2)` es utilizado para indicar a qué tabla y columna hace referencia la clave foránea.
- `[IDENTITY(inicio,incremento)]`. Es utilizado para crear una columna de identidad, la cual se autoincrementa en cada inserción. `inicio` es el valor inicial de la columna y `incremento` es el valor que se incrementará en cada inserción.
- `[NULL|NOT NULL]`. Es utilizado para indicar si la columna puede aceptar valores nulos o no.
- `REFERENCES` es utilizado para indicar a qué tabla y columna hace referencia la clave foránea.


##### 9.2. Tipos de Datos
- **Binarios**: Almacenan cadenas de bits expresados en numeros exadecimal.
  - `BINARY(n)`: Almacena cadenas de bits de longitud fija.
  - `VARBINARY(n)`: Almacena cadenas de bits de longitud variable.
- **Alfanuméricos**: Almacenan caracteres alfanuméricos.
  - `CHAR(n)`: Almacena cadenas de caracteres de longitud fija.
  - `VARCHAR(n)`: Almacena cadenas de caracteres de longitud variable.
- **Fecha y Hora**: Almacenan fechas y horas.
  - `DATETIME`: Almacena fechas y horas.
- **Numéricos Decimales(punto fijo)**: Almacenan números decimales.
  - `DECIMAL`: Almacena números decimales.
- **Numéricos Decimales(punto flotante)**: Almacenan números decimales.
  - `FLOAT`: Almacena números decimales en punto flotante.
- **Enteros**: Almacenan números enteros.
  - `INT`: Almacena números enteros.
- **Moneda**: Almacenan valores monetarios.
  - `MONEY`: Almacena valores monetarios.
- **Especiales**: Almacenan valores especiales.
  - `UNIQUEIDENTIFIER`: Almacena identificadores únicos.
  - `bit`: Almacena valores booleanos.
  - `cursor`: Almacena cursores.
  - `sql_variant`: Almacena valores de diferentes tipos de datos.
  - `table`: Almacena un resultado de una consulta en forma de tabla temporal.
- **Unicode**: Almacenan caracteres Unicode.
  - `NCHAR(n)`: Almacena cadenas Unicode de longitud fija.
  - `NVARCHAR(n)`: Almacena cadenas Unicode de longitud variable.

##### 9.3. Modificación de Tablas
Se utilizan las sentencias 2 tipos de sentencias para modificar tablas `alter table` y `drop table`.

###### 9.3.1. Modificación de Columnas
Para agregar una columna a una tabla, se utiliza la sentencia `ALTER TABLE` seguida del nombre de la tabla y la definición de la columna a agregar. Un ejemplo de agregación de columna sería:
```SQL
ALTER TABLE nombre_tabla
ADD nom_col tipo_datos
```
Para eliminar una columna de una tabla, se utiliza la sentencia `ALTER TABLE` seguida del nombre de la tabla y la columna a eliminar. Un ejemplo de eliminación de columna sería:
```SQL
ALTER TABLE nombre_tabla
DROP COLUMN nom_col
```
Para modificar el tipo de datos de una columna, se utiliza la sentencia `ALTER TABLE` seguida del nombre de la tabla y la columna a modificar. Un ejemplo de modificación de tipo de datos sería:
```SQL
ALTER TABLE nombre_tabla
ALTER COLUMN nom_col tipo_datos
```
Para agregar una clave primaria a una tabla, se utiliza la sentencia `ALTER TABLE` seguida del nombre de la tabla y la definición de la clave primaria. Un ejemplo de agregación de clave primaria sería:
```SQL
ALTER TABLE nombre_tabla
ADD CONSTRAINT nombre_constraint PRIMARY KEY(nom_col)
```
###### 9.3.2. Eliminación de Tablas
Para eliminar una tabla, se utiliza la sentencia `DROP TABLE` seguida del nombre de la tabla a eliminar. Un ejemplo de eliminación de tabla sería:
```SQL
DROP TABLE nombre_tabla
```
> **Nota**: Al eliminar una tabla, se eliminan todos los datos contenidos en ella. Es importante tener cuidado al utilizar esta sentencia para evitar la pérdida de información.

---
#### 10. Puntos Importantes a Recordar
1. **Enfocarse en los usos de SQL y sus beneficios:** Es fundamental comprender las aplicaciones y ventajas de SQL para su correcto uso en la gestión de bases de datos.
2. **Practica con ejemplos concretos:** Realizar ejercicios prácticos para afianzar tus conocimientos y habilidades en SQL.
3. **Arquitectura cliente/servidor de SQL Server:** Comprende la arquitectura cliente/servidor de SQL Server y su funcionamiento en entornos de red.


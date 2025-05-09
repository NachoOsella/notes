# 📚 Bases de Datos II

## 📖 Unidad Temática N° 1: Bases de Datos NoSQL

### 🎯 Introducción a NoSQL

El término NoSQL ("Not only SQL") surge en 1998 como alternativa a las bases de datos relacionales (RDBMS). A diferencia de estas, las BD NoSQL:
*   Buscan alternativas a los sistemas relacionales tradicionales.
*   Priorizan el acceso rápido a la información sobre la integridad estricta.
*   Generalmente no cumplen con el esquema entidad-relación.
*   No suelen utilizar SQL para la manipulación de datos.

### 🤔 ¿Por qué surgen las Bases de Datos NoSQL?

El crecimiento exponencial del volumen de información y la complejidad de su administración impulsaron la necesidad de nuevas arquitecturas. Los principales aspectos que motivaron la aparición de NoSQL son:
*   El gran aumento del tamaño y la cantidad de archivos.
*   La necesidad de respuestas rápidas ante consultas simultáneas de millones de usuarios.
*   La tendencia hacia sistemas descentralizados.

### ✨ Ventajas de las Bases de Datos NoSQL

Las BD NoSQL ofrecen varias ventajas clave:
*   **Evitan complejidad innecesaria:** Reducen las restricciones implementadas en RDBMS para mantener consistencia estricta.
*   **Alto rendimiento:** Muchas ofrecen un rendimiento superior a los RDBMS.
*   **Escalabilidad horizontal y hardware básico:** Diseñadas para escalar horizontalmente de forma sencilla, sin depender de hardware costoso.
*   **No requieren mapeado:** Sus estructuras de datos son más simples y se alinean mejor con los lenguajes de programación orientados a objetos.
*   **Facilidad para descentralizar:** Modelos de datos más aptos para la distribución en múltiples servidores.
*   **Consultas simples:** Requieren menos operaciones, son más naturales y eficientes.

> En algunos momentos, se puede hacer necesario **comprometer la fiabilidad para lograr un mejor desempeño**.

### ⚖️ Principales diferencias con las BD Relacionales

La diferencia fundamental radica en los principios de diseño y las garantías de consistencia:

*   **Teorema de CAP vs. Propiedades ACID:**
    *   **CAP Theorem:** En un sistema distribuido, solo se pueden garantizar un máximo de dos de tres características: **C**onsistencia, **A**sponibilidad, **P**artición Tolerancia. Esto lleva a sistemas como:
        *   CA: Coherentes y Disponibles (mal manejo de particiones).
        *   CP: Coherentes y Tolerantes a Particiones (ciertas carencias de disponibilidad).
        *   AP: Disponibles y Tolerantes a Particiones (no estrictamente coherentes, ej: consistencia eventual).
    *   **ACID Properties (en SQL):** Las transacciones garantizan **A**tomicidad, **C**onsistencia, **I**solamiento y **D**urabilidad.

> **Consistencia (CAP):** "La consistencia significa que cada usuario de la base de datos tiene una vista idéntica de los datos en un instante dado." (Harrison, 2015)
> **Disponibilidad (CAP):** "Disponibilidad significa que, en caso de falla, la base de datos permanece operativa." (Harrison, 2015)
> **Tolerancia a particiones (CAP):** "La tolerancia a la partición significa que la base de datos puede mantener las operaciones en caso de que la red falle entre dos segmentos del sistema distribuido." (Harrison, 2015)
> **Atomicidad (ACID):** "La transacción es indivisible, o todas las declaraciones de la transacción se aplican a la base de datos o no se aplica ninguna..." (Harrison, 2015)
>  **Manejo de datos:**
>    *   RDBMS: Estructura rígida, esquema predefinido, tipado estricto, permite JOINs. La consistencia total puede hacerlos más lentos.
>    *   NoSQL: Estructura flexible, esquemas dinámicos (o inexistentes), evita JOINs por sobrecarga en grandes volúmenes. Manejan consistencia eventual para permitir cambios concurrentes.

### 📊 Tipos de Bases de Datos NoSQL

Se destacan cuatro tipos principales:
1.  **Base de datos clave-valor:** Estructura más sencilla, almacena pares de `clave -> valor`. Ejemplos: Cassandra, Redis, DynamoDB.
2.  **Base de datos documentales:** Más flexibles, almacenan documentos (similares a JSON/BSON) con estructura variable. Ejemplos: MongoDB, ArangoDB, CouchDB.
3.  **Base de datos en grafo:** Representan datos como nodos y relaciones (aristas) entre ellos. Ejemplos: Neo4j.
4.  **Bases de datos en columnas:** Almacenan datos organizados en columnas en lugar de filas. Ejemplo: HBase.

### 🍃 ¿Qué es MongoDB?

MongoDB es un ejemplo popular de base de datos documental.
*   Ofrece gran escalabilidad y flexibilidad.
*   Almacena datos en documentos flexibles (similares a JSON/BSON) con un esquema dinámico que puede cambiar con el tiempo.
*   Un **documento** es una estructura de pares campo-valor, similar a objetos JSON. Los valores pueden ser tipos simples, arrays, u otros documentos anidados.
*   Las ventajas de usar documentos incluyen su correspondencia con tipos de lenguajes de programación y la reducción de la necesidad de JOINs costosos mediante el uso de documentos embebidos.
*   Los documentos se agrupan en **colecciones** (análogas a tablas relacionales).
*   Las colecciones se agrupan en **bases de datos**. MongoDB crea la base de datos o colección la primera vez que se insertan datos en ella.

### 🛠️ Operaciones básicas en MongoDB (Shell)

*   **Seleccionar/Ver BD:**
    ```
    use <nombre_bd>
    show dbs
    db
    ```
*   **Insertar Documentos:**
    *   `db.collection.insertOne(<documento>)`
    *   `db.collection.insertMany([<doc1>, <doc2>, ...])`
    *   Si el documento no tiene `_id`, MongoDB agrega un `ObjectId` automáticamente.
*   **Leer Documentos:**
    *   `db.collection.find(<filtro>)`
    *   Ejemplo: `db.alumnos.find({})` (todos), `db.alumnos.find({"legajo":123})` (filtrado).
    *   Se puede usar `.pretty()` para formatear la salida.
*   **Actualizar Documentos:**
    *   `db.collection.updateOne(<filtro>, <operacion_actualizacion>)`
    *   `db.collection.updateMany(<filtro>, <operacion_actualizacion>)`
    *   Usan **operadores de actualización** como `$set`, `$inc`, `$rename`, etc.
    *   Ejemplo: `db.alumnos.updateOne({"legajo":1234}, {$set: {"nombre": "Lucas"}})`
*   **Reemplazar Documentos:**
    *   `db.collection.replaceOne(<filtro>, <nuevo_documento>)`
    *   Reemplaza el documento completo (excepto el `_id`). El nuevo documento no debe usar operadores de actualización.
*   **Eliminar Documentos:**
    *   `db.collection.deleteOne(<filtro>)` (elimina máximo uno)
    *   `db.collection.deleteMany(<filtro>)` (elimina todos los que coincidan)
    *   Ejemplo: `db.alumnos.deleteMany({})` (elimina todos), `db.alumnos.deleteMany({"legajo":123})` (elimina filtrados).

---

## 📖 Unidad Temática N° 2: Bases de Datos Clave Valor

### 🎯 Introducción a las Bases de Datos Clave-Valor (KV)

Las BD Clave-Valor son un tipo fundamental dentro de la familia NoSQL.
*   Emplean un modelo simple de almacenamiento de datos.
*   Son valoradas por su alta eficacia en operaciones de lectura y escritura.

### 🔑 ¿Qué es una BD clave-valor?

Una "key-value database" o "key-value store":
*   Se basa en un modelo de almacenamiento que mapea una **clave** única a un **valor**.
*   La clave es el identificador único para consultar el valor.
*   El valor puede ser cualquier cosa: un tipo simple (cadena, número), un objeto complejo, un documento, una referencia a archivo o una tupla.
*   El contenido puede ser muy heterogéneo (diferentes tipos de valores asociados a diferentes claves).
*   Las claves pueden seguir un esquema, pero no es estrictamente necesario.
*   Ofrecen consultas muy rápidas, beneficiosas para aplicaciones de alto tráfico.
*   Pueden usarse para almacenar metadatos simples que se vinculan a datos más grandes en otras bases de datos.

### 🌱 Orígenes y Evolución

*   Un precursor es el sistema `dbm` de Unix (1979), una librería para gestionar vectores asociativos con clave única.
*   Inicialmente limitadas por rendimiento y falta de estandarización.
*   Reviven con el auge de la computación en la nube (post-2010) como parte del movimiento NoSQL.

### 🔄 Tratamiento de los datos

*   Tratan los datos como una **colección opaca** única.
*   Los registros pueden tener campos diferentes, ofreciendo gran flexibilidad.
*   Se alinean bien con conceptos modernos como la programación orientada a objetos.
*   Suelen usar menos memoria que las RDBMS para la misma cantidad de datos.

### 🚀 Desempeño

*   El rendimiento, especialmente en operaciones de lectura y escritura, es una característica clave.
*   La flexibilidad y el menor uso de memoria contribuyen a un mejor desempeño en ciertas cargas de trabajo.

### 📊 Tipos de Bases de Datos Clave-Valor

Según su almacenamiento y arquitectura:
1.  **Almacenamiento en Memoria (In-Memory):** Datos en RAM (extremadamente rápidas, baja latencia). Ideal para cachés. ✨ Ejemplos: Redis, Memcached.
2.  **Almacenamiento en Disco:** Datos en disco duro (persistentes, menos rápidas que en memoria). ✨ Ejemplos: RocksDB, LevelDB.
3.  **Distribuidas:** Diseñadas para entornos distribuidos (escalado horizontal, grandes volúmenes). ✨ Ejemplos: Amazon DynamoDB, Riak.
4.  **Especializadas:** Optimizadas para usos específicos (grafos, indexación). ✨ Ejemplos: Aerospike, Berkeley DB.
5.  **Híbridas:** Combinan KV con funcionalidades adicionales (consultas complejas, multi-modelo). ✨ Ejemplos: Redis (KV + estructuras de datos + atómicas), FoundationDB (KV + transacciones ACID).

*   Pueden usar diferentes modelos de consistencia (eventual hasta serializabilidad).
*   Algunas permiten la ordenación de claves.
*   Un registro es un conjunto de pares KV. La clave puede tener componentes (primaria + menores), similar a rutas de archivo. El valor es una cadena arbitraria de bytes.

### ✨ Ventajas de las BD Clave-Valor

*   **Simplicidad:** Fáciles de usar y entender.
*   **Escalabilidad:** Ideales para sistemas distribuidos.
*   **Rendimiento:** Muy rápidas, especialmente en memoria.
*   **Almacenamiento en diccionarios:** Permite recuperación rápida y funcional sin importar el peso del dato.

### 💼 Casos de Uso Comunes

*   Almacenamiento de sesiones de usuario.
*   Sistemas de caché.
*   Configuraciones y preferencias de usuario.
*   Datos temporales o efímeros.
*   Proyectos que requieren almacenamiento y recuperación rápida de datos.
*   Desarrollo rápido de prototipos.
*   Almacenes de sesiones y carritos de compra en e-commerce.
*   Tecnología publicitaria.
*   IoT.

### 🛠️ Funcionamiento

Una BD Clave-Valor funciona como un **diccionario** o **tabla hash**. Almacena una colección de registros (objetos con campos) que se recuperan usando una clave única que identifica cada registro.

### 🛒 Detalles de Uso Comunes

*   **Almacén de sesiones:** En aplicaciones web, se guarda información de la sesión del usuario (perfil, mensajes, configuración) con un identificador de sesión único como clave.
*   **Carro de compras:** Permiten manejar el escalado de grandes cantidades de datos y cambios de estado para millones de usuarios simultáneamente a través de procesamiento y almacenamiento distribuidos.

### ⚠️ Desventajas de las BD Clave-Valor

*   **Falta de estándares:** El manejo de datos no está estandarizado.
*   **Lenguajes de consulta básicos:** Impiden realizar trabajos de análisis profundo.
*   **Falta de herramientas avanzadas:** Algunos gestores carecen de ellas para configuración personalizada.
*   **Consultas y ordenamiento limitados:** Solo pueden realizarse partiendo de la clave primaria.

### 📏 Características

*   Son **altamente particionables**.
*   Permiten un **escalado horizontal** en niveles que otros tipos de NoSQL pueden no lograr.
*   La clave sirve como identificador único para el par clave-valor.
*   La flexibilidad en el tipo de datos de claves y valores (simples o complejos).

### 🚀 Almacenamientos de Valor Clave en Acción / Aplicaciones

*   Benefician aplicaciones que consultan **conjuntos de datos pequeños** rápidamente (ej: mostrar las últimas publicaciones de un feed social).
*   Ideales para **aplicaciones en tiempo real** que requieren actualizaciones segundo a segundo (ej: valores de acciones).

### 🆚 Almacenamientos KV frente a Bases de Datos Relacionales

*   **RDBMS:** Almacenan datos en tablas (filas y columnas) con un esquema rígido. Un identificador único (clave primaria) relaciona columnas en una fila. Los desarrolladores se limitan a las estructuras definidas. Permiten JOINs.
*   **BD KV:** Asocian una clave única con un valor flexible (puede ser un objeto complejo). Los desarrolladores tienen más libertad en el tipo de valor. La recuperación se basa directamente en la clave, evitando la necesidad de JOINs complejas.

### 💡 Elegir la tienda de valor clave adecuada

Considerar:
*   **Caching en memoria:** Crucial para aplicaciones que necesitan respuestas muy rápidas, almacenando datos frecuentes en RAM para evitar accesos a disco.
*   **Particionamiento y distribución:** Para grandes volúmenes de datos y escalar, busque bases de datos diseñadas para entornos distribuidos (soportan estrategias como hashing o sharding).

### ⚙️ Mejores prácticas para la implementación

Para preservar el rendimiento, especialmente a medida que la base de datos crece:
*   Utilizar **claves primarias compuestas** para optimizar consultas en rango.
*   Usar una **clave de clasificación** para consultas en rango.
*   Usar una **clave de fragmento (shard key)** para almacenamiento distribuido.
*   Asegurarse de que el motor de la base de datos sea compatible con **caching**.

### ☁️ Redis Cloud

Es un servicio de base de datos gestionado que ofrece las capacidades de Redis en la nube:
*   Velocidad y fiabilidad de Redis.
*   Escalabilidad sin fisuras y alta disponibilidad.
*   Soporte para Redis y Redis Stack.
*   Escalabilidad lineal.
*   Fallo instantáneo, copias de seguridad y recuperación.
*   Actuación previsible.
*   Supervisión y soporte 24/7.

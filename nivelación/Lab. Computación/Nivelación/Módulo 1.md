# Dato, información y conocimiento
---
## Conceptos Básicos

- **Datos**
    Son hechos aislados y en bruto, los cuales situados en un
    contexto significativo y mediante una o varias operaciones de procesamiento, permiten obtener resultados que son objeto de dicho procesamiento
    
- **Información**
    Es el conjunto de datos organizados, procesados y contextualizados que se transforman en un mensaje con un sentido para un receptor. 
    
- **Conocimiento**
    Es un proceso complejo que depende de múltiples factores ya que en el mismo se produce una mezcla de experiencias y valores que permiten interpretar la información y hacen al saber, es decir permiten analizar cómo sirve la información y así transformarla, siendo útil para la acción.
    

![[Pasted image 20240222201005.png]]

---

## Sistemas de información

Para comprender que es un sistema de información y todo lo que lo integra primero hay que entender que es un sistema en si.

### Sistema

Un sistema es un conjunto de elementos que se interrelacionan entre sí y con un ambiente (un sistema abierto) y con un objetivo común.

Basándose en lo anterior se puede decir entonces que un Sistema de Información (S.I.) es básicamente un conjunto de partes que trabajan juntas para satisfacer las necesidades de información de una organización. Está formado por personas, datos, actividades y recursos materiales que procesan y distribuyen información de manera efectiva. Su objetivo es ayudar a los usuarios a aumentar su conocimiento, reducir la incertidumbre y mejorar la toma de decisiones en la organización.

**Un sistema de información realiza 4 actividades principales:**

- **Entrada de Datos**
    
    Los datos ingresados deben ser relevantes para la organización y el propósito del Sistema de Información (S.I.). Es crucial identificar los datos necesarios para evitar errores relacionados con la abundancia o escasez de información, ya que estos errores pueden generar costos elevados, pérdida de tiempo e incertidumbre.
    
- **Almacenamiento de Datos**
    
    Este proceso asegura que el S.I. pueda recuperar datos de manera consistente y confiable cuando sea necesario. El almacenamiento debe seguir estructuras previamente definidas, construidas por un profesional experto que conozca los requisitos específicos del S.I. Los datos se guardan en almacenamiento no volátil, específicamente en una Base de Datos.
    
- **Procesamiento**
    
    Ocurre cuando se genera información a partir de los datos seleccionados y almacenados en los procesos anteriores.
    
- **Salida de Información**
    
    Este es el objetivo principal del S.I. Para que la información sea útil a los administradores y personas involucradas en la toma de decisiones, debe cumplir con ciertas características.
    

### Esquema de un Sistema de Información

![[Pasted image 20240222201018.png]]

---

### Propiedades de la información

- Accesible: Que los usuarios puedan acceder a ella de una manera fácil.
- Exacta: Libre de errores.
- Completa: Que contenga todos los hechos relevantes.
- Económica: El costo debe ser accesible.
- Flexible: Que pueda utilizarse para una gran variedad de propósitos.
- Relevante: Debe ser importante para las personas que toman las decisiones.
- Segura: Estar protegida de usuarios no autorizados.
- Simple: Sin complejidades que enturbien su significado.
- Oportuna: En el momento en que se necesita.
- Verificable: Que pueda ser comprobable su exactitud.
- Confiable: Que el método de recolección y procesamiento sean fiable de igual modo que su fuente.
## Conclusión

Este tema se enfoca en cómo se almacenan los datos persistentes en un Sistema de Información (S.I.), es decir, aquellos guardados en un almacenamiento no volátil. Se aborda la manera en que estos datos están disponibles para otros procesos dentro del mismo sistema. Se destaca la importancia de considerar la perspectiva del "todo", aplicando un enfoque sistémico al diseñar o trabajar en el almacenamiento de datos para satisfacer un requerimiento específico, teniendo en cuenta la relación entre las partes y el conjunto.

Se menciona como ejemplo un Sistema de Procesamiento de Transacciones (TPS), que registra las transacciones rutinarias diarias necesarias para el funcionamiento de una empresa. Este sistema se ubica en el nivel más bajo de la jerarquía organizacional y se ilustra con el caso de un sistema de cajas en un supermercado.

---

# Base de Datos

## Conceptos Básicos

Es un conjunto de datos pertenecientes a un mismo contexto y almacenados sistemáticamente para su posterior uso. Estos datos pueden ser almacenados física o digitalmente, pero con el avance de la tecnología la primer opción esta dejando de ser utilizada.

Se dividen en 2 tipos, Estructuradas y No Estructuradas(veremos solo el primer tipo)

### Información importante a tener en cuenta:

- Cada unidad de dato es indivisible en dicha base de datos y se encuentra almacenado en un campo.
- Un conjunto de campos referido a una misma y única persona, cosa o transacción en particular forman lo que se llama un registro.
- Un conjunto de registros y campos relacionados con el mismo tema de una organización se agrupan en una misma tabla de datos

---

# Elementos de una Base de Datos

- **Campo**
    
    Es el espacio de almacenamiento de un dato en particular, la pieza más pequeña de los componentes de una base de datos, que es indivisible y contiene un único dato.
    
- **Registro**
    
    Es un conjunto de campos que describen un mismo objeto o entidad. Es equivalente a un ficha si hablamos de medios electrónicos. 
    
    Cada registro está compuesto por los mismos campos, y en la misma disposición; sólo cambia el contenido, pero permanece invariable la longitud y la ubicación de cada uno de los datos en todos los registros.
    
- **Tabla**
    
    Es una colección de registros idénticos en cuanto a su formato y que se refieren al conjunto de objetos del mismo tipo.
    
    Se le denomina tabla ya que los datos se organizan en formato fila/columna. En cada fila se encuentran los datos de un único registro, por lo que en las columnas encontraremos un determinado campo de cada uno de los registros de la tabla.
    
- Los nombres de los campos aparecen al tope de la tabla y describen la información que contiene cada uno de ellos.
- A las tablas también se las llama entidades porque representan una cosa, persona o transacción y a cada campo se lo llama atributo ya que describen a esa entidad

![[Pasted image 20240222201042.png]]

---

En un sistema de información también hay datos que no se almacenan en ninguna base de datos, a estos se los denomina datos transitorios (los permanentes son denominados Persistentes). Los ejemplos mas comunes son:

### Datos de entrada

Se refieren a la información que entra por primera vez al sistema y que por ende no estaba almacenada en una base de datos previamente, esta información nueva puede dar pie a modificaciones en los datos persistentes ya almacenados o convertirse en una base de datos nueva.

### Datos de Salida

Hacen referencia a los mensajes que emana el sistema, esta información puede derivar de los datos persistentes pero no son considerados como parte de la propia base de datos.

---

# Sistema de Base de Datos

Una base de datos no se encuentra aislada, no es solo un archivo almacenado en un dispositivo físico, sino que se interrelacionan con diferentes componentes que tienen el objetivo común de almacenar datos, el mantenimiento de los mismos y que además el sistema disponga de esos datos en todo momento para poder obtener información a partir del Sistema de Base de Datos.

### Componentes

- **Base de Datos**
    
    Es el conjunto de datos pertenecientes a un mismo contexto, recolectados y almacenados sistemáticamente para su posterior uso.
    
- **Hardware**
    
    Son los componentes físicos necesarios para el almacenamiento de los datos
    y su posterior procesamiento:
    
    - Para la base de datos: Volúmenes de almacenamiento, procesadores, memorias, etc. (todo lo que hace posible la ejecución del software de la base de datos)
    - Para la aplicación:
        - Terminales inteligentes: Una pc
        - Terminales no inteligentes: Aquellas que no realizan ningún tipo de procesamiento.
- **Software**
    
    En la gestión de bases de datos, existen diversos niveles de software que conectan la base de datos física con los usuarios del sistema:
    
    1. **Sistema Operativo**: Administra el hardware necesario para el funcionamiento del sistema.
    2. **Sistema Gestor de Base de Datos (SGBD o DBMS)**: Este sistema maneja las solicitudes de acceso a la base de datos realizadas por los usuarios. Su función principal es abstraer a los usuarios de los detalles técnicos de la base de datos, permitiendo que interactúen de manera más amigable con ella.
    3. **Aplicaciones de Usuario**: Son programas creados por programadores para que los usuarios puedan acceder a la base de datos de manera más intuitiva.
    
    **Funciones del SGBD**:
    
    - **Mantenimiento de Relaciones entre los Datos**: El SGBD se encarga de mantener la integridad de las relaciones entre los datos almacenados en la base de datos.
    - **Garantía de Integridad de Datos**: Asegura que los datos estén almacenados correctamente y que se cumplan las reglas que definen las relaciones entre ellos.
    - **Recuperación de Datos en Caso de Errores del Sistema**: En caso de fallos o errores del sistema, el SGBD garantiza la recuperación de los datos hasta un punto coherente, evitando la pérdida de información.
- **Usuarios**
    
    El usuario es aquella persona que de alguna forma interactúa con la base de datos.
    
    1. Programador de aplicaciones: Es quién se encarga de escribir los programas de aplicación que utiliza la base de datos. 
    2. Usuario final: Es quién interactúa con el sistema desde una terminal en línea. 
    3. Administrador de Base de Datos (DBA). Es el técnico responsable de poner en práctica las decisiones del administrador de datos.

### Conformación de una base de datos

![[Pasted image 20240222201104.png]]

---

# Niveles de abstracción de datos

Para garantizar la utilidad del sistema, es crucial que recupere los datos de manera eficiente. Esto ha llevado al diseño de estructuras de datos complejas en las bases de datos. Dado que muchos usuarios no están familiarizados con la tecnicidad de estas estructuras ni con el hardware, los desarrolladores las ocultan mediante niveles de abstracción para simplificar la interacción y proteger los datos contra errores.
Hay 3 niveles de abstracción:

- **Nivel físico:**
    
    Es el nivel mas bajo de los 3 y describe como se almacenan los datos en los dispositivos de almacenamiento secundarios, por ejemplo un disco duro.
    
    En este nivel interviene el sistema operativo con el rol de gestionar el almacenamiento secundario y su sistema de archivos.
    
- **Nivel Conceptual o lógico:**
    
    Es un nivel más alto de abstracción y describe qué datos se almacenan en la base de datos y qué relaciones existen entre esos datos.
    
- **Nivel de vistas:**
    
    Es el nivel más alto de abstracción y refiere a los distintos segmentos que se pueden visibilizar de la base de datos completa de parte de los usuarios finales.
    

![[Pasted image 20240222201115.png]]

---
# Modelo de Datos

El modelo de datos es una colección de herramientas conceptuales para describir los datos, las relaciones, la semántica y las restricciones de consistencia. Algunos ejemplos de modelos de datos son:

- **Modelo Entidad-Relación:**
    
    Está basado en una percepción del mundo real que consta de una colección de objetos básicos, llamadas entidades, y de relaciones entre estos objetos.
    
    ![[Pasted image 20240222201143.png]]
    
- **Modelo de Datos orientado a objetos:**
    
    Es una extensión del paradigma de programación orientado a objetos donde se representa el mundo real y sus problemas a través de objetos; cada uno de ellos posee un nombre, atributos y operaciones, y poseen las propiedades de polimorfismo, herencia y encapsulamiento.
    ![[Pasted image 20240222201147.png]]
    
- **Modelo de Datos Semiestructurados:**
    
    Permite la especificación de los datos, donde los elementos de datos individuales del mismo tipo pueden tener diferentes conjuntos de atributos.
    ![[Pasted image 20240222201155.png]]
    
- **Modelo Relacional:**
    
    El **Modelo Relacional** es un tipo de modelo basado en registros, lo que significa que la Base de Datos se estructura en registros de formato fijo de varios tipos. Este modelo es una metodología que se utiliza para representar una realidad específica, utilizando una colección de herramientas conceptuales para describir datos, las relaciones entre ellos y las restricciones de consistencia.
    
    En un sistema relacional, los datos se perciben en forma de **tablas relacionales**, que se vinculan entre sí a través de identificadores llamados **clave**. Una base de datos relacional es un sistema diseñado específicamente para manejar información que ha sido previamente organizada en una o varias tablas relacionadas entre sí mediante campos comunes.
    
    Cuando se diseña una tabla para una base de datos en el modelo relacional, se enfoca en la tabla, teniendo en cuenta su nombre, el nombre de los campos y los campos claves, dejando de lado los registros individuales.
    (este es el modelo que usaremos a lo largo de la materia)
    

### Tipos de Datos:

- Alfanumérico: Implica que el campo va a guardar textos, números y/o símbolos.
- Numérico: En capos de este tipo se van a guardar números que luego pueden ser utilizados para cálculos matemáticos, se distingue si serán enteros o decimales.
- Fecha y Hora: Estos campos permitirán el guardado de fechas y horas.
- Booleano: Los campos de este tipo guardarán datos que puedan asumir solo dos valores (verdadero o falso)
---
## [[nivelación/Lab. Computación/Nivelación/Módulo 2|Módulo 2]]


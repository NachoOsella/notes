# Programación Orientada a Objetos

## Definición
Es una técnica de programación que:
- Utiliza *objetos* como bloque esencial de construcción, estos objetos utilizan *mensajes* como forma de "colaborar" entre si. Por lo tanto se puede decir que:
```
				Objetos + Mensajes = Programa
```
- Facilita la creación de software de calidad gracias a la potencia de mantenimiento, la extensibilidad y la reutilización del software creado bajo este paradigma.
- Trata de amoldarse al pensamiento del humano y no tanto al de una maquina.

## Componentes
### Objetos
Es el elemento fundamental de este paradigma. Es una entidad que posee atributos y métodos, los atributos definen el estado del mismo y los métodos definen su comportamiento. Cada objeto forma parte de una organización jerárquica por ende, no es un ente aislado.

### Métodos
Los métodos definen e implementan el comportamiento del objeto. Especifican la forma en que se controlan los datos de un objeto, se puede decir que son un conjunto de instrucciones que le dice al objeto **como se comporta**.

### Mensajes
Un objeto solo en si mismo no es muy útil, por lo que en general se utilizan muchos de ellos. Para poder interactuar entre ellos y conseguir funcionalidades mas complejas, se necesita de un mensaje para comunicar los unos con los otros.
El mensaje simplemente es *una petición de un objeto a otro*.
![[Pasted image 20240320195648.png]]
### Clases
Una clase es un modelo que se utiliza para describir uno o mas objetos del mismo tipo. Cada vez que se crea un objeto, este es una instancia de la clase. Seria como el molde de los objetos.

## Principios
### Abstracción
Es el proceso en el cual se extraen las propiedades/características mas importantes del sistema o del objeto. Facilita la comprensión, el modelado y la implementación. 
### Encapsulamiento
Es el mecanismo por el cual los objetos protegen sus variables bajo la custodia de sus métodos. De esta manera el usuario puede ver los objetos como cajas negras que proporcionan servicios.
Permite:
- **Modularidad:** El código fuente de un objeto se puede escribir y mantener independientemente del código de los otros objetos y permite la reutilización.
- **Ocultación de la información:** El objeto puede tener información publica (con la que interactúa el usuario) o privada (oculta al usuario).
### Herencia
Es la propiedad que permite a los objetos crearse a partir de otros. Cada vez que el objeto se divide, la subclase creada comparte características con la clase de la que deriva.
### Polimorfismo
Hace referencia a la capacidad de objetos de distintas clases de responder de manera diferente a un mismo mensaje o método. Lo que significa que un método puede actuar de manera diferente dependiendo del objeto al que se lo aplique. Permite crear código mas genérico y flexible.

```
💡Si un lenguaje cumple con estos 4 principios, se puede decir que es un Lenguaje Orientado a Objetos.
```

## Modelado de Clases
Se utiliza el lenguaje unificado de modelado(*UML*). Es un lenguaje gráfico para visualizar, especificar, construir y documentar un sistema. Este lenguaje ofrece un estándar para describir un "*plano*" del sistema.
#### Para que se necesitan?
Para empezar a desarrollar soluciones orientadas a objetos es necesario primero identificar las clases principales del dominio del problema. Para eso, *MUL* ofrece un **Diagrama de Clases** mediante el cual es posible representar clases, atributos, métodos y relaciones de los objetos.
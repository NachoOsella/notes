# Arquitectura y Funcionamiento del Microprocesador

## Unidad Central de Procesamiento (CPU)
Es la encargada de leer las instrucciones de la memoria, procesarla, realizar los cálculos solicitados y guardar en la memoria los resultados de dichos operaciones.

## Unidad Aritmética-Lógica (UAL)
Es la encargada de realizar **operaciones aritméticas** (suma, resta) y **lógicas** (comparaciones, operaciones de Boole, etc.) solicitadas por el programa. Es comandada por la unidad de control, es decir, la *UAL* opera siguiendo las órdenes de la Unidad de Control.

## Unidad de Control (µC)
La Unidad de Control (µC) en un sistema informático tiene la función principal de coordinar y ejecutar las instrucciones del programa. Su funcionamiento se resume en los siguientes pasos:

1. **Extracción e Identificación de Instrucción**: La µC extrae la instrucción a ejecutar desde la Memoria Principal y la identifica.

2. **Establecimiento de Señales Eléctricas**: Una vez identificada la instrucción, la µC establece las señales eléctricas correspondientes para ejecutarla.

3. **Procesamiento de la Instrucción Actual**: Dependiendo del tipo de instrucción (por ejemplo, operaciones aritméticas o lógicas), la µC establece señales para la Unidad Aritmético-Lógica (UAL) y extrae los datos necesarios de la memoria principal. Luego, desencadena el procesamiento de dichos datos en la UAL.

4. **Procesamiento de la Instrucción Siguiente**: Una vez finalizada la ejecución de la instrucción actual, la µC continúa con la siguiente instrucción del programa.

5. **Control del Funcionamiento del Sistema**: La µC coordina y controla el funcionamiento de todo el sistema, enviando órdenes externas de lectura/escritura a la memoria y unidades de entrada/salida, así como órdenes internas a la UAL para realizar operaciones.

6. **Sincronización con el Reloj**: La Unidad de Control recibe señales de un reloj, que sincroniza todas las operaciones de la computadora. El ritmo de trabajo de la CPU está determinado por la frecuencia de este reloj, que marca la velocidad de procesamiento de la computadora.

En resumen, la Unidad de Control coordina la ejecución de instrucciones, controla el funcionamiento del sistema y se sincroniza con el reloj para marcar el ritmo de trabajo de la CPU.

## Frecuencia de Señal de Reloj
Es una señal eléctrica de forma rectangular, es decir una sucesión indefinida de 0s y 1s, que se mide en ciclos por unidad de tiempo (usualmente segundos). La unidad utilizada es el Hercio (Hz).

## Registros

Los registros son *elementos de la memoria de acceso rápido* que se encuentran dentro del procesador, existen 5 tipos de registros según su utilidad:
1. **Registros de Propósito General:** Suelen utilizarse como operandos en las instrucciones del ensamblador.
2. **Registros de Datos:** Se pueden diferenciar por el formato y el tamaño de los datos que almacenan.
3. **Registros de Direccionamiento:** Se utilizan para acceder a memoria y pueden almacenar direcciones o índices.
4. **Registros de Instrucción:**
	- *Program Counter (pc):* Contiene la siguiente dirección de la instrucción en que hay que leer en memoria.
	- *Stack Pointer (sp):* Contiene la última dirección de mememoria.
5. **Registros de Estado y Control:**
	- *Bit de Cero (Zero):* Se activa si el resultado obtenido es 0.
	- *Bit de Acarreo (Carry):* Se activa si en el ultimo bit que operamos en una operación aritmética se produce transporte (carry).
	- *Bit de Desbordamiento (Overflow):* Se activa si el resultado de una operación aritmética no cabe en el registro.
	- *Bit de Signo (Sign):* Se activa si el resultado de una operación aritmética es negativo.
	- *Bit de Interrupción (Interupt):* Se activa si se produce una interrupción.
## Buses
Como la [[## Unidad de Control (µC)]] necesita comunicarse con la memoria y los periféricos, lo hace a través de unos "canales" llamados **Buses**. Esta comunicación se realiza por los *buses externos*, que conforman el *Bus del Sistema*. Este ultimo esta compuesto por 3 grupos funcionales de líneas denominados:
1. **Bus de Datos:** Funciona con el bus de direcciones y sirve para transmitir instrucciones y datos, debido a esto es bidireccional (de la CPU a la memoria y viceversa). La cantidad de "canales" que ocupe depende de los bits del CPU.
2. **Bus de Direcciones:** Son líneas de señales para transmitir las direcciones de las posiciones de la memoria en las que el CPU debe escribir o leer información. Es unidireccional.
	La formula para saber la cantidad de buses necesarios es:
	$$B = \frac{\ln(Cantidad \, de \, bytes)}{\ln(2)}$$
3. **Bus de Control:** Sirve para transmitir las señales de control que coordinan el funcionamiento del CPU, es decir si quiere que escriba o lea cierta dirección de la memoria. Dependiendo la acción se le asigna un 1 o un 0.


#### Interrupciones: 
Las interrupciones son el mecanismos mediante el cual un dispositivo externo, al procesador puede interrumpir el programa que está ejecutando el procesador con el fin de ejecutar otro programa.

#### E/S para DMA: 
El Direct Memory Access es un procesador/controlador especializado en transferencias de gran tamaño desde un periférico a la memoria y viceversa.


---

## Memorias
![[Pasted image 20240503121128.png]]

### Tipos de Memoria

#### Memoria ROM (Read-Only Memory):
Es un tipo de memoria de almacenamiento no volátil que contiene datos que no cambian o son permanentes. Por lo general, se utiliza para almacenar el firmware o el software de sistema de un dispositivo, como las instrucciones de arranque. Los datos en la memoria ROM no se pueden modificar, solo leer.

#### Memoria RAM (Random Access Memory):
Es un tipo de memoria volátil que se utiliza para almacenar datos y programas temporales que el procesador necesita acceder rápidamente. A diferencia de la ROM, la RAM permite lectura y escritura de datos. Es fundamental para el funcionamiento de programas y sistemas operativos, pero al ser volátil los datos se pierden cuando se apaga el dispositivo.


#### Memoria FIFO
Es una memoria de acceso secuencial. Los datos pueden ser leídos en el mismo orden en el que fueron escritos, ademas son escritos en serie y leídos en serie.

#### Memoria LIFO
Al contrario de la FIFO, los datos son leidos en forma de pila, es decir, los primeros en escribirse son los ultimos en leerse.

#### Memoria PROM
Es solo de lectura ya que al momento de escribirse se quema un fusible que impide el volver a hacerlo.

#### EPROM
Es similiar a la prom pero que su información puede ser borrada con luz ultravioleta.

#### EEPROM
Es una variable de la EPROM y puede programarse y borrarse electricamente.

#### Memoria FLASH H
Es similar a la EEPROM pero su velocidad de escritura es mayor. Es la mas utilizada hoy en día y existen muchas variantes de ella.


### Banco de Memoria
Se trata de un diagrama de bloques que ilustra la disposición de inicio y fin de la memoria. Desde la perspectiva del micro controlador, la cantidad de chips de memoria es irrelevante, ya que percibe la memoria como un único banco y su preocupación principal radica en la capacidad de almacenamiento.

---

## Decodificador
Un decodificador es un circuito de combinaciones que convierte un código binario en señales de control para direccionar espacios de memoria. Por cada N entradas, puede direccionar 2^N espacios de memoria. Por ejemplo, con 2 entradas, puede direccionar 4 espacios de memoria, ya que 2^2 es igual a 4.

---

## Microprocesador
#### Velocidad del Microprocesador
Determina la rapidez con la que se ejecutan las instrucciones. Se mide en Hertz (Hz) y se expresa en Megahertz (MHz) o Gigahertz (GHz) y es controlado por el reloj del sistema.

La frecuencia de reloj es la cantidad de ciclos de reloj que se ejecutan por segundo. Cada ciclo de reloj representa una instrucción ejecutada por el procesador.

#### Tipos de instrucciones
1. *Transferencia:* MOV
2. *Aritméticas:* ADD, DCR, INC
3. *Lógicas:* AND, OR, XOR
4. *Rutinas de Secuencia:* JUMP




# Preguntas parte 1

## ¿Qué es el internet?
El internet es una red global de computadoras interconectadas que permite la comunicación y el intercambio de datos entre dispositivos en todo el mundo. Utiliza un conjunto de protocolos, conocidos como TCP/IP, para transmitir información a través de diversas redes interconectadas.

## Línea de tiempo del internet desde 1960 hasta 1990
1. **1960**: Comienzo del desarrollo de ARPANET, precursor del internet, por el Departamento de Defensa de EE.UU.
2. **1972**: Se desarrola el primer programa de correco electrónico(Ray Tomlinson).
3. **1973**: Al expandir el alcance de las redes, se crean los primeros nodos internacionales.
4. **1980**: Se establecen los protocolos TCP/IP, permitiendo la comunicación entre diferentes redes en sistemas UNIX.
5. **1981**: Aparición de las Computadoras Personales, creado asi redes locales.
6. **1983**: Se oficializa el lanzamiento de Internet.

## Diagrama de referencia del modelo TCP/IP
![Modelo TCP/IP](https://www.profesionalreview.com/wp-content/uploads/2020/02/protocolo-TCP-IP-vs-OSI.png)

## Explicación del modelo OSI
El modelo OSI (Open Systems Interconnection) es un marco de referencia para la comunicación en redes de computadoras. Se compone de siete capas, cada una de las cuales tiene una función específica y se encarga de un aspecto particular del proceso de comunicación. Las capas del modelo OSI, de la más baja a la más alta, son:

1. **Capa Física**
2. **Capa de Enlace de Datos**
3. **Capa de Red**
4. **Capa de Transporte**
5. **Capa de Sesión**
6. **Capa de Presentación**
7. **Capa de Aplicación**

Cada una de estas capas interactúa con las capas adyacentes y tiene responsabilidades específicas en el proceso de transmisión de datos a través de una red.

## ¿Qué es una IP privada y qué es una IP pública?
- **IP privada**: Direcciones IP utilizadas dentro de una red local (LAN) que no son accesibles desde internet.
- **IP pública**: Direcciones IP asignadas a dispositivos accesibles desde internet, permitiendo la comunicación con redes externas.

## ¿Qué es un grupo de trabajo?
Un grupo de trabajo es una configuración de red de igual a igual en la que computadoras y dispositivos comparten recursos y responsabilidades sin un control centralizado, comúnmente en redes pequeñas.

## ¿Qué comando se utiliza para ver la IP de una computadora?
- **Windows**: `ipconfig`
- **Linux/MacOS**: `ifconfig` o `ip a`

## ¿Qué hace el comando ping?
El comando `ping` se utiliza para probar la conectividad de red entre dos dispositivos. Envía paquetes ICMP "Echo Request" y espera respuestas, midiendo el tiempo que tarda en recibir una respuesta.

## ¿Cómo puedo instalar una conexión SSH?
En sistemas basados en Unix, como Linux, se puede instalar un servidor SSH usando:
```bash
sudo apt-get install openssh-server
```
Para conectarse a una máquina remota, se usa:
```bash
ssh usuario@direccion_ip
```
---
# Preguntas parte 2

## Defina todas las capas del modelo OSI
El modelo OSI (Interconexión de Sistemas Abiertos) es un marco conceptual utilizado para entender y diseñar la interoperabilidad de los sistemas de red. Se divide en siete capas:

1. **Capa Física**: Trata con la transmisión y recepción de señales no estructuradas en un medio físico.
2. **Capa de Enlace de Datos**: Proporciona transferencia de datos fiable a través de un enlace físico.
3. **Capa de Red**: Se encarga de determinar la ruta que los datos tomarán para llegar a su destino.
4. **Capa de Transporte**: Asegura la transferencia completa y correcta de datos entre sistemas finales.
5. **Capa de Sesión**: Gestiona y controla las conexiones entre computadoras.
6. **Capa de Presentación**: Traduce los datos entre el formato de la red y el formato que entiende la aplicación.
7. **Capa de Aplicación**: Proporciona servicios de red a las aplicaciones del usuario.

## ¿Qué es un cable módem?
Un cable módem es un dispositivo que conecta una computadora a un servicio de internet de banda ancha a través de la infraestructura de televisión por cable.

## ¿Qué es la fibra óptica?
La fibra óptica es una tecnología que utiliza filamentos de vidrio o plástico para transmitir datos como pulsos de luz, permitiendo altas velocidades de transmisión y largas distancias sin pérdida significativa de calidad.

## ¿Qué es un switch, router y servidor?
- **Switch**: Dispositivo de red que conecta varios dispositivos en una red local y usa direcciones MAC para enviar datos a los destinos correctos.
- **Router**: Dispositivo que conecta diferentes redes y dirige el tráfico de datos entre ellas utilizando direcciones IP.
- **Servidor**: Computadora o programa que proporciona servicios a otros programas o dispositivos en la red, como almacenamiento de datos, aplicaciones web, etc.

## ¿Qué es una VPN y para qué sirve?
Una VPN (Red Privada Virtual) crea una conexión segura y encriptada a través de una red pública, como internet, permitiendo a los usuarios enviar y recibir datos como si sus dispositivos estuvieran conectados directamente a una red privada.

## ¿Qué es la red Tor?
Tor (The Onion Router) es una red de anonimato que permite a los usuarios navegar por internet de forma privada y segura, ocultando su ubicación y actividad mediante el enrutamiento de su tráfico a través de múltiples nodos.

## ¿Qué es la tecnología Dial-Up? ¿Qué es la tecnología ADSL?
- **Dial-Up**: Tecnología de acceso a internet a través de líneas telefónicas analógicas, con velocidades muy bajas en comparación con las tecnologías modernas.
- **ADSL (Asymmetric Digital Subscriber Line)**: Tecnología de acceso a internet de banda ancha que utiliza líneas telefónicas de cobre, ofreciendo mayores velocidades de descarga en comparación con la subida.

## ¿Qué es la tecnología FTTH?
FTTH (Fiber to the Home) es una tecnología de fibra óptica que lleva la conexión de banda ancha directamente a las casas de los usuarios, proporcionando altas velocidades de internet.

## Diferencias entre 3G, 3.5G, 4G y 5G. ¿Existe o se está desarrollando 6G?
- **3G**: Tercera generación de tecnología móvil, con velocidades de hasta 2 Mbps.
- **3.5G**: Evolución de 3G, también conocido como HSPA, con velocidades de hasta 14 Mbps.
- **4G**: Cuarta generación, con velocidades de hasta 1 Gbps.
- **5G**: Quinta generación, con velocidades potenciales de hasta 10 Gbps y menor latencia.
- **6G**: Está en fase de investigación y desarrollo, se espera que ofrezca velocidades aún mayores y mejor integración con tecnologías avanzadas como IoT y AI.

## ¿Qué se define como internet inalámbrico?
El internet inalámbrico es un tipo de conexión a internet que no requiere cables físicos, utilizando en su lugar tecnologías de radiofrecuencia, como Wi-Fi, para conectar dispositivos a la red.

## ¿Qué es FING y para qué sirve?
Fing es una herramienta de escaneo de red que permite a los usuarios identificar todos los dispositivos conectados a una red, proporcionando información como direcciones IP y MAC, nombre del dispositivo y más.

## Diferencias entre 2.4GHz y 5GHz
- **2.4GHz**: Mayor alcance pero menor velocidad, más susceptible a interferencias.
- **5GHz**: Menor alcance pero mayor velocidad, menos interferencias.

## ¿Cómo medir la cobertura de una red Wi-Fi?
Se puede medir la cobertura de una red Wi-Fi utilizando aplicaciones de análisis de Wi-Fi que muestran la intensidad de la señal en diferentes áreas, como NetSpot o Wi-Fi Analyzer.

## ¿Qué es el tráfico de internet?
El tráfico de internet se refiere al volumen de datos que se transmiten y reciben a través de la red en un período de tiempo específico.

## ¿Cómo medir la velocidad de subida y bajada de una red?
Se puede medir la velocidad de subida y bajada de una red utilizando herramientas en línea como Speedtest.net o aplicaciones específicas que realizan pruebas de velocidad de internet.

## ¿Qué es un rompemuros o repetidor?
Un repetidor, o extensor de rango, es un dispositivo que recibe señales de Wi-Fi y las retransmite para extender la cobertura de la red a áreas donde la señal es débil o inexistente.

## ¿Qué es el PowerLine communication?
La comunicación PowerLine es una tecnología que permite transmitir datos a través del cableado eléctrico existente, utilizando adaptadores que se conectan a las tomas de corriente para extender la red de internet a través de la casa.

---
### Pregunta aparte
- **¿Qué es la dirección MAC?**
La dirección MAC (Media Access Control) es un identificador único asignado a la tarjeta de red de un dispositivo, utilizado para identificarlo en una red local. Se compone de 6 bytes en formato hexadecimal.

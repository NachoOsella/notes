
## Preguntas

### ADMINISTRACION:

1. ¿ A que se denomina estrategias de Administracion?
2. ¿Que son las funciones del administrador de memoria?
3. Defina Memoria virtual 
4. ¿Que es la paginacion?
5. ¿A que se denomina fallo de pagina?
6. ¿Que son tablas de pagina? 
### ARCHIVOS:
1. ¿Que son los archivos? 
2. ¿Que es un sistema de archivos? 
3. ¿Como es la nomenclatura de los archivos? 
4. Nombre y describabrevemente los tipos de archivo 
5. Nombre y describabrevemente los tipos de acceso a los archivos.
6. ¿Que es un atributo de archivo? nombre y escriba el significado de almenos 10. 
7. Explique brevemente las 11 operaciones que podemos realizar con los archivos. 
8. ¿Que es un Directorio?
9. ¿a que se le llama directior raiz? 
10. Haga un diagrama de un sistema de directorios jerarquico
11. A que se le denomina Ruta de un ejemplo de una ruta tipoca de Windows y una de linux
12. Nombre y describa las 8 operaciones que podemos realizar con los directorios.
### Aplicacion en linux:
1. ¿Que es un sistema de archivo en linux? 
2. ¿Que es un sistema de archivos virtual en linux?
3. ¿Que es un sistema de archivos extendido en linux? 
4. Explique sistema de archivos de red, arqitectura, protocolo e implementacion del NFS
### Seguridad:
1. ¿A que se denomina UID? y ¿GIDs?¿Que hace chmod?
2. ¿Cuales son las categorias de los permisos de un archivo?
3. De ejemplos de modo de proteccion de archivos en simbolico y que acceso permite 
4. Definir que es super usuario y que comando puedo usar para pasar de usuario a super usaurio.

---

## ADMINISTRACIÓN

### Estrategias de Administración
Serie de estrategias y prácticas para gestionar, optimizar y asegurar el correcto funcionamiento del sistema y los recursos de hardware asociados.

### Funciones del Administrador de Memoria
Las funciones del administrador de memoria incluyen:
1. **Asignación de Memoria:** Asignar y liberar memoria a los procesos cuando la solicitan y terminan.
2. **Gestión de Espacio Libre:** Mantener un registro de las áreas libres y ocupadas de la memoria.
3. **Paginación y Segmentación:** Implementar mecanismos para permitir el uso eficiente de la memoria virtual.
4. **Protección de Memoria:** Asegurar que los procesos no interfieran con la memoria de otros procesos.
5. **Swapping:** Gestionar el intercambio de datos entre la memoria principal y el almacenamiento secundario.

### Memoria Virtual
La memoria virtual es una técnica de gestión de memoria que permite a los programas usar más memoria de la que físicamente posee el sistema, al utilizar espacio en el disco duro para simular memoria RAM adicional.

### ¿Qué es la paginación?

La paginación es una técnica utilizada en los sistemas operativos para gestionar la memoria. En vez de asignar toda la memoria de manera contigua a un proceso, la memoria se divide en pequeñas unidades llamadas **páginas**. Estas páginas son fragmentos de memoria de tamaño fijo, por ejemplo, 4 KB.

Cuando un programa necesita más memoria, el sistema operativo le asigna una cantidad adecuada de páginas. Estas páginas pueden no estar contiguas físicamente en la memoria, lo que permite una utilización más eficiente y flexible de la memoria disponible.

### ¿A qué se denomina fallo de página?

Un **fallo de página** ocurre cuando un programa intenta acceder a una página de memoria que no está actualmente en la memoria física (RAM). Aquí está el proceso detallado:

1. **Acceso Fallido**: El programa intenta acceder a una dirección de memoria que no está en la RAM.
2. **Interrupción**: El procesador genera una interrupción para notificar al sistema operativo.
3. **Manejo del Fallo**: El sistema operativo localiza la página requerida, que suele estar en el disco duro (en el archivo de paginación o swap).
4. **Transferencia**: La página se transfiere desde el disco a la RAM.
5. **Actualización**: Las tablas de página se actualizan para reflejar la nueva ubicación de la página en la RAM.
6. **Reanudación**: El proceso que causó el fallo de página se reanuda y puede acceder a la dirección de memoria solicitada.

Los fallos de página pueden ser costosos en términos de tiempo, ya que acceder al disco duro es mucho más lento que acceder a la RAM.

### ¿Qué son las tablas de página?

Las **tablas de página** son estructuras de datos utilizadas por el sistema operativo para llevar un seguimiento de la relación entre las direcciones de memoria virtuales y las direcciones de memoria físicas. Aquí hay una explicación detallada:

1. **Dirección Virtual**: Cuando un programa accede a una dirección de memoria, usa una dirección virtual.
2. **Traducción**: La dirección virtual se traduce a una dirección física mediante la tabla de página.
3. **Entrada de Tabla de Página**: Cada entrada en la tabla de página contiene la dirección física correspondiente a una página virtual específica.
4. **Niveles de Tablas**: En sistemas con mucha memoria, se utilizan tablas de página jerárquicas (multinivel) para manejar el gran espacio de direcciones virtuales eficientemente.

Las tablas de página permiten que el sistema operativo implemente la paginación, al gestionar y mantener la correspondencia entre las páginas virtuales y las páginas físicas. Esto hace posible que los programas se ejecuten como si tuvieran acceso a una gran cantidad de memoria contigua, cuando en realidad la memoria física puede estar fragmentada.

---
## ARCHIVOS

### Archivos
Los archivos son unidades de almacenamiento de datos que contienen información y están organizados en un sistema de archivos. Pueden contener texto, imágenes, programas, y otros tipos de datos.

### Sistema de Archivos
Un sistema de archivos es la estructura y lógica utilizadas por un sistema operativo para gestionar y almacenar archivos en un dispositivo de almacenamiento, como un disco duro o una unidad SSD.

### Nomenclatura de los Archivos
La nomenclatura de los archivos se refiere a las reglas y convenciones para nombrar archivos. En muchos sistemas, un nombre de archivo puede incluir caracteres alfanuméricos y algunos caracteres especiales, y tiene una extensión que indica su tipo.

### Tipos de Archivos
1. **Archivos de Texto:** Contienen solo caracteres de texto.
2. **Archivos Binarios:** Contienen datos en formato binario.
3. **Archivos Ejecutables:** Contienen programas que pueden ser ejecutados por el sistema operativo.
4. **Archivos de Imagen:** Contienen datos gráficos.
5. **Archivos de Audio/Video:** Contienen datos multimedia.

### Tipos de Acceso a los Archivos

1. **Acceso Indexado**
    - *Qué hace:* Usa un índice para localizar registros rápidamente.
    - *Ventajas:* Búsqueda rápida.
    - *Desventajas:* Requiere espacio extra para el índice.
2. **Acceso Secuencial**
    - *Qué hace:* Lee los datos en el orden en que están almacenados.
    - *Ventajas:* Simple de implementar.
    - *Desventajas:* Lento para búsquedas específicas.
3. **Acceso Directo**
    - *Qué hace:* Accede directamente a un registro específico sin leer los anteriores.
    - *Ventajas:* Muy rápido.
    - *Desventajas:* Necesita conocer la ubicación exacta del registro.
4. **Acceso Secuencial Indexado**
	- *Qué hace:* Usa un índice para encontrar un punto y luego lee secuencialmente desde allí.
    - *Ventajas:* Balance entre rapidez y simplicidad.
    - *Desventajas:* Más complejo que el acceso secuencial puro, pero más eficiente.

### Atributo de Archivo
- **Nombre**: El nombre del archivo, que es una cadena de caracteres que identifica el archivo en el sistema de archivos.
- **Extensión**: La parte del nombre del archivo que sigue al punto (.), que generalmente indica el tipo de archivo (por ejemplo, `.txt`, `.jpg`).
- **Tamaño**: La cantidad de espacio en disco que ocupa el archivo, medida en bytes, kilobytes (KB), megabytes (MB), etc.
- **Fecha de Creación**: La fecha y hora en que el archivo fue creado.
- **Fecha de Modificación**: La fecha y hora en que el archivo fue modificado por última vez.
- **Fecha de Acceso**: La fecha y hora en que el archivo fue accedido por última vez (por ejemplo, abierto o leído).
- **Permisos**: Los permisos que determinan quién puede leer, escribir o ejecutar el archivo. Estos permisos suelen estar especificados para el propietario, el grupo y otros usuarios.
- **Propietario**: El usuario que posee el archivo y tiene control sobre él.
- **Grupo**: El grupo de usuarios al que pertenece el archivo, lo que puede afectar los permisos de acceso.
- **Atributo de Solo Lectura**: Un atributo que indica que el archivo no puede ser modificado o borrado, solo leído.
- **Atributo Oculto**: Un atributo que oculta el archivo de las vistas normales de los usuarios en el sistema de archivos.

### Operaciones con Archivos
1. **Crear:** Generar un nuevo archivo.
2. **Abrir:** Preparar un archivo existente para lectura o escritura.
3. **Leer:** Extraer datos de un archivo.
4. **Escribir:** Insertar datos en un archivo.
5. **Cerrar:** Finalizar la interacción con un archivo.
6. **Borrar:** Eliminar un archivo del sistema de archivos.
7. **Renombrar:** Cambiar el nombre de un archivo.
8. **Copiar:** Duplicar un archivo en otra ubicación.
9. **Mover:** Transferir un archivo a una nueva ubicación.
10. **Buscar:** Localizar un archivo específico.
11. **Atribuir:** Modificar los atributos de un archivo.

### Directorio
Un directorio es una estructura que contiene referencias a otros archivos o directorios, organizando el sistema de archivos de manera jerárquica.

### Directorio Raíz
El directorio raíz es el nivel más alto en la jerarquía de un sistema de archivos, y todos los demás archivos y directorios están contenidos dentro de él.

### Diagrama de Sistema de Directorios Jerárquico
```
/
├── home
│   ├── user
│   │   ├── documents
│   │   └── pictures
├── var
│   ├── log
│   └── tmp
└── etc
    ├── network
    └── system
```

### Ruta
La ruta es la localización completa de un archivo o directorio en el sistema de archivos. Ejemplos:
- **Windows:** `C:\Users\User\Documents\file.txt`
- **Linux:** `/home/user/documents/file.txt`

### Operaciones con Directorios
1. **Crear:** Generar un nuevo directorio.
2. **Eliminar:** Borrar un directorio.
3. **Renombrar:** Cambiar el nombre de un directorio.
4. **Listar:** Mostrar el contenido de un directorio.
5. **Cambiar Directorio:** Navegar a un directorio diferente.
6. **Mover:** Transferir un directorio a una nueva ubicación.
7. **Copiar:** Duplicar un directorio en otra ubicación.
8. **Buscar:** Localizar un directorio específico.

---

## APLICACIÓN EN LINUX

### Sistema de Archivos en Linux
Un sistema de archivos en Linux es la estructura lógica que el sistema operativo usa para organizar y almacenar archivos. Linux soporta varios sistemas de archivos como ext4, Btrfs, XFS, etc.

### Sistema de Archivos Virtual en Linux
El sistema de archivos virtual (VFS) en Linux es una capa de abstracción que permite a diferentes sistemas de archivos coexistir en el mismo sistema operativo, proporcionando una interfaz uniforme para interactuar con todos los sistemas de archivos.

### Sistema de Archivos Extendido en Linux
El sistema de archivos extendido (ext) es una familia de sistemas de archivos utilizados en Linux, incluyendo ext2, ext3, y ext4. Ext4 es el más reciente y ofrece mejoras en la eficiencia, fiabilidad y capacidad.

### Sistema de Archivos de Red (NFS)
NFS (Network File System) permite que los archivos en un servidor sean accedidos por clientes a través de una red. La arquitectura de NFS incluye un servidor NFS, clientes NFS, y utiliza el protocolo NFS para la comunicación. La implementación de NFS en Linux suele hacerse mediante el uso del demonio `nfsd` en el servidor y el comando `mount` en el cliente.

---

## SEGURIDAD

### UID y GID
- **UID (User Identifier):** Es un número único asignado a cada usuario en el sistema.
- **GID (Group Identifier):** Es un número único asignado a cada grupo en el sistema.

### chmod
El comando `chmod` se utiliza para cambiar los permisos de un archivo o directorio en Unix/Linux.

### Categorías de Permisos de un Archivo
1. **Propietario (Owner):** El usuario que posee el archivo.
2. **Grupo (Group):** El grupo que posee el archivo
3. **Otros (Others):** Todos los demás usuarios que no son el propietario ni parte del grupo.

### Ejemplos de Modo de Protección de Archivos en Simbólico y Acceso Permitido
- **Lectura, Escritura y Ejecución para el Propietario; Solo Lectura para el Grupo y Otros:**
  - Simbólico: `rwxr--r--`
  - Comando: `chmod 744 archivo`
- **Lectura y Escritura para el Propietario y el Grupo; Sin Acceso para Otros:**
  - Simbólico: `rw-rw----`
  - Comando: `chmod 660 archivo`
- **Solo Ejecución para el Propietario; Sin Acceso para el Grupo y Otros:**
  - Simbólico: `--x------`
  - Comando: `chmod 100 archivo`

### Super Usuario
El superusuario, o `root`, tiene privilegios completos en el sistema y puede realizar cualquier operación, incluyendo la configuración del sistema y la administración de usuarios. Para pasar de usuario a superusuario, se utiliza el comando `su` (cambiar a superusuario) o `sudo` (ejecutar un comando con privilegios de superusuario).

```bash
# Para cambiar a superusuario
su

# Para ejecutar un comando con privilegios de superusuario
sudo comando
```

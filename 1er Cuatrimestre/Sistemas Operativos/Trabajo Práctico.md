### ADMINISTRACIÓN
#### ¿A qué se denomina estrategias de Administración?
Las estrategias de administración en sistemas operativos se refieren a los métodos y políticas que se implementan para gestionar de manera eficiente los recursos del sistema, como la CPU, la memoria, los dispositivos de almacenamiento y otros recursos de hardware y software. Estas estrategias buscan optimizar el rendimiento del sistema, asegurar la equidad entre los usuarios, maximizar la utilización de los recursos y garantizar la estabilidad y seguridad del sistema.

#### ¿Qué son las funciones del administrador de memoria?
Las funciones del administrador de memoria incluyen:
1. **Asignación de Memoria**: Asignar bloques de memoria a procesos cuando lo requieran.
2. **Desasignación de Memoria**: Liberar la memoria cuando ya no es necesaria.
3. **Gestión del Espacio Libre**: Mantener un registro de las áreas de memoria libre.
4. **Paginación y Segmentación**: Implementar técnicas para gestionar la memoria virtual.
5. **Protección de Memoria**: Asegurar que los procesos no accedan a áreas de memoria asignadas a otros procesos.
6. **Compacción de Memoria**: Reorganizar la memoria para reducir la fragmentación.

#### Defina Memoria Virtual
La memoria virtual es una técnica de administración de memoria que permite a los programas utilizar más memoria que la físicamente disponible en el sistema. Lo logra usando una combinación de memoria física y espacio en disco, creando una "ilusión" de una gran cantidad de memoria disponible. La memoria virtual facilita la ejecución de programas grandes y mejora la utilización de la memoria física al cargar solo las partes necesarias de un programa en la memoria en un momento dado.

#### ¿Qué es la paginación?
La paginación es una técnica de gestión de memoria que divide la memoria física en bloques de tamaño fijo llamados marcos y la memoria lógica de los procesos en bloques de igual tamaño llamados páginas. Cuando un proceso necesita acceder a una página que no está en la memoria física, se produce un fallo de página y el sistema operativo carga la página necesaria desde el disco a un marco libre en la memoria.

#### ¿A qué se denomina fallo de página?
Un fallo de página ocurre cuando un proceso intenta acceder a una página que no está actualmente cargada en la memoria física. El sistema operativo debe entonces cargar la página requerida desde el almacenamiento secundario (como un disco duro) a la memoria principal, lo cual puede causar una interrupción y una demora en el procesamiento.

#### ¿Qué son tablas de página?
Las tablas de página son estructuras de datos utilizadas en la paginación para mantener un mapeo entre las direcciones lógicas de las páginas y las direcciones físicas de los marcos en la memoria. Cada entrada en una tabla de página contiene la dirección del marco en el que se encuentra la página correspondiente, junto con otros bits de control y estado.

---
### ARCHIVOS
#### ¿Qué son los archivos?
Los archivos son colecciones de datos relacionados que se almacenan en dispositivos de almacenamiento secundario (como discos duros, SSDs, etc.). Los archivos pueden contener programas, documentos, bases de datos, imágenes, y otros tipos de información, y se gestionan mediante sistemas de archivos.

#### ¿Qué es un sistema de archivos?
Un sistema de archivos es el componente del sistema operativo responsable de gestionar la creación, eliminación, lectura y escritura de archivos, así como de organizar y mantener la estructura de directorios. Proporciona una forma lógica de almacenar y organizar la información en dispositivos de almacenamiento.

#### ¿Cómo es la nomenclatura de los archivos?
La nomenclatura de los archivos se refiere a las reglas y convenciones utilizadas para nombrar archivos en un sistema de archivos. Esto incluye el uso de extensiones de archivo (como .txt, .jpg, .exe), restricciones en el uso de caracteres especiales, y la longitud máxima permitida para los nombres de archivos.

#### Nombre y describa brevemente los tipos de archivo
1. **Archivos Ordinarios**: Contienen datos de usuario y programas.
2. **Archivos de Directorio**: Contienen información sobre otros archivos y directorios.
3. **Archivos Especiales**: Utilizados para dispositivos de hardware y otros propósitos especiales, como archivos de dispositivo y tuberías.

#### Nombre y describa brevemente los tipos de acceso a los archivos
1. **Acceso Secuencial**: Los datos se leen o escriben de manera ordenada, uno tras otro.
2. **Acceso Directo**: Permite leer o escribir datos en cualquier orden, accediendo directamente a una ubicación específica del archivo.
3. **Acceso Indexado**: Utiliza una estructura de índice para acceder a los bloques de datos en un orden específico.

#### ¿Qué es un atributo de archivo? Nombre y escriba el significado de al menos 10.
Los atributos de archivo son metadatos asociados con un archivo que describen su estado y propiedades. Algunos atributos comunes son:
1. **Read-Only**: El archivo solo puede ser leído, no modificado.
2. **Hidden**: El archivo no se muestra en listados normales de directorios.
3. **System**: Indica que el archivo es crítico para el sistema operativo.
4. **Archive**: El archivo ha sido modificado desde la última copia de seguridad.
5. **Compressed**: El archivo está almacenado en formato comprimido para ahorrar espacio.
6. **Encrypted**: El archivo está cifrado para proteger su contenido.
7. **Temporary**: El archivo es temporal y puede ser eliminado cuando no se necesita.
8. **Sparse**: El archivo contiene grandes áreas vacías que no ocupan espacio en disco.
9. **Offline**: El archivo está archivado en almacenamiento secundario y no está disponible inmediatamente.
10. **Not Indexed**: El archivo no debe ser indexado por el servicio de búsqueda del sistema.

#### Explique brevemente las 11 operaciones que podemos realizar con los archivos
1. **Crear**: Generar un nuevo archivo vacío.
2. **Borrar**: Eliminar un archivo existente.
3. **Abrir**: Preparar un archivo para su lectura o escritura.
4. **Cerrar**: Terminar el acceso a un archivo abierto.
5. **Leer**: Extraer datos de un archivo.
6. **Escribir**: Insertar datos en un archivo.
7. **Repositionar**: Mover el puntero de lectura/escritura a una posición específica.
8. **Renombrar**: Cambiar el nombre de un archivo.
9. **Copiar**: Crear una copia del archivo en otra ubicación.
10. **Mover**: Transferir un archivo a otra ubicación.
11. **Atributos**: Consultar o modificar los atributos de un archivo.

#### ¿Qué es un Directorio?
Un directorio es una estructura que organiza y mantiene una colección de archivos y otros directorios. Los directorios permiten una organización jerárquica de los archivos, facilitando su acceso y gestión.

#### ¿A qué se le llama directorio raíz?
El directorio raíz es el nivel superior en la jerarquía de directorios de un sistema de archivos. Todos los demás archivos y directorios están contenidos, directa o indirectamente, dentro del directorio raíz.

#### Haga un diagrama de un sistema de directorios jerárquico
```
/
├── home
│   ├── usuario1
│   ├── usuario2
│   └── usuario3
├── etc
│   ├── passwd
│   ├── hosts
│   └── fstab
├── var
│   ├── log
│   ├── mail
│   └── www
└── usr
    ├── bin
    ├── lib
    └── share
```

#### ¿A qué se le denomina Ruta? Dé un ejemplo de una ruta típica de Windows y una de Linux
Una ruta es una cadena que describe la ubicación de un archivo o directorio en el sistema de archivos. Ejemplos:
- **Windows**: `C:\Users\Usuario\Documentos\archivo.txt`
- **Linux**: `/home/usuario/documentos/archivo.txt`

#### Nombre y describa las 8 operaciones que podemos realizar con los directorios
1. **Crear Directorio**: Generar un nuevo directorio.
2. **Eliminar Directorio**: Eliminar un directorio existente.
3. **Listar Directorios**: Mostrar el contenido de un directorio.
4. **Cambiar Directorio**: Moverse a otro directorio.
5. **Renombrar Directorio**: Cambiar el nombre de un directorio.
6. **Mover Directorio**: Transferir un directorio a otra ubicación.
7. **Copiar Directorio**: Crear una copia de un directorio.
8. **Consultar Atributos**: Ver los atributos de un directorio.

---
### Aplicación en Linux
#### ¿Qué es un sistema de archivo en Linux?
Un sistema de archivos en Linux es la estructura y el método que Linux utiliza para almacenar y organizar archivos en un disco. Ejemplos incluyen EXT4, XFS, Btrfs, etc.

#### ¿Qué es un sistema de archivos virtual en Linux?
Un sistema de archivos virtual (VFS) en Linux es una capa de abstracción que proporciona una interfaz unificada para diferentes sistemas de archivos. Facilita el acceso a archivos sin importar el tipo de sistema de archivos subyacente.

#### ¿Qué es un sistema de archivos extendido en Linux?
El sistema de archivos extendido en Linux (EXT) es una serie de sistemas de archivos que incluyen EXT2, EXT3 y EXT4, cada uno con mejoras sobre el anterior en términos de rendimiento, capacidad y características adicionales.

---
### Seguridad
#### ¿A qué se denomina UID y GID?
- **UID (User Identifier)**: Es un número único asignado a cada usuario en un sistema operativo, que se utiliza para identificar al usuario dentro del sistema. El UID determina los privilegios y permisos que el usuario tiene sobre los recursos del sistema.
- **GID (Group Identifier)**: Similar al UID, el GID es un número único asignado a un grupo de usuarios. Los GID se utilizan para gestionar los permisos de acceso y privilegios para grupos de usuarios, permitiendo que múltiples usuarios compartan acceso a los mismos recursos del sistema.

#### ¿Qué hace `chmod`?
El comando `chmod` (change mode) en sistemas Unix y Linux se utiliza para cambiar los permisos de acceso de los archivos y directorios. Este comando permite ajustar los permisos de lectura, escritura y ejecución para el propietario del archivo, el grupo y otros usuarios.

#### ¿Cuáles son las categorías de los permisos de un archivo?
Los permisos de un archivo en sistemas Unix y Linux se dividen en tres categorías:
1. **Permisos del Propietario**: Los derechos asignados al usuario que posee el archivo.
2. **Permisos del Grupo**: Los derechos asignados al grupo al que pertenece el archivo.
3. **Permisos para Otros**: Los derechos asignados a todos los demás usuarios.

#### Ejemplos de modo de protección de archivos en simbólico y qué acceso permite
- **Lectura (r)**: Permite ver el contenido del archivo.
- **Escritura (w)**: Permite modificar el contenido del archivo.
- **Ejecución (x)**: Permite ejecutar el archivo como un programa.

Ejemplo de modo de protección en simbólico:
- `rwxr-xr--`: El propietario tiene permisos de lectura, escritura y ejecución; el grupo tiene permisos de lectura y ejecución; otros tienen solo permisos de lectura.

#### Definir qué es superusuario y qué comando puedo usar para pasar de usuario a superusuario
- **Superusuario**: Es un usuario con privilegios elevados que tiene control total sobre el sistema operativo. En Unix y Linux, el superusuario se denomina generalmente `root`.
- **Comando para pasar a superusuario**: Se utiliza el comando `su` para cambiar al usuario `root`. Por ejemplo, `su -` permite cambiar al superusuario si se tiene la contraseña adecuada. Otra opción es `sudo` seguido del comando que se desea ejecutar con privilegios de superusuario, como en `sudo su` o `sudo <comando>`.




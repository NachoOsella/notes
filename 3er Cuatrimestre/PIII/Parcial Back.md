## 📚 Módulo 1: Introducción al Lenguaje Java

Java es un lenguaje de **alto nivel**, **orientado a objetos** y **portable** ("Escribe una vez, ejecuta en cualquier lugar") gracias a la **Máquina Virtual Java (JVM)**. El código fuente (`.java`) se compila a **bytecode** (`.class`), que la JVM interpreta para cada sistema operativo.

**Características Principales:**
1.  **Alto Nivel:** Sintaxis cercana al humano.
2.  **Portabilidad (JVM):** Código fuente (`.java`) → Compilador (`javac`) → Bytecode (`.class`) → JVM (Windows/Linux/macOS) → Ejecución.
3.  **Orientación a Objetos (POO):**
    *   **Clases y Objetos:** Clases son plantillas; objetos son instancias.
    *   **Encapsulamiento:** Ocultar detalles internos, proteger datos.
    *   **Herencia:** Subclases heredan de superclases, reutilizando código.
    *   **Polimorfismo:** Objetos de diferentes clases responden al mismo mensaje de forma específica.

**Java Development Kit (JDK):**
Incluye el compilador (`javac`), la JVM, bibliotecas de clases (API), y herramientas (debugger, Javadoc).

**Programa Mínimo `HolaMundo.java`:**
```java
public class HolaMundo {
    public static void main(String[] args) { // Punto de entrada
        System.out.println("Hola mundo!!!");
    }
}
```
Compilar: `javac HolaMundo.java` | Ejecutar: `java HolaMundo`

**Sintaxis Clave:**
*   Nombres de archivo coinciden con clase pública (`.java`).
*   Identificadores: `camelCase` (variables, métodos), `CamelCase` (clases), `CONST_CASE` (constantes).
*   Instrucciones terminan en `;`. Bloques en `{ }`.
*   Sensible a mayúsculas/minúsculas. Comentarios: `//`, `/* */`, `/** */`.

**Tipos de Datos:** (Fuertemente tipado)
1.  **Primitivos:** `byte`, `short`, `int` (común), `long`, `float`, `double` (común decimal), `char`, `boolean`.
2.  **Referencia (Objetos):**
    *   `String`: Secuencia de caracteres inmutable. Usa comillas dobles.
    *   Arrays, Clases propias, Tipos Envoltorio (e.g., `Integer` para `int`).
    *   Almacenan direcciones de memoria, pueden ser `null`.
3.  **Fechas Modernas:** `java.time.LocalDate`, `java.time.LocalTime`, `java.time.LocalDateTime`.

**Variables:**
*   Declaración: `tipo nombre;` Inicialización: `nombre = valor;`
*   **Ámbito (Scope):**
    *   **De Instancia:** En clase, fuera de método. Copia por objeto.
    *   **Local:** En método, existe solo ahí.
    *   **De Parámetro:** En firma de método.
    *   **De Bloque:** Dentro de `{}`.
    *   **Estáticas (De Clase):** Con `static`. Única copia para la clase.

**Operadores:**
*   **Aritméticos:** `+`, `-`, `*`, `/`, `%`.
*   **Asignación:** `=`, `+=`, `-=`, etc.
*   **Comparación:** `==`, `!=`, `>`, `<`, `>=`, `<=`.
*   **Lógicos:** `&&` (AND), `||` (OR), `!` (NOT).
*   **Incremento/Decremento:** `++`, `--` (pre y post).
*   **Ternario:** `condicion ? valorSiTrue : valorSiFalse;`

**Estructuras de Control:**
1.  **Selección:**
    *   `if`, `if-else`, `if-else if-else`.
    *   `switch`: Selección múltiple basada en valor. Usa `case`, `break`, `default`.
2.  **Repetición (Bucles):**
    *   `while`: 0 a N veces, condición al inicio.
    *   `do-while`: 1 a N veces, condición al final.
    *   `for (inicialización; condición; actualización)`: N veces conocido.

**Entrada/Salida Estándar:**
*   Salida: `System.out.print()`, `System.out.println()`.
*   Entrada: `Scanner teclado = new Scanner(System.in);`
    *   `teclado.nextLine()` (String), `teclado.nextInt()` (int), etc.
    *   Cerrar con `teclado.close()`. (Cuidado con `nextLine()` después de `nextInt()`).

---

## 🗃️ Módulo 2: Colecciones en Java

Estructuras para almacenar y manipular grupos de objetos.

**Arreglos (Arrays):**
*   Colección de **tamaño fijo** y **mismo tipo**.
*   Declaración: `int[] numeros;` Creación: `numeros = new int[5];`
*   Acceso por índice: `numeros[0]`. Propiedad `length`.
*   Multidimensionales: `int[][] matriz = new int[2][3];`.
*   Desventaja: Tamaño fijo, inserción/eliminación ineficiente.

**Framework de Colecciones:** Interfaces y clases.
*   Principales Interfaces: `Collection`, `List`, `Set`, `Map`, `Queue`.

**Listas (`List<E>`):** Colección **ordenada**, permite **duplicados**, acceso por **índice**, tamaño **dinámico**.
*   Métodos comunes: `add()`, `get()`, `remove()`, `size()`, `isEmpty()`, `contains()`.
*   Implementaciones:
    1.  **`ArrayList<E>`:** Basada en arreglo dinámico. Acceso `get()` rápido (O(1)). Inserción/eliminación en medio lenta (O(n)). Ideal para acceso frecuente por índice.
    2.  **`LinkedList<E>`:** Basada en lista doblemente enlazada. Inserción/eliminación en extremos rápida (O(1)). Acceso `get()` lento (O(n)). Ideal para frecuentes inserciones/eliminaciones.
    3.  `Vector<E>`: Legado, sincronizado (más lento). Preferir `ArrayList`.

**Mapas (`Map<K, V>`):** Pares **clave-valor**. **Claves únicas**. No hereda de `Collection`.
*   Métodos: `put()`, `get()`, `remove()`, `containsKey()`, `size()`, `keySet()`, `values()`, `entrySet()`.
*   Implementaciones:
    1.  **`HashMap<K, V>`:** Basado en tabla hash. Sin orden. Operaciones O(1) en promedio. Permite una clave `null`. Ideal para búsquedas rápidas sin orden.
    2.  **`TreeMap<K, V>`:** Basado en árbol Rojo-Negro. Ordenado por claves. Operaciones O(log n). No permite claves `null` (usualmente). Ideal si se necesita orden.
    3.  **`LinkedHashMap<K, V>`:** Tabla hash + lista enlazada. Mantiene orden de inserción. Rendimiento similar a `HashMap`.
    4.  `ConcurrentHashMap<K, V>`: Para entornos multihilo.

**Conjuntos (`Set<E>`):** **No permite duplicados**.
*   Método `add()` devuelve `false` si el elemento ya existe.
*   Implementaciones:
    1.  **`HashSet<E>`:** Basado en tabla hash. Sin orden. Operaciones O(1) en promedio. Permite un `null`. Ideal para unicidad rápida sin orden.
    2.  **`TreeSet<E>`:** Basado en árbol Rojo-Negro. Elementos ordenados. Operaciones O(log n). No permite `null` (usualmente). Ideal para unicidad ordenada.
    3.  **`LinkedHashSet<E>`:** Tabla hash + lista enlazada. Mantiene orden de inserción. Rendimiento similar a `HashSet`.

**¿Cómo elegir?**
*   ¿Clave-Valor? → Mapas.
*   ¿Duplicados? → Sí: Listas; No: Sets.
*   Listas: ¿Acceso por índice frecuente? → `ArrayList`. ¿Inserciones/eliminaciones frecuentes? → `LinkedList`.
*   Sets/Mapas: ¿Necesitas orden? → `TreeSet`/`TreeMap` (por clave), `LinkedHashSet`/`LinkedHashMap` (por inserción). ¿Sin orden y rápido? → `HashSet`/`HashMap`.

---

## 💡 Módulo 3: Algoritmos

Conjunto de **pasos ordenados y finitos** para resolver un problema.
*   Propiedades: Claro, Finito, Efectivo.

**Clasificación General:**
*   **Según Problema:** Búsqueda (Lineal, Binaria), Ordenamiento (Bubble, Merge, Quick).
*   **Según Operación:** Iterativos (bucles), Recursivos (se llaman a sí mismos).

**Complejidad de Algoritmos:** Mide recursos (tiempo, espacio) vs. tamaño de entrada (`n`).
*   **Notación Big O (O Grande):** Tasa de crecimiento del tiempo/espacio para `n` grande (peor caso).
    *   `O(1)`: Constante (ej. `array[i]`).
    *   `O(log n)`: Logarítmica (ej. Búsqueda Binaria).
    *   `O(n)`: Lineal (ej. Búsqueda Lineal).
    *   `O(n log n)`: Loglineal (ej. Merge Sort).
    *   `O(n²)`: Cuadrática (ej. Bucles anidados simples, Bubble Sort).
    *   `O(2ⁿ)`: Exponencial (ej. Fibonacci recursivo ingenuo).
    *   `O(n!)`: Factorial (ej. Viajante por fuerza bruta).

**Malos Diseños Comunes:**
*   No usar estructura de datos adecuada (ej. buscar en array en vez de `HashSet`).
*   Recorridos innecesarios o bucles anidados ineficientes.

**Búsqueda Lineal vs. Binaria:**
*   **Lineal:** `O(n)`. No requiere orden.
*   **Binaria:** `O(log n)`. **Requiere datos ordenados.** Mucho más eficiente para grandes colecciones.

**Fibonacci:** `F(n) = F(n-1) + F(n-2)`
*   **Recursivo Ingenuo:** `O(2ⁿ)` - muy ineficiente por recálculos.
*   **Programación Dinámica:** `O(n)` - almacena resultados intermedios (memoización o tabulación) para evitar recálculos. Mucho más eficiente.

**Estrategias de Resolución:**
1.  **Divide and Conquer:** Dividir, resolver subproblemas, combinar (ej. Merge Sort, Búsqueda Binaria).
2.  **Backtracking:** Construir solución paso a paso, retroceder si no es válida (ej. Sudokus).
3.  **Greedy (Voraces):** Decisión localmente óptima esperando óptimo global (ej. Dijkstra).
4.  **Dynamic Programming:** Resolver subproblemas superpuestos guardando resultados (ej. Fibonacci optimizado).

---

## 🧪 Módulo 4: Testing (Anexo)

Proceso para evaluar un sistema y asegurar que funcione correctamente.
*   **Objetivo:** Identificar errores (bugs).
*   **Buena Prueba:** Objetiva, Reproducible, Relevante, Precisa, Completa.

**Tipos de Testing (Principales):**
1.  **Pruebas Unitarias:** Prueban la unidad más pequeña (método/clase) aisladamente.
2.  **Pruebas de Integración:** Prueban interacción entre módulos.
3.  **Pruebas de Sistema:** Prueban el sistema completo.
4.  **Pruebas de Aceptación (UAT):** Realizadas por el cliente/usuario.
5.  **Pruebas de Regresión:** Verifican que cambios no rompan lo existente.

**Herramientas: JUnit y Mockito**

**JUnit (Pruebas Unitarias en Java):**
*   Clase de prueba con métodos anotados con `@Test`.
*   **Aserciones:** Verifican condiciones (ej. `assertEquals(esperado, actual)`).
*   Anotaciones comunes: `@Test`, `@BeforeEach` (antes de cada test), `@AfterEach` (después de cada test), `@BeforeAll` (una vez antes de todos), `@AfterAll` (una vez después de todos), `@Disabled`.

**Mockito (Simulación de Objetos - Mocks/Spies):**
Para aislar la unidad bajo prueba de sus dependencias.
*   **Mock 👻:** Objeto simulado que reemplaza dependencia real. Comportamiento configurable (`when(...).thenReturn(...)`).
*   **Spy 🕵️:** Objeto real "parcialmente simulado". Mantiene comportamiento original, pero métodos específicos pueden ser stubeados.
*   Anotaciones clave:
    *   `@Mock`: Crea un mock.
    *   `@Spy`: Crea un spy (necesita instancia real).
    *   `@InjectMocks`: Crea instancia de clase a probar e inyecta mocks/spies.
*   Configuración: `when(mock.metodo()).thenReturn(valor);`
*   Verificación: `verify(mock).metodo(argumentos);` (usar `anyString()`, `anyInt()` para argumentos flexibles).

**Pruebas en Métodos Privados:**
*   Generalmente **no se recomienda**. Probar a través de la interfaz pública.
*   Si es necesario: Reflection API (con precaución, frágil).

---

## 🏗️ Módulo 5: Maven (Anexo N°3)

Herramienta de **automatización de construcción** y **gestión de proyectos** Java.
*   **POM (`pom.xml`):** Corazón de Maven. Archivo XML que describe el proyecto, dependencias, plugins, etc.
    *   Coordenadas: `groupId`, `artifactId`, `version`.
    *   `packaging`: `jar`, `war`, etc.
*   **Gestión de Dependencias:** Descarga y administra bibliotecas (JARs) automáticamente.
*   **Repositorios:** Lugares donde se almacenan artefactos.
    *   **Local:** (`.m2/repository`) Caché en tu máquina.
    *   **Remoto:** (ej. Maven Central) De donde se descargan.
*   **Ciclo de Vida (Lifecycle):** Secuencia de fases (ej. `compile`, `test`, `package`, `install`, `deploy`). Al ejecutar una fase, se ejecutan las anteriores.
    *   `default`: Para construir. `clean`: Para limpiar. `site`: Para documentación.
*   **Plugins:** Realizan tareas (goals) vinculadas a fases (ej. `maven-compiler-plugin`).

**Instalación (con SDKMAN):**
`sdk install maven <version>` (ej. `sdk install maven 3.9.0`).
Verificar con `mvn -version`.

**Conceptos Clave:**
*   **Dependencias en `pom.xml`:**
    ```xml
    <dependencies>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-api</artifactId>
            <version>5.10.0</version>
            <scope>test</scope> <!-- Alcance (test, compile, provided, runtime) -->
        </dependency>
    </dependencies>
    ```
*   **`dependencyManagement`:** Para gestionar versiones de dependencias en POMs padres.
*   **Plugins en `pom.xml`:**
    ```xml
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>11</source> <!-- Versión Java fuente -->
                    <target>11</target> <!-- Versión Java bytecode -->
                </configuration>
            </plugin>
        </plugins>
    </build>
    ```
*   **Arquetipos (Archetypes):** Plantillas para crear nuevos proyectos (`mvn archetype:generate`).
*   **`settings.xml`:** Configuración global/usuario (repositorios privados, proxies).

Maven estandariza la construcción, gestiona dependencias y facilita la colaboración.
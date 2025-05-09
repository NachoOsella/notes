# 📚 Resumen Programación III - FRONT END (Guía para Parcial)

## 📌 Unidad Temática 1: HTML, CSS y Javascript

### 🌐 Introducción a HTML

**¿Qué es HTML?**

*   **HTML (HyperText Markup Language)**: Es el lenguaje **estándar** para crear la **estructura** de las páginas web. No es un lenguaje de programación, sino de *marcado*.
*   **HyperText**: Capacidad de enlazar documentos (navegación).
*   **Markup Language**: Usa **etiquetas** (`<tag>`) para definir la estructura y el significado del contenido.

> 💡 **Analogía Clave:** Piensa en HTML como los **cimientos y el esqueleto** de una casa. Define dónde van las paredes, puertas, ventanas, pero no cómo se ven (eso es CSS) ni cómo funcionan (eso es JavaScript).

**🧱 Estructura básica de un documento HTML:**

Todo documento HTML5 moderno necesita esta estructura mínima:

```html
<!DOCTYPE html> <!-- Declara que usamos HTML5 -->
<html lang="es"> <!-- Contenedor raíz, 'lang' indica el idioma -->
<head>
    <meta charset="UTF-8"> <!-- Codificación de caracteres (¡Importante!) -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- Para diseño responsivo -->
    <title>Título de la Página</title> <!-- Aparece en la pestaña del navegador -->
    <link rel="stylesheet" href="styles.css"> <!-- Enlace a hoja de estilos CSS (opcional) -->
    <!-- Aquí van otros metadatos, enlaces a scripts (con defer/async), etc. -->
</head>
<body>
    <!-- Aquí va TODO el contenido VISIBLE de la página -->
    <h1>Hola Mundo</h1>
    <p>Este es un párrafo.</p>
    <!-- Más elementos: imágenes, enlaces, listas, tablas, formularios... -->
    <script src="script.js"></script> <!-- Enlace a archivo JavaScript (a menudo al final del body) -->
</body>
</html>
```

**Explicación Paso a Paso:**

1.  `<!DOCTYPE html>`: Siempre al inicio, define la versión de HTML.
2.  `<html>`: Envuelve todo el contenido. El atributo `lang` mejora la accesibilidad y SEO.
3.  `<head>`: Contiene **información sobre el documento**, no visible directamente.
    *   `meta charset`: Fundamental para que se muestren bien los caracteres especiales (acentos, ñ). UTF-8 es el estándar.
    *   `meta name="viewport"`: Clave para que la página se adapte a dispositivos móviles (responsive).
    *   `<title>`: Texto de la pestaña del navegador y marcador.
    *   `<link rel="stylesheet">`: Conecta el HTML con el archivo CSS que le dará estilo.
4.  `<body>`: Contiene **todo el contenido visible** para el usuario: texto, imágenes, etc.
    *   `<script src="...">`: Usualmente se coloca aquí, justo antes de cerrar `</body>`, para que el HTML se cargue primero y el script pueda manipular elementos ya existentes.

> ✨ **Punto Clave (HTML Estructura):** La estructura básica con `DOCTYPE`, `html`, `head`, y `body` es **obligatoria**. El `head` es para metadatos y enlaces, el `body` para el contenido visible. ¡No olvides `charset="UTF-8"` y `viewport`!

---

### 🏷️ Principales Etiquetas HTML

HTML tiene muchas etiquetas, pero estas son fundamentales:

**1. Estructurales:**

*   `<html>`, `<head>`, `<body>`: Ya vistas, definen la estructura global.

**2. Texto:**

*   `<h1>` a `<h6>`: **Encabezados** o Títulos. `<h1>` es el más importante (generalmente uno por página), `<h6>` el menos importante. Definen jerarquía.
*   `<p>`: **Párrafo**. Para bloques de texto.
*   `<br>`: **Salto de línea**. Úsalo con moderación, el espaciado se controla mejor con CSS.
*   `<hr>`: **Línea horizontal**. Separa visualmente secciones temáticas.

**3. Enlaces e Imágenes:**

*   `<a>`: **Ancla (Hipervínculo)**. Crea enlaces.
    *   **Atributo `href`**: **Obligatorio**. Indica la URL de destino (otra página, un archivo, un email, etc.).
    *   **Contenido**: El texto o imagen clickeable.
    ```html
    <a href="https://www.ejemplo.com">Visitar Ejemplo</a>
    <a href="pagina2.html">Ir a Página 2</a>
    <a href="#seccion-abajo">Ir a una sección</a>
    <a href="mailto:info@ejemplo.com">Enviar correo</a>
    ```
*   `<img>`: **Imagen**. Incrusta una imagen.
    *   **Atributo `src`**: **Obligatorio**. Ruta (URL) de la imagen.
    *   **Atributo `alt`**: **Muy Recomendado**. Texto alternativo si la imagen no carga (importante para accesibilidad y SEO).
    *   **Atributos `width` y `height` (opcionales):** Definen tamaño (mejor hacerlo con CSS).
    ```html
    <img src="logo.png" alt="Logo de la empresa">
    <img src="https://via.placeholder.com/150" alt="Imagen de ejemplo">
    ```

> ✨ **Punto Clave (Etiquetas Básicas):** Domina `h1-h6`, `p`, `a` (con `href`) e `img` (con `src` y `alt`). Son la base para mostrar contenido y navegar.

---

### 🧩 Etiquetas Semánticas

Son etiquetas HTML que **describen el significado** de su contenido, no solo su apariencia.

**¿Por qué usarlas?**

*   ♿ **Accesibilidad:** Ayudan a lectores de pantalla a entender la estructura.
*   📈 **SEO:** Facilitan a los motores de búsqueda indexar el contenido relevante.
*   🧹 **Código Limpio:** Hacen el HTML más legible y mantenible que usar solo `<div>` y `<span>`.

**Principales Etiquetas Semánticas:**

*   `<header>`: Cabecera de la página o de una sección (logo, título principal, menú principal).
*   `<nav>`: Contiene la **navegación principal** (menú de enlaces).
*   `<main>`: **Contenido principal y único** de la página. Debe haber **solo uno** por página.
*   `<article>`: Contenido **independiente y autocontenido** (post de blog, noticia, producto). Puede tener su propio `<header>` y `<footer>`.
*   `<section>`: Agrupa contenido **temáticamente relacionado**. Usualmente tiene un encabezado (`h2`-`h6`).
*   `<aside>`: Contenido **secundario o tangencial** (barra lateral, anuncios, biografía del autor).
*   `<footer>`: Pie de página del documento o sección (copyright, enlaces secundarios, contacto).

**Ejemplo de Estructura Semántica:**

```html
<body>
    <header>
        <h1>Mi Sitio Web</h1>
        <nav>
            <ul>
                <li><a href="#">Inicio</a></li>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <article>
            <h2>Título del Artículo</h2>
            <p>Contenido del artículo...</p>
        </article>

        <section>
            <h2>Sección Relacionada</h2>
            <p>Contenido de la sección...</p>
        </section>
    </main>

    <aside>
        <h3>Publicidad</h3>
        <p>Anuncio aquí.</p>
    </aside>

    <footer>
        <p>&copy; 2023 Mi Sitio Web</p>
    </footer>
</body>
```

> ✨ **Punto Clave (Semántica):** **Usa etiquetas semánticas siempre que sea posible**. Ayudan a todos (navegadores, buscadores, desarrolladores, usuarios con lectores de pantalla) a entender tu contenido. Reemplaza `div` genéricos por `<header>`, `<nav>`, `<main>`, etc., cuando aplique.

---

### 🎨 CSS (Cascading Style Sheets)

**¿Qué es CSS?**

*   Es el lenguaje para **definir la presentación y el estilo** de los documentos HTML.
*   Separa el **contenido (HTML)** de la **presentación (CSS)**.

**Ventajas:**

*   🧹 **Separación de responsabilidades:** HTML para estructura, CSS para estilo.
*   ♻️ **Reutilización:** Define un estilo una vez, aplícalo a muchos elementos.
*   ⚡ **Rendimiento:** Estilos en archivo único se cachean mejor.
*   📐 **Consistencia:** Apariencia uniforme en todo el sitio.

**🎯 Selectores CSS:**

Indican a qué elementos HTML aplicar los estilos. ¡Son clave!

1.  **Selector de Tipo (Elemento):** Aplica a todas las etiquetas de ese tipo.
    ```css
    p {
      color: blue; /* Todas las etiquetas <p> tendrán texto azul */
    }
    ```
2.  **Selector de Clase (`.`):** Aplica a todos los elementos con ese atributo `class`. **¡El más usado y recomendado para estilos reutilizables!**
    ```css
    .destacado { /* Elementos con class="destacado" */
      font-weight: bold;
      background-color: yellow;
    }
    ```
    ```html
    <p class="destacado">Texto importante.</p>
    <span class="destacado">Otro texto.</span>
    ```
3.  **Selector de ID (`#`):** Aplica a UN ÚNICO elemento con ese atributo `id`. **Úsalo con moderación**, principalmente para identificar elementos únicos (ej: para JavaScript o anclas internas), no tanto para estilos generales.
    ```css
    #menu-principal { /* El elemento con id="menu-principal" */
      border: 1px solid black;
    }
    ```
    ```html
    <nav id="menu-principal">...</nav>
    ```
4.  **Selector de Atributo:** Selecciona elementos basados en sus atributos y/o valores.
    ```css
    input[type="text"] { /* Inputs de tipo texto */
      border: 1px solid gray;
    }
    a[target="_blank"] { /* Enlaces que abren en nueva pestaña */
      background-image: url('external-link.png');
    }
    ```

> **Consejo Profe:** Para una buena arquitectura CSS, **prioriza las clases (`.clase`)** para aplicar estilos. Son reutilizables y flexibles. Reserva los IDs (`#id`) para identificar elementos únicos que necesitarás en JavaScript o para navegación interna.

**🔧 Propiedades CSS Comunes:**

Definen CÓMO se verá el elemento seleccionado.

*   `color`: Color del texto.
*   `background-color`: Color de fondo.
*   `font-size`: Tamaño del texto.
*   `font-family`: Tipo de fuente (letra).
*   `font-weight`: Grosor del texto (e.g., `bold`).
*   `text-align`: Alineación del texto (`left`, `center`, `right`).
*   `width`: Ancho del elemento.
*   `height`: Alto del elemento.
*   `margin`: Espacio **exterior** al borde del elemento (separa de otros elementos).
*   `padding`: Espacio **interior** entre el contenido y el borde del elemento.
*   `border`: Borde alrededor del elemento (grosor, estilo, color).

**Ejemplo:**

```css
h1 {
  color: #333; /* Color de texto gris oscuro */
  font-family: Arial, sans-serif; /* Fuente Arial, si no está, una genérica sans-serif */
  text-align: center; /* Texto centrado */
}

.boton-primario {
  background-color: blue;
  color: white;
  padding: 10px 20px; /* 10px arriba/abajo, 20px izq/der */
  border: none;
  margin-top: 15px; /* Margen superior de 15px */
}
```

> ✨ **Punto Clave (CSS Básico):** Entiende la **relación Selector -> Propiedad -> Valor**. Domina los selectores básicos (clase, ID, tipo) y las propiedades comunes para controlar colores, fuentes, tamaño y espaciado.

---

### 📦 El Modelo de Caja (Box Model)

¡Fundamental para entender el layout en CSS! **Todo elemento HTML se representa como una caja rectangular.**

Esta caja tiene 4 capas (de adentro hacia afuera):

1.  **Content (Contenido):** El texto, imagen u otro contenido real del elemento. Su tamaño se define con `width` y `height`.
2.  **Padding (Relleno):** Espacio transparente **entre el contenido y el borde**. Aumenta el tamaño visible de la caja.
3.  **Border (Borde):** Línea que rodea el padding y el contenido. También aumenta el tamaño total de la caja.
4.  **Margin (Margen):** Espacio transparente **fuera del borde**. Separa esta caja de otras cajas/elementos. No forma parte del tamaño visible de la caja en sí, pero afecta el espacio alrededor.

**Visualización:**

```
+-------------------------------------+
| Margin                              |
|   +-----------------------------+   |
|   | Border                      |   |
|   |   +---------------------+   |   |
|   |   | Padding             |   |   |
|   |   |   +---------------+   |   |   |
|   |   |   | Content       |   |   |   |
|   |   |   +---------------+   |   |   |
|   |   |                     |   |   |
|   |   +---------------------+   |   |
|   |                             |   |
|   +-----------------------------+   |
|                                     |
+-------------------------------------+
```

**Ejemplo CSS:**

```css
.mi-caja {
  width: 200px;        /* Ancho del contenido */
  height: 100px;       /* Alto del contenido */
  padding: 20px;       /* Relleno de 20px en todos los lados */
  border: 5px solid red; /* Borde rojo sólido de 5px */
  margin: 30px;        /* Margen de 30px en todos los lados */
  background-color: lightblue; /* Color de fondo del área de contenido + padding */
}
```

> ⚠️ **Importante:** Por defecto (`box-sizing: content-box`), el `width` y `height` definen solo el área del *contenido*. El tamaño total ocupado por la caja será `width + padding-left + padding-right + border-left + border-right`. A menudo se usa `box-sizing: border-box;` para que `width` y `height` incluyan el padding y el borde, simplificando los cálculos de layout.

> ✨ **Punto Clave (Box Model):** ¡Entender Content, Padding, Border, Margin es **CRUCIAL** para posicionar y dimensionar elementos! Controla cómo interactúan visualmente. Recuerda `box-sizing: border-box;` como un truco útil.

---

### 📱 Diseño Responsivo (Responsive Design)

Permite que un sitio web se **adapte automáticamente** a diferentes tamaños de pantalla (móviles, tablets, escritorio). ¡Esencial hoy en día!

**Técnicas Clave:**

1.  **Media Queries:** Aplican estilos CSS **solo si se cumplen ciertas condiciones**, generalmente relacionadas con el tamaño de la pantalla.
    ```css
    /* Estilos base (móvil primero) */
    .columna {
      width: 100%; /* Ocupa todo el ancho en pantallas pequeñas */
    }

    /* Estilos para pantallas medianas (tablets) y más grandes */
    @media (min-width: 768px) {
      .columna {
        width: 50%; /* Dos columnas en pantallas medianas */
        float: left; /* O usar Flexbox/Grid */
      }
    }

    /* Estilos para pantallas grandes (escritorio) y más grandes */
    @media (min-width: 1024px) {
      .columna {
        width: 33.33%; /* Tres columnas en pantallas grandes */
      }
    }
    ```
    *   `min-width`: Aplica estilos si el ancho es *igual o mayor* al valor.
    *   `max-width`: Aplica estilos si el ancho es *igual o menor* al valor.

2.  **Unidades Relativas:** Unidades que se definen en relación a otra cosa, permitiendo que los tamaños se ajusten proporcionalmente.
    *   `%`: Porcentaje del elemento contenedor padre.
    *   `vw` (Viewport Width): Porcentaje del ancho de la ventana del navegador. `1vw` = 1% del ancho.
    *   `vh` (Viewport Height): Porcentaje del alto de la ventana. `1vh` = 1% del alto.
    *   `em`: Relativo al tamaño de fuente del *elemento actual* o del *padre*. `2em` = doble del tamaño de fuente.
    *   `rem` (Root em): Relativo al tamaño de fuente del **elemento raíz** (`<html>`). **Más predecible que `em` para layouts generales.**

**Ejemplo con Unidades Relativas:**

```css
body {
  font-size: 16px; /* Tamaño base */
}

h1 {
  font-size: 2rem; /* 2 * 16px = 32px */
}

.contenedor-fluido {
  width: 90%;     /* 90% del ancho del padre */
  max-width: 1200px; /* Pero no más de 1200px */
  margin: 0 auto; /* Centrado horizontal */
}

.banner-completo {
  height: 50vh; /* Ocupa la mitad del alto de la ventana */
  width: 100vw; /* Ocupa todo el ancho de la ventana */
}
```

> ✨ **Punto Clave (Responsivo):** Usa **Media Queries** para cambiar drásticamente el layout en puntos de quiebre (breakpoints) y **Unidades Relativas** (especialmente `rem` y `%`) para que los elementos escalen fluidamente. El enfoque "Mobile First" (diseñar primero para móvil y luego añadir estilos para pantallas más grandes con `min-width`) es muy popular.

---

### 💨 Introducción a Tailwind CSS

**¿Qué es Tailwind CSS?**

*   Es un **framework de CSS utility-first**. En lugar de darte componentes pre-hechos (como Bootstrap), te da **clases de utilidad** de bajo nivel que aplicas directamente en tu HTML.
*   **No escribes casi CSS propio.** Combinas clases de Tailwind para construir diseños únicos.

**Beneficios Clave:**

*   🎨 **Personalización Total:** No estás limitado por estilos de componentes predefinidos.
*   ⚡ **Desarrollo Rápido:** Prototipado y construcción muy ágiles aplicando clases directamente.
*   📱 **Responsivo Sencillo:** Usa prefijos (`sm:`, `md:`, `lg:`) en las clases para aplicar estilos en diferentes tamaños de pantalla.
*   🧹 **Mantenimiento Fácil:** Los estilos están junto al HTML, menos necesidad de grandes archivos CSS y evita duplicación.

**Instalación (Opción Rápida CDN):**

Para prototipos o pruebas rápidas, puedes incluirlo desde un CDN en tu `<head>`:

```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
<!-- O la URL de la versión más reciente que encuentres -->
```

> **Nota:** Para proyectos reales, se recomienda la instalación local con NPM/Yarn para poder configurarlo, optimizarlo (PurgeCSS) y usar todas sus características.

**Ejemplo Básico con Tailwind:**

```html
<body class="bg-gray-100 font-sans">
  <div class="container mx-auto p-4"> <!-- Contenedor centrado con padding -->
    <h1 class="text-2xl font-bold text-blue-700 mb-4"> <!-- Título grande, negrita, azul, margen inferior -->
      Bienvenido a Tailwind
    </h1>
    <button class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
      <!-- Botón verde, blanco, padding, redondeado, cambio de color al pasar el mouse (hover) -->
      Haz Clic
    </button>
  </div>
</body>
```

> ✨ **Punto Clave (Tailwind Intro):** Tailwind es **diferente**. No pienses en escribir CSS, piensa en **combinar clases de utilidad** en tu HTML. `bg-color`, `text-size`, `font-weight`, `p-spacing`, `m-spacing`, etc.

---

### 🔑 Conceptos Clave de Tailwind CSS

1.  **Clases de Utilidad:** Cada clase aplica **una única regla CSS**.
    *   `p-4` -> `padding: 1rem;`
    *   `text-center` -> `text-align: center;`
    *   `font-bold` -> `font-weight: 700;`
    *   `bg-red-500` -> `background-color: #ef4444;` (El número 500 indica la intensidad del color).
    *   **¡La clave es aprender las clases más comunes!** La documentación oficial es tu mejor amiga.

2.  **Prefijos Responsivos:** Aplican una utilidad **solo a partir de cierto tamaño de pantalla**.
    *   `sm:` (>= 640px)
    *   `md:` (>= 768px)
    *   `lg:` (>= 1024px)
    *   `xl:` (>= 1280px)
    *   `2xl:` (>= 1536px)

    **Ejemplo:** Un div que es rojo en móvil, azul en tablet y verde en escritorio.
    ```html
    <div class="bg-red-500 md:bg-blue-500 lg:bg-green-500">...</div>
    <!-- Por defecto (móvil) es rojo. A partir de 'md' es azul. A partir de 'lg' es verde. -->
    ```
    **Ejemplo:** Texto centrado en móvil, a la izquierda en pantallas medianas o más grandes.
    ```html
    <p class="text-center md:text-left">Mi texto</p>
    ```

3.  **Prefijos de Estado (Hover, Focus, etc.):** Aplican estilos en ciertos estados.
    *   `hover:`: Al pasar el mouse por encima.
    *   `focus:`: Cuando el elemento (ej: input, botón) tiene el foco.
    *   `active:`: Mientras se está haciendo clic.
    *   `disabled:`: Para elementos deshabilitados.

    **Ejemplo:** Botón que cambia de color al pasar el mouse.
    ```html
    <button class="bg-blue-500 hover:bg-blue-700 text-white ...">
      Botón
    </button>
    ```

4.  **Flexbox y Grid:** Tailwind tiene excelentes utilidades para Flexbox y Grid.
    *   `flex`, `inline-flex`, `items-center`, `justify-between`, etc.
    *   `grid`, `grid-cols-3`, `gap-4`, `col-span-2`, etc.

    **Ejemplo Flexbox:** Centrar elementos vertical y horizontalmente.
    ```html
    <div class="flex items-center justify-center h-screen">
      Contenido Centrado
    </div>
    ```
    **Ejemplo Grid:** Una cuadrícula de 3 columnas con espacio entre ellas.
    ```html
    <div class="grid grid-cols-3 gap-4">
      <div>Col 1</div>
      <div>Col 2</div>
      <div>Col 3</div>
      <!-- ... más elementos ... -->
    </div>
    ```

> ✨ **Punto Clave (Tailwind Core):** Domina la sintaxis `prefijo:utilidad` (e.g., `md:text-lg`, `hover:bg-red-700`). Aprende las utilidades más comunes para layout (Flex/Grid, padding, margin), texto, colores y bordes. La **combinación** de estas clases es lo que crea tu diseño.

---

### <0xF0><0x9F><0xA7><0xAE> JavaScript Básico

**¿Qué es JavaScript (JS)?**

*   Es un lenguaje de programación **de alto nivel, dinámico y no tipado** (aunque TypeScript añade tipado estático).
*   Se ejecuta **principalmente en el navegador del cliente**. (También en servidor con Node.js).
*   Permite añadir **interactividad y dinamismo** a las páginas web.

**¿Qué puede hacer en el navegador?**

*   🖱️ **Manipular el DOM:** Cambiar contenido HTML, atributos y estilos *después* de que la página se cargó.
*   🎬 **Responder a Eventos:** Reaccionar a acciones del usuario (clics, teclado, formularios).
*   🔄 **Realizar Peticiones Asíncronas (AJAX/Fetch):** Comunicarse con servidores para obtener o enviar datos *sin recargar la página*.

**Modelo de Programación:**

*   Orientado a Objetos **basado en prototipos** (aunque ES6 introdujo sintaxis `class` que es azúcar sintáctica sobre prototipos). Los objetos heredan directamente de otros objetos.

> **Nota para estudiantes Java:** JavaScript es muy diferente a Java. Es **dinámicamente tipado** (no declaras tipos de variables `int`, `String`, etc., explícitamente), y su modelo de objetos (prototipos) es distinto al de clases de Java. ¡Cuidado con asumir que funcionan igual!

**📝 Sintaxis Básica:**

**1. Declaración de Variables:**

*   `let`: Para variables que **pueden cambiar** de valor. Tienen **alcance de bloque** (`{}`). **Recomendada.**
*   `const`: Para variables cuyo valor **no cambiará** (constantes). También tiene **alcance de bloque**. **Recomendada** siempre que sepas que el valor no cambiará.
*   `var`: La forma antigua. Tiene **alcance de función**, lo que puede causar confusiones. **Evítala en código moderno.**

```javascript
let edad = 30;
edad = 31; // Válido

const nombre = "Ana";
// nombre = "Elena"; // Inválido, daría error

var ciudad = "Córdoba"; // Trata de no usar var
```

**2. Tipos de Datos Primitivos:**

*   `String`: Cadenas de texto ("Hola", 'Mundo', \`Plantilla ${variable}\`).
*   `Number`: Números (enteros o decimales: 42, 3.14).
*   `Boolean`: Verdadero o falso (`true`, `false`).
*   `null`: Representa la ausencia intencional de un valor de objeto.
*   `undefined`: Indica que una variable ha sido declarada pero no inicializada.
*   `Symbol` (ES6): Identificadores únicos.
*   `BigInt` (ES2020): Para números enteros muy grandes.

**3. Objetos (Object):** Colección de pares clave-valor (propiedades).

```javascript
const persona = {
  nombre: "Juan",
  edad: 25,
  esEstudiante: true,
  saludar: function() { // Métodos (funciones dentro de objetos)
    console.log("Hola, soy " + this.nombre);
  }
};

console.log(persona.nombre); // Acceso a propiedad: Juan
persona.saludar(); // Llamada al método: Hola, soy Juan
```

**4. Operadores:**

*   **Aritméticos:** `+`, `-`, `*`, `/`, `%` (módulo), `**` (exponenciación ES6).
*   **Asignación:** `=`, `+=`, `-=`, `*=`, `/=`.
*   **Comparación:**
    *   `==` (Igualdad **con conversión de tipo** - ¡EVITARLA!): `'5' == 5` -> `true` (peligroso).
    *   `===` (Igualdad **estricta**, sin conversión de tipo): `'5' === 5` -> `false`. **¡USA SIEMPRE ESTA!**
    *   `!=` (Desigualdad con conversión).
    *   `!==` (Desigualdad estricta). **¡USA SIEMPRE ESTA!**
    *   `>`, `<`, `>=`, `<=`.
*   **Lógicos:**
    *   `&&` (AND): `true && false` -> `false`.
    *   `||` (OR): `true || false` -> `true`.
    *   `!` (NOT): `!true` -> `false`.

**Ejemplo Java vs JavaScript (Comparación):**

```java
// Java (Estático, tipos declarados)
int edadJava = 30;
String nombreJava = "Ana";
if (edadJava == 30) { /*...*/ }

// JavaScript (Dinámico, tipos inferidos)
let edadJS = 30;
const nombreJS = "Ana";
if (edadJS === 30) { /*...*/ } // Usar ===
```

> ✨ **Punto Clave (JS Syntax):** Usa `let` y `const`. Entiende los tipos básicos. **Usa siempre `===` y `!==` para comparaciones.** Los objetos son colecciones clave-valor muy flexibles.

---

### ⚙️ Estructuras de Control y Funciones en JS

**1. Condicionales:**

*   `if...else if...else`: Ejecuta bloques de código según condiciones.
    ```javascript
    let nota = 7;
    if (nota >= 9) {
      console.log("Sobresaliente");
    } else if (nota >= 5) {
      console.log("Aprobado");
    } else {
      console.log("Suspendido");
    }
    ```
*   `switch`: Evalúa una expresión contra múltiples `case`. ¡No olvides el `break`!
    ```javascript
    let dia = "Lunes";
    switch (dia) {
      case "Lunes":
        console.log("Inicio de semana");
        break; // ¡Importante! Si no, sigue al siguiente case
      case "Viernes":
        console.log("Casi finde");
        break;
      default:
        console.log("Otro día");
    }
    ```

**2. Bucles (Loops):**

*   `for`: Repite un bloque un número determinado de veces.
    ```javascript
    for (let i = 0; i < 5; i++) {
      console.log("Iteración número: " + i);
    }
    ```
*   `while`: Repite mientras una condición sea verdadera.
    ```javascript
    let contador = 0;
    while (contador < 3) {
      console.log("Contador: " + contador);
      contador++;
    }
    ```
*   `do...while`: Similar a `while`, pero ejecuta el bloque **al menos una vez** antes de chequear la condición.
    ```javascript
    let j = 5;
    do {
      console.log("Valor de j: " + j); // Se ejecuta aunque j no sea < 5
      j++;
    } while (j < 5);
    ```
*   `for...of` (ES6): Itera sobre los **valores** de objetos iterables (Arrays, Strings, Maps, Sets).
    ```javascript
    const colores = ["rojo", "verde", "azul"];
    for (const color of colores) {
      console.log(color); // Imprime "rojo", "verde", "azul"
    }
    ```
*   `for...in`: Itera sobre las **claves (propiedades)** de un objeto. (Usar con cuidado, puede iterar sobre propiedades heredadas).
    ```javascript
    const coche = { marca: "Ford", modelo: "Fiesta" };
    for (const propiedad in coche) {
      console.log(propiedad + ": " + coche[propiedad]); // Imprime "marca: Ford", "modelo: Fiesta"
    }
    ```

**3. Funciones:** Bloques de código reutilizables.

*   **Función Declarada:**
    ```javascript
    function sumar(a, b) {
      return a + b;
    }
    let resultado = sumar(5, 3); // resultado es 8
    ```
*   **Expresión de Función (Anónima):** Asigna una función a una variable.
    ```javascript
    const restar = function(a, b) {
      return a - b;
    };
    let resultadoResta = restar(10, 4); // resultadoResta es 6
    ```
*   **Arrow Functions (Funciones Flecha - ES6):** Sintaxis más concisa. Tienen un comportamiento diferente con `this` (no tienen su propio `this`, heredan el del contexto exterior).
    ```javascript
    // Versión larga
    const multiplicar = (a, b) => {
      return a * b;
    };

    // Versión corta (si solo hay un return)
    const dividir = (a, b) => a / b;

    // Versión corta con un solo parámetro
    const cuadrado = x => x * x;

    let resMult = multiplicar(2, 6); // 12
    let resDiv = dividir(10, 2);     // 5
    let resCuad = cuadrado(4);       // 16
    ```

> ✨ **Punto Clave (JS Control y Funciones):** Domina `if/else`, `for`, `while`. Aprende a usar `for...of` para arrays. Conoce los 3 tipos de funciones, especialmente las *Arrow Functions* por su concisión y uso extendido en JS moderno.

---
---

## 📌 Unidad Temática 2: Arquitectura - DOM – FETCH API

### 🏛️ Modelo Cliente-Servidor

Es la **arquitectura fundamental de la web**. Dos actores principales:

1.  **Cliente:**
    *   **Quién es:** El dispositivo/software que **solicita** recursos (Navegador web, app móvil).
    *   **Qué hace:** Envía **peticiones HTTP** (ej: GET para una página, POST para enviar datos), recibe respuestas, **renderiza** HTML/CSS, ejecuta JavaScript.
2.  **Servidor:**
    *   **Quién es:** La computadora/software que **proporciona** los recursos (Servidor físico, servicio en la nube como AWS, software como Apache/Nginx).
    *   **Qué hace:** **Escucha** peticiones HTTP, las **procesa** (puede buscar archivos, consultar bases de datos, ejecutar lógica de negocio con Python, Java, PHP, Node.js), y envía **respuestas HTTP**.

**🔄 Proceso de Comunicación Típico (GET):**

1.  **Cliente (Navegador):** Escribe `www.ejemplo.com` -> Navegador envía una **Solicitud HTTP GET** al servidor de `ejemplo.com`.
    ```http
    GET /index.html HTTP/1.1
    Host: www.ejemplo.com
    ... (otros encabezados) ...
    ```
2.  **Servidor:** Recibe la solicitud, busca el archivo `index.html`.
3.  **Servidor:** Envía una **Respuesta HTTP** con el contenido del archivo y un código de estado.
    ```http
    HTTP/1.1 200 OK
    Content-Type: text/html
    ... (otros encabezados) ...

    <!DOCTYPE html>... (contenido del archivo HTML) ...
    ```
4.  **Cliente (Navegador):** Recibe la respuesta, interpreta (renderiza) el HTML/CSS y ejecuta el JS.

> ✨ **Punto Clave (Cliente-Servidor):** Toda interacción web se basa en este modelo: el **Cliente pide**, el **Servidor responde**. HTTP es el idioma que usan para comunicarse.

---

### 🔥 Servidores Web y Protocolo HTTP

**🖥️ ¿Qué es un Servidor Web?**

*   Es el **software** (o hardware+software) que **atiende las solicitudes HTTP** de los clientes.
*   **Funciones:**
    *   Escuchar peticiones en puertos específicos (usualmente 80 para HTTP, 443 para HTTPS).
    *   Encontrar y entregar los recursos solicitados (archivos HTML, CSS, JS, imágenes).
    *   (En sitios dinámicos) Pasar la petición a una aplicación backend para procesarla.
*   **Ejemplos Populares:** Apache, Nginx (muy común como proxy inverso), IIS (Microsoft), Caddy.

**📜 Protocolo HTTP (HyperText Transfer Protocol):**

*   El protocolo **base** para la comunicación en la web. Define cómo se formatean y transmiten los mensajes (peticiones y respuestas).
*   **Modelo Petición/Respuesta:** El cliente inicia, el servidor contesta.
*   **Stateless (Sin Estado):** Cada petición es independiente. El servidor no recuerda peticiones anteriores del mismo cliente (se usan cookies o tokens para mantener sesiones).

**⚙️ Métodos HTTP Principales (Verbos):** Indican la acción deseada sobre un recurso.

*   `GET`: **Solicitar/Leer** un recurso (ej: cargar una página, obtener datos). Seguro e idempotente.
*   `POST`: **Enviar datos** para crear un nuevo recurso o procesar datos (ej: enviar un formulario, crear un usuario). No es seguro ni idempotente.
*   `PUT`: **Actualizar completamente** un recurso existente (reemplaza todo el recurso). Idempotente.
*   `DELETE`: **Eliminar** un recurso. Idempotente.
*   `PATCH`: **Actualizar parcialmente** un recurso. No necesariamente idempotente.

**📊 Códigos de Estado HTTP:** Indican el resultado de la petición. ¡Crucial entenderlos!

*   **`1xx` (Informativos):** Petición recibida, continuando proceso. (Raros de ver directamente).
*   **`2xx` (Éxito):** La petición fue exitosa.
    *   `200 OK`: Éxito general (para GET, PUT, PATCH, DELETE).
    *   `201 Created`: Recurso creado exitosamente (para POST que crea algo).
    *   `204 No Content`: Éxito, pero no hay contenido para devolver (para DELETE).
*   **`3xx` (Redirección):** Se necesita acción adicional para completar la petición.
    *   `301 Moved Permanently`: El recurso se movió permanentemente a otra URL.
    *   `302 Found`: Redirección temporal.
    *   `304 Not Modified`: El recurso no ha cambiado desde la última vez (usado con caché).
*   **`4xx` (Error del Cliente):** La petición tiene un error o no se puede cumplir.
    *   `400 Bad Request`: Petición malformada o inválida.
    *   `401 Unauthorized`: No autenticado (falta iniciar sesión o token inválido).
    *   `403 Forbidden`: Autenticado, pero sin permisos para acceder al recurso.
    *   `404 Not Found`: **¡El más famoso!** El recurso solicitado no existe en el servidor.
*   **`5xx` (Error del Servidor):** El servidor falló al intentar cumplir una petición válida.
    *   `500 Internal Server Error`: Error genérico del servidor (un bug en el backend, por ejemplo).
    *   `503 Service Unavailable`: El servidor no está listo para manejar la petición (sobrecargado, en mantenimiento).

> ✨ **Punto Clave (HTTP):** Conoce los **métodos principales (GET, POST, PUT, DELETE)** y su propósito. Familiarízate con los **códigos de estado más comunes (200, 201, 400, 401, 403, 404, 500)** para diagnosticar problemas.

---

### ⚖️ Sitios Estáticos y Dinámicos

**1. 📜 Sitios Estáticos:**

*   **Qué son:** Compuestos por archivos fijos (HTML, CSS, JS, imágenes) que **no cambian** a menos que el desarrollador los modifique manualmente.
*   **Cómo funcionan:** El servidor simplemente **envía los archivos tal cual están** al navegador. No hay procesamiento en tiempo real ni bases de datos involucradas en la entrega.
*   **Características:**
    *   🚀 **Rápidos y Sencillos:** Carga muy rápida, fáciles de alojar (hosting simple, a veces gratuito como GitHub Pages, Netlify).
    *   🔒 **Seguros:** Menor superficie de ataque al no tener backend complejo ni DB.
    *   📉 **Menos recursos de servidor:** No requieren procesamiento intenso.
*   **Ejemplos de uso:** Páginas de documentación, portfolios, sitios informativos simples, landing pages.
*   **Flujo:** Cliente pide -> Servidor encuentra archivo -> Servidor envía archivo.

**2. 🚀 Sitios Dinámicos:**

*   **Qué son:** Generan contenido **en tiempo real** en el servidor, a menudo usando bases de datos y lógica de programación backend. El contenido puede variar según el usuario, la hora, interacciones, etc.
*   **Cómo funcionan:** El servidor recibe la petición, ejecuta código (PHP, Python, Java, Node.js), consulta una base de datos, **genera el HTML dinámicamente** y lo envía al navegador.
*   **Características:**
    *   🤝 **Interactividad:** Permiten login de usuarios, comentarios, personalización, etc.
    *   🔄 **Contenido Actualizado:** Muestran información en tiempo real (noticias, redes sociales, e-commerce).
    *   ⚙️ **Requieren Backend:** Necesitan un lenguaje de servidor, base de datos y un entorno de ejecución.
    *   ⏳ **Más Lentos (potencialmente):** El procesamiento en servidor añade latencia comparado con servir archivos estáticos.
*   **Ejemplos de uso:** Redes sociales, tiendas online, blogs con CMS, aplicaciones web complejas.
*   **Flujo (Simplificado):** Cliente pide -> Servidor pasa a Aplicación Web -> App consulta DB -> App genera HTML -> Servidor envía HTML.

**Comparación Rápida:**

| Característica  | Sitio Estático                     | Sitio Dinámico                       |
| :-------------- | :--------------------------------- | :----------------------------------- |
| **Contenido**   | Fijo (archivos pre-creados)        | Generado en tiempo real              |
| **Interactividad**| Limitada (solo frontend con JS)    | Alta (login, formularios, DB)        |
| **Hosting**     | Simple, servidor de archivos       | Complejo, servidor con backend/DB    |
| **Rendimiento** | Muy rápido                         | Depende del procesamiento            |
| **Backend**     | No requiere                        | Requerido (PHP, Java, Python...)     |
| **Ejemplos**    | Docs, Portfolios, Landing Pages  | Redes Sociales, E-commerce, Blogs    |

> ✨ **Punto Clave (Estático vs Dinámico):** La diferencia clave es **dónde y cuándo se genera el HTML**. Estático = archivos fijos enviados. Dinámico = HTML creado en el servidor por petición. Elige según la necesidad de interactividad y contenido actualizado.

---

### 🌳 DOM (Document Object Model)

**¿Qué es el DOM?**

*   Es una **interfaz de programación** (API) para documentos HTML y XML.
*   Representa la **estructura de la página como un árbol de objetos (nodos)**. Cada etiqueta HTML, atributo y texto se convierte en un nodo en este árbol.
*   **No es JavaScript**, es un estándar W3C. JavaScript es el lenguaje que usamos *en el navegador* para **acceder y manipular** este árbol del DOM.

**¿Por qué surgió?**

*   Para permitir que las páginas web fueran **dinámicas** (DHTML) sin recargar la página completa.
*   Inicialmente, cada navegador tenía su forma (incompatible) de acceder a elementos (`document.all` en IE, `document.layers` en Netscape).
*   El DOM estándar unificó la forma de interactuar con la estructura del documento.

**Analogía:** El DOM es como el **mapa genealógico** de tu página HTML. `<html>` es el ancestro común, `<head>` y `<body>` son hijos, y así sucesivamente hasta las hojas (texto, imágenes). JavaScript puede usar este mapa para encontrar un "familiar" (nodo) y cambiarle el nombre (contenido), el color de pelo (estilo), etc.

**De lo Abstracto a lo Concreto:**

*   El **estándár DOM** es abstracto.
*   En el **navegador**, JavaScript interactúa con la implementación concreta del DOM a través del objeto global `document`.
*   Métodos como `document.getElementById()`, `document.querySelector()` permiten obtener referencias a nodos específicos.
*   Cada nodo es un objeto JS con propiedades (`.textContent`, `.style`, `.id`) y métodos (`.appendChild()`, `.remove()`, `.addEventListener()`).

**Relación con Arquitecturas (MVC):**

*   En patrones como **Modelo-Vista-Controlador (MVC)**, el DOM es la **Vista** (lo que el usuario ve).
*   JavaScript actúa como el **Controlador**, manipulando la Vista (DOM) en respuesta a eventos o cambios en el Modelo (datos).
*   Frameworks modernos (React, Angular, Vue) abstraen la manipulación directa del DOM (usan Virtual DOM, etc.) para mejorar rendimiento y organización, pero *al final*, siempre terminan modificando el DOM real del navegador.

> ✨ **Punto Clave (DOM):** El DOM es la **representación en memoria (como un árbol de objetos)** de tu HTML. JavaScript lo usa para **leer y modificar dinámicamente** la página *después* de que se haya cargado. ¡Entender su estructura de árbol es fundamental!

---

### 🛠️ Manipulación del DOM con JavaScript

Aquí es donde JavaScript brilla en el frontend: cambiar la página dinámicamente.

**1. 🔍 Acceso a Elementos (Nodos):** Cómo obtener una referencia a un elemento HTML en tu JS.

*   **Métodos Modernos (Recomendados):**
    *   `document.querySelector(selectorCSS)`: Devuelve el **primer** elemento que coincide con el selector CSS especificado. ¡Muy potente!
    *   `document.querySelectorAll(selectorCSS)`: Devuelve una **NodeList (estática)** con **todos** los elementos que coinciden. Se puede iterar sobre ella.
    *   `elemento.querySelector()` y `elemento.querySelectorAll()`: Buscan *dentro* de un elemento específico, no en todo el documento.
    ```javascript
    // Obtener el primer elemento con la clase 'mi-clase'
    const primerElemento = document.querySelector('.mi-clase');

    // Obtener el elemento con id 'principal'
    const elemPrincipal = document.querySelector('#principal'); // Equivale a getElementById

    // Obtener todos los párrafos dentro del div con id 'contenido'
    const divContenido = document.querySelector('#contenido');
    const parrafos = divContenido.querySelectorAll('p');

    // Iterar sobre los párrafos
    parrafos.forEach(p => {
      console.log(p.textContent);
    });
    ```
*   **Métodos Tradicionales (Menos flexibles, algunos devuelven colecciones "vivas"):**
    *   `document.getElementById(id)`: Obtiene el elemento por su `id`. Rápido y específico.
    *   `document.getElementsByClassName(clase)`: Devuelve una `HTMLCollection` (viva) de elementos con esa clase.
    *   `document.getElementsByTagName(nombreTag)`: Devuelve una `HTMLCollection` (viva) de elementos con ese nombre de etiqueta.

> **Importante:** Las `HTMLCollection` devueltas por `getElementsByClassName` y `getElementsByTagName` son "vivas", se actualizan automáticamente si el DOM cambia. `NodeList` de `querySelectorAll` es "estática". Esto puede ser fuente de errores si no se tiene en cuenta al iterar y modificar. `querySelector` y `querySelectorAll` son generalmente preferibles por usar selectores CSS y devolver resultados más predecibles.

**2. ✨ Crear y Agregar Elementos:**

*   `document.createElement(nombreTag)`: Crea un nuevo nodo de elemento (ej: `p`, `div`, `li`).
*   `nodo.textContent = "texto"`: Establece el contenido de texto de un nodo.
*   `nodo.innerHTML = "html"`: Establece el contenido HTML (¡Cuidado con XSS si viene de usuario!).
*   `padre.appendChild(hijo)`: Agrega `hijo` como el **último** hijo de `padre`.
*   **Métodos Modernos para Insertar:**
    *   `padre.append(nodo1, nodo2, ...)`: Agrega nodos o texto al final de `padre`.
    *   `padre.prepend(nodo1, nodo2, ...)`: Agrega nodos o texto al principio de `padre`.
    *   `nodo.before(nodoNuevo)`: Inserta `nodoNuevo` antes de `nodo`.
    *   `nodo.after(nodoNuevo)`: Inserta `nodoNuevo` después de `nodo`.
    *   `nodo.replaceWith(nodoNuevo)`: Reemplaza `nodo` con `nodoNuevo`.
*   `nodo.remove()`: Elimina el nodo del DOM.

**Ejemplo: Crear y agregar un `<li>` a una lista `<ul>`:**

```javascript
// HTML: <ul id="miLista"></ul>

// 1. Obtener referencia a la lista padre
const lista = document.querySelector('#miLista');

// 2. Crear el nuevo elemento <li>
const nuevoItem = document.createElement('li');

// 3. Añadir contenido al <li>
nuevoItem.textContent = 'Nuevo elemento de lista';

// 4. Agregar el <li> a la <ul>
lista.appendChild(nuevoItem); // O lista.append(nuevoItem);
```

**3. 🔧 Modificar Atributos y Propiedades:**

*   **Propiedades Directas:** Muchos atributos HTML tienen propiedades DOM correspondientes. Es la forma preferida.
    ```javascript
    const imagen = document.querySelector('#miImagen');
    imagen.src = 'nueva-imagen.jpg'; // Modifica el atributo src
    imagen.alt = 'Nueva descripción'; // Modifica el atributo alt
    imagen.className = 'clase1 clase2'; // Reemplaza todas las clases
    ```
*   **`classList`:** API moderna y cómoda para manejar clases CSS.
    ```javascript
    const miDiv = document.querySelector('.miDiv');
    miDiv.classList.add('activo'); // Añade la clase 'activo'
    miDiv.classList.remove('oculto'); // Quita la clase 'oculto'
    miDiv.classList.toggle('seleccionado'); // Añade 'seleccionado' si no está, la quita si está
    if (miDiv.classList.contains('importante')) { ... } // Verifica si tiene una clase
    ```
*   **Métodos `getAttribute`, `setAttribute`, `removeAttribute`:** Para atributos estándar o personalizados (especialmente `data-*`).
    ```javascript
    const enlace = document.querySelector('a');
    enlace.setAttribute('href', 'https://nuevo-destino.com');
    enlace.setAttribute('target', '_blank');
    let destino = enlace.getAttribute('href');
    enlace.removeAttribute('target');

    // Atributos data-* (dataset)
    const usuario = document.querySelector('#user');
    // HTML: <div id="user" data-user-id="123" data-role="admin">...</div>
    console.log(usuario.dataset.userId); // "123" (acceso fácil con .dataset)
    console.log(usuario.dataset.role);   // "admin"
    usuario.dataset.userStatus = 'active'; // Añade/modifica data-user-status="active"
    ```
*   **Estilos (`.style`):** Para modificar estilos CSS directamente (inline). Menos recomendado que usar clases CSS, pero útil para cambios dinámicos específicos.
    ```javascript
    const titulo = document.querySelector('h1');
    titulo.style.color = 'red';
    titulo.style.backgroundColor = 'yellow'; // Propiedades CSS con guion se escriben en camelCase
    titulo.style.fontSize = '2em';
    ```

**4. 🧭 Recorrido del DOM (Navegación):** Moverse entre nodos relacionados.

*   `nodo.parentNode` / `nodo.parentElement`: El nodo/elemento padre.
*   `nodo.childNodes`: `NodeList` de **todos** los nodos hijos (incluye texto, comentarios).
*   `nodo.children`: `HTMLCollection` solo de los nodos hijos que son **elementos HTML**. ¡Más útil generalmente!
*   `nodo.firstChild` / `nodo.lastChild`: Primer/último nodo hijo (puede ser texto).
*   `nodo.firstElementChild` / `nodo.lastElementChild`: Primer/último **elemento** hijo.
*   `nodo.nextSibling` / `nodo.previousSibling`: Siguiente/anterior nodo hermano (puede ser texto).
*   `nodo.nextElementSibling` / `nodo.previousElementSibling`: Siguiente/anterior **elemento** hermano.

**🚀 Consejo de Rendimiento:** Las operaciones de lectura/escritura en el DOM son costosas (pueden forzar al navegador a recalcular estilos y layout - *reflow/repaint*). **Minimízalas:**
*   Guarda referencias a nodos en variables si los vas a usar varias veces.
*   Si vas a añadir muchos elementos, créalos todos primero (idealmente en un `DocumentFragment`) y añádelos al DOM de una sola vez.
*   Evita modificar estilos dentro de bucles intensivos.

**Ejemplo Completo (Lista de Tareas - Adaptado):**
(Este ejemplo es intrínsecamente de frontend JS, una traducción a Java no tendría sentido práctico en este contexto)

```html
<!DOCTYPE html>
<html>
<head><title>Lista de Tareas</title></head>
<body>
    <h1>Mis Tareas</h1>
    <input type="text" id="nuevaTarea" placeholder="Escribe una tarea...">
    <button id="agregarBtn">Agregar</button>
    <ul id="listaTareas">
        <!-- Las tareas se agregarán aquí -->
    </ul>

    <script>
        // 1. Obtener referencias a elementos importantes
        const inputNuevaTarea = document.getElementById('nuevaTarea');
        const botonAgregar = document.getElementById('agregarBtn');
        const listaUL = document.getElementById('listaTareas');

        // 2. Función para agregar una tarea
        function agregarTarea() {
            const textoTarea = inputNuevaTarea.value.trim(); // Obtener texto y quitar espacios extra

            if (textoTarea === "") {
                alert("Por favor, escribe una tarea."); // Validación simple
                return; // No hacer nada si está vacío
            }

            // Crear nuevo elemento <li>
            const nuevoLI = document.createElement('li');
            nuevoLI.textContent = textoTarea;

            // (Opcional) Añadir botón para eliminar la tarea
            const botonEliminar = document.createElement('button');
            botonEliminar.textContent = ' X';
            botonEliminar.style.marginLeft = '10px'; // Estilo simple
            botonEliminar.onclick = function() {
                listaUL.removeChild(nuevoLI); // O nuevoLI.remove();
            };
            nuevoLI.appendChild(botonEliminar);


            // Añadir el <li> a la <ul>
            listaUL.appendChild(nuevoLI);

            // Limpiar el input para la siguiente tarea
            inputNuevaTarea.value = "";
            inputNuevaTarea.focus(); // Poner el foco de nuevo en el input
        }

        // 3. Asociar la función al evento 'click' del botón
        botonAgregar.addEventListener('click', agregarTarea);

        // (Opcional) Permitir agregar tarea presionando Enter en el input
        inputNuevaTarea.addEventListener('keyup', function(event) {
            if (event.key === 'Enter') { // Si la tecla presionada fue Enter
                agregarTarea();
            }
        });

        // (Opcional) Cargar tareas iniciales o guardadas (localStorage)
        // ...

    </script>
</body>
</html>
```

**Explicación del Ejemplo:**

1.  **Selección:** Obtenemos referencias al input, al botón y a la lista `<ul>` usando `getElementById`.
2.  **Función `agregarTarea`:**
    *   Lee el valor del input usando `.value` y lo limpia con `.trim()`.
    *   Valida que no esté vacío.
    *   Crea un nuevo elemento `<li>` con `createElement`.
    *   Asigna el texto leído a la propiedad `.textContent` del `<li>`.
    *   *Extra:* Crea un botón 'X', le asigna una función `onclick` para eliminar el `<li>` (usando `removeChild` o el más moderno `.remove()`), y lo añade al `<li>`.
    *   Añade el `<li>` completo a la `<ul>` con `appendChild`.
    *   Limpia el input (`.value = ""`) y le devuelve el foco (`.focus()`) para facilitar la entrada de la siguiente tarea.
3.  **Event Listener (Botón):** Usamos `addEventListener` para llamar a `agregarTarea` cuando se hace clic en el botón `agregarBtn`.
4.  **Event Listener (Input - Enter):** Añadimos otro listener al input que escucha el evento `keyup`. Si la tecla presionada es 'Enter', también llama a `agregarTarea`.

**❌ Errores Comunes en Manipulación DOM:**

*   **Selección Incorrecta:** Usar mal los selectores (`getElementById` vs `querySelector`, mayúsculas/minúsculas, sintaxis CSS).
*   **DOM no Cargado:** Intentar acceder a un elemento *antes* de que el navegador lo haya creado (ej: script en `<head>` sin `defer` o sin esperar a `DOMContentLoaded`). Solución: Poner scripts al final de `<body>` o usar `defer` / `DOMContentLoaded`.
*   **Modificaciones Ineficientes:** Cambiar el DOM muchas veces dentro de un bucle. Agrupa cambios (DocumentFragment).
*   **Confundir Propiedades vs Atributos:** Intentar leer `div.value` (no existe) en lugar de `input.value`.
*   **Memory Leaks:** Añadir event listeners y no quitarlos (`removeEventListener`) cuando el elemento se elimina, especialmente en SPAs (Single Page Applications).

> ✨ **Punto Clave (Manipulación DOM):** El flujo es: **Seleccionar -> Crear/Modificar -> Añadir/Quitar**. Usa `querySelector/All`, `createElement`, `textContent/innerHTML`, `append/remove`, `classList`. ¡Piensa en el rendimiento y maneja los errores comunes!

---

### 🎉 Manejo de Eventos en la Web

Los eventos son **acciones o sucesos** que ocurren en la página (clics, teclas presionadas, carga de página, etc.) a los que tu código JavaScript puede **reaccionar**.

**Contexto:**

*   **Patrón Observer:** Los elementos DOM (sujetos) *emiten* eventos. Tu código JS *registra* listeners (observadores) para ser notificado.
*   **Historia:** Atributos inline (`onclick="..."`) -> Métodos específicos de navegador (`attachEvent` vs `addEventListener`) -> Estándar DOM Level 2 (`addEventListener`).
*   **Forma Moderna Recomendada:** `elemento.addEventListener(tipoEvento, funcionManejadora, opciones)`

**🌊 Fases del Evento y Flujo (Event Flow):** ¡Importante entender esto para eventos anidados!

Cuando un evento ocurre en un elemento dentro de otros (ej: clic en un botón dentro de un div dentro del body), el navegador sigue 3 fases:

1.  **⬇️ Fase de Captura (Capturing):** El evento "baja" desde `window` -> `document` -> `html` -> `body` -> ... hasta el elemento donde ocurrió (*target*). Los listeners registrados para la fase de captura se ejecutan en este descenso.
2.  **🎯 Fase de Objetivo (Target):** El evento llega al elemento específico donde ocurrió la acción. Los listeners adjuntos directamente a este elemento se ejecutan.
3.  **⬆️ Fase de Burbujeo (Bubbling):** El evento "sube" de vuelta desde el *target* hacia `window`. Los listeners registrados para la fase de burbujeo (¡la **predeterminada**!) se ejecutan en este ascenso.

**Visualización:**

```
      Window
        | (Captura ↓)
      Document
        |
      HTML
        |
      BODY
        |
      DIV
        | (Evento ocurre aquí: TARGET)
      BUTTON  <---- Clic!
        | (Burbujeo ↑)
      DIV
        |
      BODY
        |
      HTML
        |
      Document
        |
      Window
```

*   Por defecto, `addEventListener` escucha en la fase de **burbujeo**.
*   Puedes escuchar en la fase de **captura** pasando `true` como tercer argumento: `el.addEventListener('click', func, true);` o `{ capture: true }`.

**🖱️⌨️📄 Eventos Comunes:**

*   **Ratón:**
    *   `click`: Clic simple.
    *   `dblclick`: Doble clic.
    *   `mousedown`/`mouseup`: Botón presionado/soltado.
    *   `mouseover`/`mouseout`: Puntero entra/sale del elemento (¡burbujea!).
    *   `mouseenter`/`mouseleave`: Puntero entra/sale del elemento (¡no burbujea! - a menudo más útil).
    *   `mousemove`: Puntero se mueve sobre el elemento.
*   **Teclado:**
    *   `keydown`: Tecla presionada.
    *   `keyup`: Tecla soltada.
    *   `keypress`: (Obsoleto) Para teclas que producen caracteres.
*   **Formulario:**
    *   `submit`: Se intenta enviar el formulario (¡importante `preventDefault()` para validación JS!).
    *   `change`: Valor de input/select/textarea cambia *y pierde el foco*.
    *   `input`: Valor de input/textarea cambia (*más inmediato* que `change`).
    *   `focus`/`blur`: Elemento recibe/pierde el foco.
    *   `reset`: Formulario reseteado.
*   **Documento/Ventana:**
    *   `load`: Toda la página (HTML, CSS, JS, imágenes) ha terminado de cargar. Se usa en `window`.
    *   `DOMContentLoaded`: El HTML se ha cargado y parseado, el árbol DOM está listo (no espera CSS/imágenes). ¡Más rápido y a menudo suficiente! Se usa en `document`.
    *   `resize`: Tamaño de la ventana del navegador cambia. Se usa en `window`.
    *   `scroll`: Usuario desplaza la página. Se usa en `window` o elementos con scroll.
    *   `beforeunload`: Justo antes de que el usuario abandone la página (para avisos de "datos sin guardar").

**➕ Agregar y Quitar Manejadores (Listeners):**

```javascript
const miBoton = document.querySelector('#miBoton');

// Función manejadora (puede ser nombrada o anónima)
function handleClick() {
  console.log('¡Botón clickeado!');
}

// Agregar listener (fase de burbujeo por defecto)
miBoton.addEventListener('click', handleClick);

// Agregar listener en fase de captura
// miBoton.addEventListener('click', handleCaptureClick, true);

// Quitar listener (¡NECESITAS la referencia a la MISMA función!)
// miBoton.removeEventListener('click', handleClick);
// Por esto, las funciones nombradas son mejores si necesitas quitar listeners.
```

**🎯 Delegación de Eventos:** Técnica avanzada y eficiente.

*   **Problema:** Si tienes muchos elementos (ej: 100 botones en una lista) o elementos que se añaden dinámicamente, añadir un listener a cada uno es ineficiente.
*   **Solución:** Añade **UN SOLO listener al contenedor padre**. Dentro del manejador, usa el `event.target` para saber qué hijo específico disparó el evento.

**Ejemplo Delegación:** Manejar clics en items de una lista.

```html
<ul id="listaItems">
    <li>Item 1 <button class="eliminar">X</button></li>
    <li>Item 2 <button class="eliminar">X</button></li>
    <!-- Más items, quizás añadidos dinámicamente -->
</ul>

<script>
    const lista = document.getElementById('listaItems');

    lista.addEventListener('click', function(event) {
        // event.target es el elemento EXACTO donde se hizo clic (podría ser el <li> o el <button>)
        console.log('Clic en:', event.target);

        // Verificar si el clic fue en un botón con clase 'eliminar'
        if (event.target.classList.contains('eliminar')) {
            console.log('Eliminando item...');
            const itemAEliminar = event.target.closest('li'); // Encuentra el <li> padre más cercano
            if (itemAEliminar) {
                itemAEliminar.remove();
            }
        }
    });
</script>
```

**Ventajas Delegación:** Mejor rendimiento, funciona con elementos añadidos después, código más limpio.

**🎁 Objeto `event`:**

Cuando se dispara un evento, la función manejadora recibe automáticamente un objeto `event` con información útil:

*   `event.target`: El elemento **donde originalmente ocurrió** el evento (el más profundo).
*   `event.currentTarget`: El elemento **al que está adjunto el listener** (útil en delegación o si el listener está en un padre).
*   `event.type`: El tipo de evento que se disparó (ej: `"click"`, `"keydown"`).
*   `event.key` / `event.code`: (Eventos de teclado) La tecla presionada.
*   `event.clientX` / `event.clientY`: (Eventos de ratón) Coordenadas del puntero relativas a la ventana.
*   `event.preventDefault()`: **¡Método crucial!** **Evita el comportamiento por defecto** del navegador para ese evento (ej: evita que un formulario se envíe, que un enlace navegue). Esencial para validaciones JS, SPAs.
*   `event.stopPropagation()`: **Detiene la propagación** del evento (ya sea en fase de captura o burbujeo). Úsalo con cuidado, puede romper funcionalidades esperadas.

**Ejemplo `preventDefault`:** Validar un formulario antes de enviarlo.

```javascript
const miForm = document.querySelector('#miForm');
const emailInput = document.querySelector('#email');

miForm.addEventListener('submit', function(event) {
  // Validar el email
  if (!emailInput.value.includes('@')) {
    alert('Email inválido');
    event.preventDefault(); // ¡Evita que el formulario se envíe!
  }
  // Si la validación pasa, no se llama a preventDefault y el formulario se envía.
});
```

**❌ Errores Comunes en Eventos:**

*   **Olvidar `preventDefault()`:** Especialmente en `submit` de formularios o clics en enlaces que manejas con JS. La página se recargará inesperadamente.
*   **Confundir `target` y `currentTarget`:** Especialmente en delegación. `target` es donde se hizo clic, `currentTarget` es donde pusiste el listener.
*   **Memory Leaks:** No quitar listeners con `removeEventListener` cuando ya no se necesitan (ver Manipulación DOM).
*   **Problemas con `this`:** El valor de `this` dentro de un manejador puede variar (si usas funciones normales vs arrow functions). Las arrow functions suelen simplificar esto al heredar el `this` del contexto donde se definen.

> ✨ **Punto Clave (Eventos):** Usa `addEventListener`. Entiende el flujo **Captura-Target-Burbujeo**. Conoce los eventos comunes. Usa el objeto `event` (especialmente `target`, `preventDefault`). Considera la **delegación** para listas o elementos dinámicos.

---

### 📡 Fetch API (Peticiones HTTP desde el Navegador)

Permite a JavaScript **realizar peticiones HTTP asíncronas** para comunicarse con servidores (APIs) y obtener/enviar datos **sin recargar la página**. Es la evolución moderna de AJAX.

**¿Qué es y por qué usar Fetch?**

*   Interfaz **moderna y basada en Promesas** del navegador.
*   Reemplaza al antiguo y más complejo `XMLHttpRequest`.
*   Fundamental para crear **SPAs (Single Page Applications)** y aplicaciones web interactivas que cargan datos dinámicamente.

**Contexto y REST:**

*   Fetch se usa comúnmente para interactuar con **APIs REST**.
*   **REST (Representational State Transfer):** Estilo arquitectónico para APIs web. Usa métodos HTTP (GET, POST, PUT, DELETE) para operar sobre "recursos" (representados por URLs). Generalmente usa **JSON** como formato de datos.
*   **Buenas Prácticas REST:** Peticiones stateless, uso correcto de verbos HTTP y códigos de estado.

**Analogía:** Fetch es como **pedir comida a domicilio por teléfono (pero sin bloquear tu día)**.
1.  Preparas tu pedido (`fetch` con URL, método, headers, body).
2.  Llamas al restaurante (envías la petición).
3.  Sigues con tu vida (el código JS sigue ejecutándose - **asíncrono**).
4.  El restaurante (servidor) prepara el pedido.
5.  El repartidor (respuesta) llega. Primero te da el **recibo (`Response` object)**.
6.  Miras el recibo: ¿Está todo OK? (`response.ok`, `response.status`).
7.  Abres la bolsa para ver la comida (llamas a `response.json()` o `response.text()` para obtener el **cuerpo/body**). Esto también toma un momentito (es otra promesa).
8.  ¡Disfrutas de la comida (usas los datos)!
9.  Si hubo un problema con el restaurante (`500`) o el repartidor no llegó (error de red), manejas el error (`.catch()`).

**Uso Básico (GET y procesar JSON):**

```javascript
const apiUrl = 'https://api.ejemplo.com/usuarios/1';

fetch(apiUrl) // Por defecto, fetch hace una petición GET
  .then(response => {
    // --- PASO 1: Chequear si la respuesta HTTP fue exitosa (200-299) ---
    if (!response.ok) {
      // Si no fue OK (ej: 404, 500), lanzamos un error para que lo capture el .catch()
      throw new Error(`Error HTTP: ${response.status}`);
    }
    // --- PASO 2: Convertir el cuerpo de la respuesta a JSON ---
    // response.json() también devuelve una Promesa
    return response.json();
  })
  .then(data => {
    // --- PASO 3: Usar los datos JSON recibidos ---
    console.log('Datos del usuario:', data);
    // Aquí actualizarías el DOM con los datos
  })
  .catch(error => {
    // --- PASO 4: Manejar errores (de red o los lanzados manualmente) ---
    console.error('Error al obtener datos:', error);
    // Mostrar un mensaje de error al usuario
  });

console.log("Petición fetch iniciada... (Este log aparece ANTES que los datos)");
```

**Explicación Clave:**

1.  `fetch(url)` inicia la petición y devuelve **inmediatamente** una Promesa.
2.  El **primer `.then()`** recibe el objeto `Response` cuando el servidor responde con los *headers*. **Es crucial chequear `response.ok` o `response.status` aquí.**
3.  Llamamos a `response.json()` (o `response.text()`, `response.blob()`, etc.) para leer el *cuerpo* de la respuesta. Esto también es **asíncrono** y devuelve otra Promesa.
4.  El **segundo `.then()`** recibe los datos ya parseados (en este caso, el objeto JSON).
5.  El `.catch()` captura **errores de red** (no se pudo conectar, DNS falló) O **errores lanzados explícitamente** (como hicimos con `throw new Error` si `!response.ok`). **¡Fetch NO rechaza la promesa por errores HTTP 4xx/5xx por sí solo!**

**Enviar Datos (POST con JSON):**

```javascript
const nuevoUsuario = { nombre: "Carlos", email: "carlos@ejemplo.com" };
const postUrl = 'https://api.ejemplo.com/usuarios';

fetch(postUrl, {
  method: 'POST', // 1. Especificar el método
  headers: {
    'Content-Type': 'application/json' // 2. Indicar que enviamos JSON
    // 'Authorization': 'Bearer TU_TOKEN_AQUI' // Si necesitas autenticación
  },
  body: JSON.stringify(nuevoUsuario) // 3. Convertir el objeto JS a string JSON
})
.then(response => {
  if (!response.ok) {
    // Podrías intentar leer el cuerpo del error si la API lo envía en JSON
    return response.json().then(errData => {
        throw new Error(`Error HTTP: ${response.status} - ${errData.message || 'Error desconocido'}`);
    }).catch(() => { // Si el cuerpo del error no es JSON o hay otro problema
        throw new Error(`Error HTTP: ${response.status}`);
    });
  }
  // Si fue 201 Created, podría no haber cuerpo o devolver el objeto creado
  if (response.status === 201) {
      return response.json(); // O return {}; si no esperas cuerpo
  }
  return response.json(); // Para otros 2xx
})
.then(data => {
  console.log('Usuario creado:', data);
})
.catch(error => {
  console.error('Error al crear usuario:', error);
});
```

**Puntos Clave para POST:**

1.  Especificar `method: 'POST'` (o 'PUT', 'DELETE', etc.) en el objeto de opciones.
2.  Establecer el header `Content-Type` correctamente (usualmente `'application/json'`).
3.  Convertir el objeto JavaScript a una cadena JSON usando `JSON.stringify()` antes de pasarlo al `body`.

**🚧 CORS (Cross-Origin Resource Sharing):**

*   **Problema:** Por seguridad, los navegadores restringen las peticiones HTTP hechas con JS a un **dominio diferente** (distinto protocolo, dominio o puerto) del que sirvió la página original.
*   **Solución:** El **servidor** al que llamas (la API) debe incluir cabeceras HTTP especiales (como `Access-Control-Allow-Origin: *` o `Access-Control-Allow-Origin: https://tu-frontend.com`) para **permitir explícitamente** las peticiones desde tu origen.
*   **Si ves errores de CORS en la consola:** El problema está en la **configuración del servidor** de la API, no en tu código Fetch (generalmente). Necesitas que el backend habilite tu dominio o uses un proxy.

**✨ Usando `async`/`await` con Fetch (Más legible):**

```javascript
async function obtenerUsuario(id) {
  const apiUrl = `https://api.ejemplo.com/usuarios/${id}`;
  try {
    const response = await fetch(apiUrl); // Espera a que fetch termine

    if (!response.ok) {
      throw new Error(`Error HTTP: ${response.status}`);
    }

    const data = await response.json(); // Espera a que la conversión a JSON termine
    console.log('Datos del usuario (async/await):', data);
    return data; // La función async devuelve una promesa con este valor

  } catch (error) {
    console.error('Error al obtener datos (async/await):', error);
    // Podrías lanzar el error de nuevo o devolver null/undefined
    throw error; // O return null;
  }
}

// Para usarla:
obtenerUsuario(1)
  .then(usuario => {
    if (usuario) { /* Hacer algo con el usuario */ }
  })
  .catch(err => { /* Manejar error si obtenerUsuario falló */ });

// O dentro de otra función async:
async function mostrarInfoUsuario() {
    try {
        const user = await obtenerUsuario(1);
        // ... mostrar datos ...
    } catch (error) {
        // ... manejar error ...
    }
}
```

**❌ Errores Comunes con Fetch:**

*   **Olvidar chequear `response.ok`:** Asumir que si no entra al `.catch()`, todo fue bien. ¡Los 404 y 500 no van al `.catch()` por defecto!
*   **Olvidar llamar a `.json()` (o `.text()`):** Intentar usar el objeto `Response` directamente como si fueran los datos.
*   **Olvidar que `.json()` devuelve una promesa:** Intentar usar el resultado de `response.json()` inmediatamente fuera del siguiente `.then()` o sin `await`.
*   **Errores de CORS:** Pensar que es un error de Fetch cuando es configuración del servidor.
*   **Errores al enviar datos (POST/PUT):** No poner `method`, olvidar `Content-Type`, no usar `JSON.stringify()` para el `body`.
*   **Anidar `.then()` innecesariamente:** En lugar de encadenarlos retornando valores/promesas. `async/await` ayuda a evitar esto.

> ✨ **Punto Clave (Fetch):** Fetch es la forma moderna de hacer peticiones HTTP asíncronas con Promesas. **SIEMPRE chequea `response.ok`**. Recuerda que `response.json()` también es asíncrono. `async/await` hace el código más legible. ¡Entiende CORS!

---

### ⏳ Promesas (Promises) en JavaScript

Son objetos que representan la **finalización (o fallo) eventual** de una operación **asíncrona**. Son la base de `fetch` y `async/await`.

**Problema que Resuelven:** El "Callback Hell" o "Pyramid of Doom".

```javascript
// ANTES (Callback Hell): Código difícil de leer y mantener
operacionAsync1(params, function(resultado1) {
  operacionAsync2(resultado1, function(resultado2) {
    operacionAsync3(resultado2, function(resultado3) {
      // ... y así sucesivamente ...
    }, function(error3) { /* ... */ });
  }, function(error2) { /* ... */ });
}, function(error1) { /* ... */ });
```

**Cómo Funcionan las Promesas:**

*   Una promesa tiene un **estado interno**:
    *   `pending`: Estado inicial, la operación aún no termina.
    *   `fulfilled` (Resuelta): La operación terminó **con éxito**. La promesa tiene un *valor*.
    *   `rejected` (Rechazada): La operación **falló**. La promesa tiene una *razón* (generalmente un objeto Error).
*   Una promesa solo puede pasar de `pending` a `fulfilled` O `rejected`, **una sola vez**. Una vez "establecida" (settled), su estado no cambia.
*   Se registran funciones callback usando los métodos `.then()`, `.catch()`, y `.finally()`.

**Métodos Clave:**

*   `promesa.then(onFulfilled, onRejected)`:
    *   `onFulfilled(valor)`: Se ejecuta si la promesa se resuelve (`fulfilled`). Recibe el valor.
    *   `onRejected(razon)`: Se ejecuta si la promesa se rechaza (`rejected`). Recibe la razón/error. (Opcional, es mejor usar `.catch()`).
    *   **Importante:** `.then()` **devuelve una NUEVA promesa**, permitiendo el **encadenamiento**.
*   `promesa.catch(onRejected)`: Azúcar sintáctica para `promesa.then(undefined, onRejected)`. Maneja rechazos de la promesa original *o de cualquier `.then()` anterior* en la cadena.
*   `promesa.finally(onFinally)`: Se ejecuta **siempre** cuando la promesa se establece (ya sea `fulfilled` o `rejected`). Útil para limpieza (ej: ocultar un spinner de carga). No recibe valor ni razón.

**Encadenamiento (Chaining):** La clave para evitar el Callback Hell.

```javascript
operacionAsync1(params)
  .then(resultado1 => {
    console.log("Paso 1 completado");
    // Importante: Retornar la siguiente promesa o un valor
    return operacionAsync2(resultado1);
  })
  .then(resultado2 => {
    console.log("Paso 2 completado");
    return operacionAsync3(resultado2);
  })
  .then(resultado3 => {
    console.log("Paso 3 completado:", resultado3);
    // Hacer algo con el resultado final
  })
  .catch(error => {
    // Un solo .catch maneja errores de CUALQUIER paso anterior
    console.error("¡Ocurrió un error en algún paso!", error);
  })
  .finally(() => {
    console.log("Operación finalizada (éxito o fallo).");
  });
```

**Crear una Promesa (Menos común, útil para adaptar callbacks antiguos):**

```javascript
function esperar(milisegundos) {
  return new Promise((resolve, reject) => {
    // La función que pasamos a new Promise se ejecuta inmediatamente
    if (milisegundos < 0) {
      reject(new Error("Los milisegundos no pueden ser negativos"));
      return;
    }
    setTimeout(() => {
      // Cuando la operación asíncrona termina (aquí simulada con setTimeout)
      // llamamos a resolve() para éxito o reject() para fallo.
      resolve(`Esperados ${milisegundos} ms`);
    }, milisegundos);
  });
}

// Usar la promesa creada:
esperar(2000)
  .then(mensaje => {
    console.log("Éxito:", mensaje); // "Éxito: Esperados 2000 ms" (después de 2 seg)
    return esperar(-100); // Provocar un error
  })
  .catch(error => {
    console.error("Fallo:", error.message); // "Fallo: Los milisegundos no pueden ser negativos"
  });
```

**`async`/`await` (Revisión):**

*   Forma más moderna y legible de trabajar con promesas.
*   Una función marcada con `async` **siempre devuelve una promesa**.
*   `await` solo se puede usar **dentro de una función `async`**.
*   `await` pausa la ejecución de la función `async` hasta que la promesa a su derecha se resuelva o rechace.
    *   Si se resuelve, `await` devuelve el valor resuelto.
    *   Si se rechaza, `await` lanza el error (que puede ser capturado por `try...catch`).

```javascript
async function procesoCompleto() {
  console.log("Iniciando proceso...");
  try {
    const resultado1 = await esperar(1000); // Pausa aquí por 1 seg
    console.log("Paso 1:", resultado1);

    const resultado2 = await esperar(500);  // Pausa aquí por 0.5 seg
    console.log("Paso 2:", resultado2);

    console.log("Proceso completado!");
    return "¡Éxito total!"; // La promesa devuelta por procesoCompleto se resolverá con este valor

  } catch (error) {
    console.error("Error en el proceso:", error);
    throw error; // Opcional: re-lanzar para que quien llame a procesoCompleto() también reciba el error
                 // O return "Algo salió mal"; (resolver con un mensaje de error)
  } finally {
    console.log("Limpieza final del proceso.");
  }
}

// Llamar a la función async
procesoCompleto()
  .then(mensajeFinal => console.log("Resultado final:", mensajeFinal))
  .catch(err => console.error("Error capturado fuera:", err));
```

**Métodos Estáticos Útiles:**

*   `Promise.all([p1, p2, ...])`: Espera a que **todas** las promesas del array se resuelvan. Devuelve una promesa con un array de los resultados. **Si UNA falla, `Promise.all` falla inmediatamente.**
*   `Promise.allSettled([p1, p2, ...])`: Espera a que **todas** las promesas se establezcan (resueltas o rechazadas). Devuelve una promesa con un array de objetos, cada uno indicando el estado (`fulfilled`/`rejected`) y valor/razón de cada promesa original. **Útil si necesitas que todas terminen, incluso si alguna falla.**
*   `Promise.race([p1, p2, ...])`: Espera a que **la primera** promesa del array se establezca (resuelva o rechace). Se resuelve o rechaza con el valor/razón de esa primera promesa.
*   `Promise.resolve(valor)` / `Promise.reject(razon)`: Crean promesas ya resueltas o rechazadas.

**❌ Errores Comunes con Promesas:**

*   **No encadenar correctamente:** Hacer operaciones asíncronas dentro de un `.then` *sin* retornar la nueva promesa. Se pierde la secuencia.
*   **Olvidar el `.catch()`:** Los errores no manejados pueden detener la ejecución o pasar desapercibidos (errores silenciosos). ¡Siempre pon un `.catch()` al final de la cadena!
*   **Crear promesas anidadas innecesariamente ("Promise Hell"):** En lugar de encadenar con `return`.
*   **Usar `Promise.all` cuando necesitas `Promise.allSettled`:** Si quieres procesar todos los resultados aunque falle alguno.
*   **No entender el contexto asíncrono:** El código *después* de iniciar una promesa (o después de un `await`) se ejecuta *antes* de que la promesa se resuelva, a menos que esté en un `.then` posterior o después de otro `await`.

> ✨ **Punto Clave (Promesas):** Son la base del JS asíncrono moderno. Usa `.then()` para éxito, `.catch()` para errores, `.finally()` para limpieza. **Encadena** promesas retornando valores o nuevas promesas desde `.then()`. `async/await` simplifica enormemente la escritura y lectura de código asíncrono (úsalo con `try/catch`).

---

### 📄 Body y Headers en HTTP (Detalle)

Cuando hacemos peticiones (especialmente POST, PUT, PATCH) o recibimos respuestas, HTTP usa Headers y Body.

**Headers (Encabezados):**

*   **Qué son:** Pares clave-valor que proporcionan **metadatos** sobre la petición o la respuesta.
*   **Función:** Indican tipo de contenido, autenticación, control de caché, información del cliente/servidor, etc.
*   **Headers Comunes en Peticiones (Cliente -> Servidor):**
    *   `Host`: Dominio del servidor (obligatorio).
    *   `User-Agent`: Identifica al navegador/cliente.
    *   `Accept`: Qué tipos de contenido acepta el cliente como respuesta (ej: `application/json`, `text/html`).
    *   `Content-Type`: **Qué tipo de contenido** se está enviando en el **body** de la petición (ej: `application/json` para JSON, `application/x-www-form-urlencoded` para formularios clásicos, `multipart/form-data` para formularios con archivos). **¡Crucial para POST/PUT!**
    *   `Content-Length`: Tamaño del body en bytes.
    *   `Authorization`: Credenciales de autenticación (ej: `Bearer <token_JWT>`, `Basic <credenciales_base64>`).
    *   `Cookie`: Envía las cookies almacenadas para ese dominio.
*   **Headers Comunes en Respuestas (Servidor -> Cliente):**
    *   `Content-Type`: Qué tipo de contenido hay en el **body** de la respuesta.
    *   `Content-Length`: Tamaño del body.
    *   `Set-Cookie`: Instruye al navegador para que guarde una cookie.
    *   `Cache-Control`: Directivas para el cacheo.
    *   `Location`: Usado en redirecciones (3xx) para indicar la nueva URL.
    *   `Access-Control-Allow-Origin`: (Para CORS) Qué orígenes pueden acceder al recurso.

**Ejemplo Fetch con Headers:**

```javascript
// GET con header de autorización
fetch('https://api.ejemplo.com/datos-privados', {
  headers: {
    'Authorization': 'Bearer MI_TOKEN_SECRETO',
    'Accept': 'application/json' // Decimos que preferimos recibir JSON
  }
})
.then(...)
.catch(...);

// POST con JSON (ya visto)
fetch('https://api.ejemplo.com/items', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json', // ¡Fundamental!
    'Authorization': 'Bearer MI_TOKEN_SECRETO'
  },
  body: JSON.stringify({ nombre: "Nuevo Item", valor: 100 })
})
.then(...)
.catch(...);
```

**Body (Cuerpo):**

*   **Qué es:** Contiene los **datos reales** que se envían en una petición (POST/PUT/PATCH) o se reciben en una respuesta (generalmente GET con datos, o respuestas de POST/PUT). No todas las peticiones/respuestas tienen body (ej: GET simple, DELETE, respuestas 204 o 304).
*   **Formatos Comunes para Enviar Datos:**
    *   **JSON (`application/json`):** El más común para APIs modernas. Hay que usar `JSON.stringify()` en JS para crearlo.
    *   **Form Data (`application/x-www-form-urlencoded`):** Formato clásico de formularios HTML (clave=valor&clave2=valor2).
    *   **Multipart Form Data (`multipart/form-data`):** Usado por formularios HTML que incluyen **subida de archivos** (`<input type="file">`). Más complejo, pero el objeto `FormData` en JS facilita su creación.
    *   **Texto Plano (`text/plain`):** Simple texto.
    *   **XML (`application/xml`):** Menos común hoy en día para APIs web, pero usado en SOAP y sistemas legacy.

**Ejemplo Fetch con `FormData` (para subir archivos o enviar como formulario):**

```javascript
// Suponiendo que tienes un <input type="file" id="archivoInput"> y otros inputs
const miForm = document.querySelector('#miForm');
const archivoInput = document.querySelector('#archivoInput');
const nombreInput = document.querySelector('#nombreInput');

miForm.addEventListener('submit', function(event) {
    event.preventDefault(); // Evitar envío normal del formulario

    // 1. Crear un objeto FormData
    const formData = new FormData(); // Puedes pasar el elemento form directamente: new FormData(miForm)

    // 2. Añadir campos (si no pasaste el form al constructor)
    formData.append('nombre', nombreInput.value);
    // Añadir el archivo (el input file tiene una propiedad 'files')
    if (archivoInput.files.length > 0) {
        formData.append('archivo', archivoInput.files[0], archivoInput.files[0].name); // (nombreCampo, FileObject, nombreArchivoOpcional)
    }

    // 3. Hacer el fetch (¡NO establecer Content-Type manualmente!)
    fetch('https://api.ejemplo.com/upload', {
        method: 'POST',
        body: formData // Pasar el objeto FormData directamente
        // El navegador automáticamente pondrá el Content-Type: multipart/form-data con el boundary correcto
    })
    .then(response => {
        if (!response.ok) throw new Error(`Error: ${response.status}`);
        return response.json();
    })
    .then(data => console.log('Éxito:', data))
    .catch(error => console.error('Error:', error));
});
```

**❌ Errores Comunes (Body/Headers):**

*   **POST/PUT sin `Content-Type`:** El servidor no sabrá cómo interpretar el `body`.
*   **Enviar objeto JS en `body` sin `JSON.stringify()`:** Se envía `"[object Object]"`.
*   **Establecer `Content-Type: multipart/form-data` manualmente al usar `FormData`:** El navegador lo hace mejor, incluyendo el `boundary` necesario. No lo pongas tú.
*   **No validar el `body` en el servidor:** Riesgos de seguridad y errores.
*   **Problemas de autenticación:** Header `Authorization` incorrecto o faltante.

> ✨ **Punto Clave (Body/Headers):** Los **Headers** son metadatos (tipo, auth, cache). El **Body** son los datos (JSON, form). ¡Configúralos correctamente en `fetch`, especialmente `Content-Type` y `body` para POST/PUT! Usa `FormData` para subir archivos.

---

### 🔗 Obtener Parámetros desde la URL

A menudo, las URLs contienen información adicional en la **Query String** (o cadena de consulta) para filtrar, paginar o pasar datos simples, especialmente en peticiones GET.

*   **Formato:** Comienza con `?` después de la ruta, los parámetros son `clave=valor` separados por `&`.
    `https://www.ejemplo.com/buscar?q=javascript&page=2&sort=date`
*   **Componentes:**
    *   `q=javascript`: Parámetro `q` con valor `javascript`.
    *   `page=2`: Parámetro `page` con valor `2`.
    *   `sort=date`: Parámetro `sort` con valor `date`.

**¿Cómo leer estos parámetros en JavaScript (lado del cliente)?**

Usando la API **`URLSearchParams`**:

```javascript
// Suponiendo que la URL actual es: https://www.ejemplo.com/productos?categoria=libros&maxPrecio=50

// 1. Obtener la query string actual
const queryString = window.location.search; // Devuelve "?categoria=libros&maxPrecio=50"

// 2. Crear un objeto URLSearchParams a partir de la query string
const params = new URLSearchParams(queryString);

// 3. Leer parámetros individuales usando .get()
const categoria = params.get('categoria'); // "libros"
const maxPrecio = params.get('maxPrecio'); // "50" (¡Ojo! Siempre devuelve strings)
const orden = params.get('orden');       // null (si el parámetro no existe)

console.log(`Categoría: ${categoria}, Precio Máx: ${maxPrecio}`);

// 4. Verificar si un parámetro existe con .has()
if (params.has('categoria')) {
  console.log("Se especificó una categoría.");
}

// 5. Obtener todos los valores si un parámetro se repite (getAll)
// Ej: URL ...?tag=web&tag=js
// const tags = params.getAll('tag'); // Devuelve ['web', 'js']

// 6. Iterar sobre todos los parámetros
console.log("Todos los parámetros:");
for (const [clave, valor] of params.entries()) {
  console.log(`${clave}: ${valor}`);
}
// Salida:
// categoria: libros
// maxPrecio: 50
```

**Manipular Parámetros y Actualizar URL (sin recargar):**

`URLSearchParams` también permite modificar parámetros, y junto con la `History API`, puedes cambiar la URL visible sin recargar la página (útil en SPAs para reflejar filtros).

```javascript
// Crear o modificar parámetros
const params = new URLSearchParams(window.location.search);

params.set('page', '3'); // Establece 'page' a 3 (o lo añade si no existe)
params.append('filtro', 'nuevo'); // Añade 'filtro=nuevo' (permite múltiples valores para la misma clave)
params.delete('maxPrecio'); // Elimina el parámetro 'maxPrecio'

// Obtener la nueva query string
const nuevaQueryString = params.toString(); // "categoria=libros&page=3&filtro=nuevo"

// Actualizar la URL en la barra del navegador SIN recargar
const nuevaUrl = `${window.location.pathname}?${nuevaQueryString}`;
// history.pushState(estado, titulo, url): Añade una entrada al historial
history.pushState({ page: 3 }, "Página 3 de Productos", nuevaUrl);
// O history.replaceState() para modificar la entrada actual sin añadir una nueva

console.log("URL actualizada a:", window.location.href);
```

**❌ Errores Comunes:**

*   **No validar/sanear parámetros:** Los datos de la URL vienen del usuario, ¡nunca confíes en ellos directamente! Valídalos antes de usarlos.
*   **Olvidar que los valores son strings:** `params.get('page')` devuelve `"2"`, no el número `2`. Usa `parseInt()`, `parseFloat()` si necesitas números.
*   **Codificación/Decodificación:** `URLSearchParams` maneja automáticamente la codificación/decodificación de caracteres especiales (espacios como `%20`, etc.), pero sé consciente de que ocurre.
*   **Compatibilidad:** `URLSearchParams` es moderno, no funciona en IE11 (pero sí en todos los navegadores actuales).

> ✨ **Punto Clave (URL Params):** Usa `URLSearchParams(window.location.search)` para leer fácilmente los parámetros de la URL actual. Los métodos `get()`, `has()`, `set()`, `delete()`, `toString()` son tus herramientas principales. ¡Recuerda que los valores son strings!

---

### 💾 Web Storage API (localStorage y sessionStorage)

Permite a las páginas web **almacenar datos clave-valor localmente** en el navegador del usuario.

**Diferencia Clave con Cookies:**
*   **Mayor capacidad:** Usualmente 5-10MB por origen (mucho más que los ~4KB de las cookies).
*   **No se envían automáticamente al servidor:** Son solo para uso del lado del cliente (JavaScript), lo que mejora el rendimiento de las peticiones.
*   **API más simple:** `setItem`, `getItem`, `removeItem`, `clear`.

**Dos Mecanismos:**

1.  `localStorage`: **Persistente**. Los datos **permanecen** incluso después de cerrar el navegador y volver a abrirlo. Se borran solo si el usuario limpia los datos del navegador o el script los borra explícitamente. **Compartido entre todas las pestañas/ventanas del mismo origen.**
2.  `sessionStorage`: **Temporal (por sesión)**. Los datos **se eliminan automáticamente** cuando se cierra la pestaña o ventana del navegador. **Aislado por pestaña/ventana** (datos en una pestaña no son visibles en otra, aunque sea del mismo sitio).

**¿Cómo se organiza?** Cada **origen** (protocolo + dominio + puerto) tiene su propio `localStorage` y `sessionStorage` aislado de otros orígenes.

**Analogía:**
*   `localStorage`: Una **libreta guardada permanentemente** en tu cajón. Cualquiera (otra pestaña del mismo sitio) que abra el cajón puede ver lo que escribiste. No se borra solo.
*   `sessionStorage`: Una **nota Post-it en tu monitor** mientras trabajas en una tarea (pestaña). Si cierras la ventana, tiras el Post-it. Si abres otra ventana para la misma tarea, necesitas un Post-it nuevo (está vacío).

**API Común (localStorage y sessionStorage funcionan igual):**

*   `localStorage.setItem('clave', 'valor')` / `sessionStorage.setItem('clave', 'valor')`
    *   Guarda un valor asociado a una clave. **¡Importante: tanto clave como valor deben ser strings!** Para guardar objetos/arrays, usa `JSON.stringify()`.
*   `localStorage.getItem('clave')` / `sessionStorage.getItem('clave')`
    *   Recupera el valor asociado a la clave. Devuelve `null` si la clave no existe.
    *   Si guardaste un objeto JSON, necesitas usar `JSON.parse()` con el resultado.
*   `localStorage.removeItem('clave')` / `sessionStorage.removeItem('clave')`
    *   Elimina el par clave-valor.
*   `localStorage.clear()` / `sessionStorage.clear()`
    *   Elimina **todos** los pares clave-valor para ese origen.

**Ejemplo `localStorage` (Guardar Preferencia de Tema):**

```javascript
// --- Al guardar la preferencia (ej, al hacer clic en un botón) ---
function guardarTema(tema) { // tema podría ser 'oscuro' o 'claro'
    localStorage.setItem('preferenciaTema', tema);
    aplicarTema(tema); // Aplicar el tema visualmente
    console.log(`Tema guardado en localStorage: ${tema}`);
}

// --- Al cargar la página ---
function cargarYAplicarTema() {
    const temaGuardado = localStorage.getItem('preferenciaTema');
    const temaAplicar = temaGuardado || 'claro'; // Usar 'claro' como default si no hay nada guardado
    aplicarTema(temaAplicar);
    console.log(`Tema cargado desde localStorage: ${temaAplicar}`);
}

function aplicarTema(tema) {
    // Lógica para cambiar clases CSS en el <body>, por ejemplo
    document.body.className = tema === 'oscuro' ? 'theme-dark' : 'theme-light';
}

// Llamar al cargar la página
document.addEventListener('DOMContentLoaded', cargarYAplicarTema);

// Ejemplo de uso (asociado a botones, por ejemplo)
// botonTemaOscuro.onclick = () => guardarTema('oscuro');
// botonTemaClaro.onclick = () => guardarTema('claro');
```

**Ejemplo `sessionStorage` (Guardar datos de formulario multi-paso):**

```javascript
// --- Al pasar del Paso 1 al Paso 2 ---
function guardarDatosPaso1() {
    const nombre = document.getElementById('nombrePaso1').value;
    const email = document.getElementById('emailPaso1').value;
    const datosPaso1 = { nombre, email }; // Crear objeto

    // Guardar como string JSON en sessionStorage
    sessionStorage.setItem('datosFormPaso1', JSON.stringify(datosPaso1));
    console.log("Datos del paso 1 guardados en sessionStorage.");
    // Navegar al paso 2...
}

// --- Al cargar el Paso 2 (o al volver al Paso 1) ---
function cargarDatosPaso1() {
    const datosGuardadosString = sessionStorage.getItem('datosFormPaso1');
    if (datosGuardadosString) {
        try {
            const datosGuardados = JSON.parse(datosGuardadosString); // Parsear JSON
            // Rellenar los campos del formulario si existen
            if(document.getElementById('nombrePaso1')) document.getElementById('nombrePaso1').value = datosGuardados.nombre || '';
            if(document.getElementById('emailPaso1')) document.getElementById('emailPaso1').value = datosGuardados.email || '';
            console.log("Datos del paso 1 recuperados de sessionStorage.");
        } catch (e) {
            console.error("Error al parsear datos de sessionStorage", e);
            // Opcional: limpiar sessionStorage si está corrupto
            // sessionStorage.removeItem('datosFormPaso1');
        }
    }
}

// Llamar a cargarDatosPaso1() cuando se cargue el DOM de cada paso relevante
// document.addEventListener('DOMContentLoaded', cargarDatosPaso1);
```

**Comparativa Detallada:**

| Característica       | `sessionStorage` (Sesión)                   | `localStorage` (Local)                        |
| :------------------- | :------------------------------------------ | :-------------------------------------------- |
| **Persistencia**     | Temporal (se borra al cerrar pestaña/nav.) | Persistente (hasta borrado manual/script)   |
| **Alcance (Scope)**  | Por Pestaña/Ventana (aislado)               | Por Origen (compartido entre pestañas)        |
| **Disponibilidad**   | Solo durante la sesión de esa pestaña       | Disponible siempre (mismo origen/navegador)   |
| **Caso de Uso Típico**| Datos temporales de sesión (form multi-paso, estado UI temporal) | Preferencias de usuario, carritos persistentes, caché offline |
| **Acceso Servidor**  | No accesible (solo JS cliente)              | No accesible (solo JS cliente)                |
| **API**              | `setItem`, `getItem`, `removeItem`, `clear` | `setItem`, `getItem`, `removeItem`, `clear` |
| **Capacidad**        | ~5MB por origen                             | ~5-10MB por origen                            |

**⚠️ Consideraciones Importantes y Buenas Prácticas:**

*   **Seguridad:** Web Storage es accesible por **cualquier script** que se ejecute en tu página. **NO almacenes información extremadamente sensible** (contraseñas, números de tarjeta, tokens de alta seguridad) aquí, ya que un ataque XSS (Cross-Site Scripting) podría robarlos. Trátalo como almacenamiento conveniente, **no seguro**. Para tokens sensibles, considera cookies `HttpOnly`.
*   **Solo Strings:** Recuerda que solo guarda strings. Usa `JSON.stringify()` para guardar objetos/arrays y `JSON.parse()` para recuperarlos. ¡Un error común es olvidar esto!
*   **Síncrono:** La API es síncrona, lo que significa que leer o escribir puede (en teoría, raramente en la práctica con datos pequeños) bloquear brevemente el hilo principal de JS. Evita almacenar cantidades masivas de datos.
*   **Límites de Almacenamiento:** Aunque es más grande que las cookies, sigue siendo limitado (5-10MB). No lo uses como base de datos principal.
*   **Comprobar Disponibilidad:** En navegación privada o si el usuario lo deshabilita, Web Storage podría no estar disponible. Puedes verificarlo:
    ```javascript
    try {
        localStorage.setItem('test', 'test');
        localStorage.removeItem('test');
        // Si llegamos aquí, localStorage está disponible
    } catch (e) {
        console.error("localStorage no está disponible.", e);
        // Usar alternativas o mostrar aviso
    }
    ```

**❌ Errores Comunes (Web Storage):**

*   **Asumir que `sessionStorage` se comparte entre pestañas.** (¡Falso!).
*   **Confundir "sesión" de `sessionStorage` con la sesión de login del servidor.** (Son cosas distintas).
*   **Guardar objetos/arrays directamente sin `JSON.stringify`/`parse`.** (Se guarda `"[object Object]"`).
*   **Creer que los datos persisten tras cerrar el navegador (para `sessionStorage`)**.
*   **Almacenar datos sensibles sin precaución.**
*   **Olvidar manejar el caso donde `getItem` devuelve `null`** (la clave no existe).
*   **No limpiar `sessionStorage` cuando es apropiado** (ej: al hacer logout, aunque los datos se borrarán al cerrar la pestaña, puede ser bueno limpiarlos explícitamente para evitar inconsistencias si el usuario sigue navegando).

> ✨ **Punto Clave (Web Storage):** `localStorage` para datos persistentes (entre sesiones), `sessionStorage` para datos temporales (por pestaña). Ambos guardan **solo strings** (usa JSON), son **solo para cliente** y tienen **riesgos de seguridad** para datos sensibles. API simple: `setItem`, `getItem`, `removeItem`, `clear`.

---

### 🍪 Cookies en la Web

Son pequeños fragmentos de datos que un **servidor envía al navegador**, el navegador los **almacena** y los **envía de vuelta automáticamente** al mismo servidor en cada petición subsiguiente.

**Diferencia Clave con Web Storage:**
*   **Iniciadas por el Servidor:** Generalmente las crea el servidor (`Set-Cookie` header).
*   **Enviadas Automáticamente:** El navegador las incluye en el `Cookie` header de las peticiones al dominio correspondiente. ¡Esto puede afectar el rendimiento si son muchas o grandes!
*   **Menor Capacidad:** Limitadas a ~4KB por cookie y ~20-50 cookies por dominio (varía por navegador).
*   **Usadas para Sesiones:** Principalmente para mantener estado (sesiones de usuario), personalización y seguimiento.

**Anatomía de una Cookie (Header `Set-Cookie`):**

`Set-Cookie: nombreCookie=valorCookie; Domain=ejemplo.com; Path=/ruta; Expires=Wed, 21 Oct 2023 07:28:00 GMT; Max-Age=3600; Secure; HttpOnly; SameSite=Strict`

*   `nombreCookie=valorCookie`: El dato en sí (¡Obligatorio!).
*   `Expires=FECHA` / `Max-Age=SEGUNDOS`: Controlan la **expiración**.
    *   Si no se especifican, es una **cookie de sesión** (se borra al cerrar navegador).
    *   `Expires`: Fecha de expiración absoluta.
    *   `Max-Age`: Duración en segundos desde ahora (más moderno). Si ambos están, `Max-Age` tiene prioridad.
*   `Domain=DOMINIO`: A qué dominio pertenece (ej: `.ejemplo.com` para incluir subdominios).
*   `Path=RUTA`: A qué ruta dentro del dominio se aplica (ej: `/` para todo el sitio, `/admin` solo para esa sección).
*   **Atributos de Seguridad (¡Muy Importantes!):**
    *   `Secure`: La cookie solo se envía sobre conexiones **HTTPS**. ¡Fundamental para datos sensibles!
    *   `HttpOnly`: La cookie **NO es accesible mediante JavaScript** (`document.cookie`). Protege contra robo de cookies de sesión vía XSS. ¡Esencial para cookies de sesión!
    *   `SameSite=Strict|Lax|None`: Controla cuándo se envía la cookie en peticiones cross-site (desde otro dominio). Ayuda a prevenir ataques CSRF (Cross-Site Request Forgery).
        *   `Strict`: Solo se envía si la petición se origina **desde el mismo sitio**. La más segura.
        *   `Lax`: (Default en muchos navegadores) Se envía en navegación normal (clic en enlace), pero no en peticiones cross-site embebidas (imágenes, iframes) o hechas con JS (Fetch desde otro dominio). Buen equilibrio.
        *   `None`: Se envía siempre (requiere `Secure`). Necesario para cookies de seguimiento cross-site (ahora más restringidas por los navegadores).

**Tipos de Cookies:**

*   **De Sesión:** Sin `Expires`/`Max-Age`. Viven en memoria, se borran al cerrar navegador.
*   **Persistentes:** Con `Expires`/`Max-Age`. Se guardan en disco, duran hasta la fecha/tiempo especificado.
*   **De Origen (First-Party):** Dominio coincide con el de la barra de direcciones.
*   **De Terceros (Third-Party):** Dominio diferente (ej: de redes de publicidad, analytics). Cada vez más bloqueadas por privacidad.
*   **Necesarias/Técnicas:** Esenciales para el funcionamiento básico (login, carrito).
*   **De Análisis/Rendimiento:** Miden uso del sitio.
*   **De Publicidad/Seguimiento:** Crean perfiles de usuario para anuncios.

**Ciclo de Vida:**

1.  **Creación:** Servidor envía `Set-Cookie` en la respuesta.
2.  **Almacenamiento:** Navegador guarda la cookie asociada al dominio/path.
3.  **Transmisión:** Navegador envía `Cookie` header en peticiones futuras al mismo dominio/path.
4.  **Utilización:** Servidor lee el `Cookie` header para identificar al usuario, recordar preferencias, etc.
5.  **Expiración/Eliminación:** Por fecha/tiempo, cierre de navegador (sesión) o borrado manual.

**🍪 Crear y Usar Cookies con JavaScript:**

Aunque `HttpOnly` lo previene, **sí puedes crear/leer/eliminar cookies que NO sean `HttpOnly`** desde JavaScript usando `document.cookie`. ¡Es un poco engorroso porque es una sola string!

```javascript
// --- Establecer una Cookie (¡Recordar codificar valores!) ---
function setCookie(nombre, valor, diasParaExpirar) {
    let expires = "";
    if (diasParaExpirar) {
        const date = new Date();
        date.setTime(date.getTime() + (diasParaExpirar * 24 * 60 * 60 * 1000));
        expires = "; expires=" + date.toUTCString();
    }
    // ¡Importante! Codificar el valor por si tiene caracteres especiales (;,=,espacios)
    document.cookie = nombre + "=" + (encodeURIComponent(valor) || "")  + expires + "; path=/; SameSite=Lax"; // Añadir otros atributos como Secure si es necesario
    console.log(`Cookie creada: ${nombre}=${valor}`);
}

// --- Leer una Cookie Específica ---
function getCookie(nombre) {
    const nombreEQ = nombre + "=";
    const ca = document.cookie.split(';'); // Separa todas las cookies
    for(let i=0; i < ca.length; i++) {
        let c = ca[i];
        while (c.charAt(0)==' ') c = c.substring(1,c.length); // Quita espacios iniciales
        if (c.indexOf(nombreEQ) == 0) {
            // ¡Importante! Decodificar el valor
            return decodeURIComponent(c.substring(nombreEQ.length,c.length));
        }
    }
    return null; // No encontrada
}

// --- Eliminar una Cookie (Establecer fecha de expiración en el pasado) ---
function deleteCookie(nombre) {
    document.cookie = nombre +'=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT; SameSite=Lax'; // Fecha pasada
    console.log(`Cookie eliminada: ${nombre}`);
}

// --- Ejemplos de Uso ---
setCookie('usuario', 'JuanPerez', 7); // Guarda 'usuario=JuanPerez' por 7 días

let usuarioGuardado = getCookie('usuario'); // Recupera 'JuanPerez'
if (usuarioGuardado) {
    console.log(`Bienvenido de nuevo, ${usuarioGuardado}`);
} else {
    console.log("Bienvenido, visitante.");
}

// deleteCookie('usuario'); // Para borrarla
```

> **Nota Java:** El manejo principal de cookies (especialmente las de sesión `HttpOnly`) se hace en el **backend** (Java con Servlets, Spring, etc.). En Java, usarías `HttpServletRequest.getCookies()` para leerlas y `HttpServletResponse.addCookie(new Cookie(...))` para enviarlas al cliente. El acceso con JS es más para cookies no críticas o de seguimiento.

> ✨ **Punto Clave (Cookies):** Pequeños datos enviados por el servidor y devueltos automáticamente por el navegador. Usadas para estado (sesiones), personalización, tracking. Atributos `Secure`, `HttpOnly`, `SameSite` son **cruciales** para seguridad. El acceso JS (`document.cookie`) es posible pero limitado (no `HttpOnly`) y engorroso.

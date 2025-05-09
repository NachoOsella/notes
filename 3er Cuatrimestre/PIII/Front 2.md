# Resumen: Programación III - FRONT END (UTN Córdoba) 🚀

Este resumen cubre los conceptos clave de las Unidades Temáticas 1 y 2 del curso de Tecnicatura Universitaria en Programación, enfocándose en HTML, CSS, JavaScript básico, Tailwind CSS, Arquitectura Web, DOM, Eventos, Fetch API, Promesas, Almacenamiento Web y Cookies.

---

## Unidad 1: HTML, CSS y Javascript (Básico)

### HTML (HyperText Markup Language) 뼈대

Lenguaje de marcado estándar para crear y estructurar páginas web.

*   **HyperText**: Capacidad de enlazar documentos.
*   **Markup Language**: Usa etiquetas (`<tag>`) para definir estructura y formato.

> **Analogía**: HTML son los cimientos y el "esqueleto" de tu sitio web. 🏗️

**Estructura Básica:**
```html
<!DOCTYPE html> <!-- Indica HTML5 -->
<html lang="es"> <!-- Contenedor raíz -->
<head> <!-- Metadatos, links a CSS/JS, título -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título de la Página</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body> <!-- Contenido visible -->
    <h1>Hola Mundo</h1>
    <p>Contenido de la página.</p>
</body>
</html>
```

**Etiquetas Principales:**

1.  **Estructurales**: `<html>`, `<head>`, `<body>`.
2.  **Texto**:
    *   `<h1>` a `<h6>`: Encabezados (Jerarquía importante, `<h1>` único por página).
    *   `<p>`: Párrafos.
    *   `<br>`: Salto de línea (usar con moderación).
    *   `<hr>`: Línea horizontal (separador visual).
3.  **Enlaces e Imágenes**:
    *   `<a>`: Hipervínculo. Atributo clave: `href`.
        ```html
        <a href="https://www.ejemplo.com">Visitar Ejemplo</a>
        ```
    *   `<img>`: Imagen. Atributos clave: `src` (ruta) y `alt` (texto alternativo - ¡muy importante!).
        ```html
        <img src="imagen.jpg" alt="Descripción de la imagen">
        ```

**Etiquetas Semánticas:** Describen el propósito del contenido, mejorando accesibilidad y SEO.

*   `<header>`: Cabecera (logo, título, nav principal).
*   `<nav>`: Sección de navegación principal.
*   `<main>`: Contenido principal y único de la página.
*   `<section>`: Agrupa contenido temático relacionado.
*   `<article>`: Contenido independiente y autocontenido (post de blog, noticia).
*   `<aside>`: Contenido secundario relacionado (barra lateral, anuncios).
*   `<footer>`: Pie de página (copyright, enlaces secundarios).

> **Validación**: Usa [W3C Validator](https://validator.w3.org/) para comprobar tu HTML. ✅

**Recursos:**
*   [MDN: HTML](https://developer.mozilla.org/es/docs/Web/HTML)
*   [W3Schools: HTML](https://www.w3schools.com/html/)

---

### CSS (Cascading Style Sheets) 🎨

Lenguaje para definir la presentación y estilos visuales de documentos HTML. Separa contenido (HTML) de presentación (CSS).

**Ventajas:** Separación, Reutilización, Rendimiento, Consistencia.

**Selectores CSS:** Indican a qué elementos aplicar estilos.

1.  **Tipo (Elemento)**: `h1 { color: blue; }`
2.  **Clase (`.`):** `.mi-clase { font-size: 16px; }` (Aplicado con `class="mi-clase"`)
3.  **ID (`#`):** `#mi-id { background-color: yellow; }` (Aplicado con `id="mi-id"`, debe ser único)
4.  **Atributo**: `input[type="text"] { border: 1px solid black; }`

> **Consejo ✨**: Prefiere usar **clases** para estilos reutilizables. Reserva los **IDs** para elementos únicos o referencias en JavaScript.

**Propiedades Comunes:**

*   `color`: Color del texto.
*   `background-color`: Color de fondo.
*   `width`, `height`: Dimensiones del elemento.
*   `margin`: Espacio *exterior* al borde.
*   `padding`: Espacio *interior* entre el contenido y el borde.
*   `border`: Borde del elemento (ej: `border: 1px solid black;`).

**El Modelo de Caja (Box Model):** Todo elemento HTML es una caja rectangular.

1.  **Content**: El contenido (texto, imagen).
2.  **Padding**: Relleno interno.
3.  **Border**: Borde alrededor del padding y contenido.
4.  **Margin**: Margen exterior, separa de otros elementos.

```css
.mi-caja {
  width: 300px;        /* Ancho del contenido */
  padding: 20px;       /* Relleno interior */
  border: 1px solid black; /* Borde */
  margin: 15px;        /* Margen exterior */
  background-color: white;
}
```

**Diseño Responsivo:** Adapta el sitio a diferentes tamaños de pantalla.

*   **Media Queries**: Aplican estilos bajo condiciones (ej: ancho de pantalla).
    ```css
    @media (max-width: 600px) { /* Estilos para pantallas hasta 600px */
      body { background-color: lightblue; }
      h1 { font-size: 20px; }
    }
    ```
*   **Unidades Relativas**: `%`, `vw`/`vh` (viewport width/height), `em`/`rem` (relativas a fuente).

**Recursos:**
*   [MDN: CSS](https://developer.mozilla.org/es/docs/Web/CSS)
*   [W3Schools: CSS](https://www.w3schools.com/css/)
*   [CSS-Tricks: Box Model](https://css-tricks.com/the-css-box-model/)

---

### Introducción a Tailwind CSS 🌬️

Framework CSS "utility-first". Ofrece clases de bajo nivel para construir diseños directamente en el HTML, en lugar de componentes predefinidos.

**Beneficios:** Personalización total, Desarrollo rápido, Responsivo simple, Mantenimiento fácil.

**Instalación (Opción rápida CDN):**
```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
```
> **Nota ⚠️**: Para producción, se recomienda instalación local (NPM) para optimización (PurgeCSS).

**Conceptos Clave:**

1.  **Clases de Utilidad**: Cada clase aplica una propiedad CSS específica (`p-4` -> `padding: 1rem;`, `text-center` -> `text-align: center;`, `bg-blue-500` -> color de fondo azul).
2.  **Prefijos Responsivos**: Aplican utilidades en ciertos breakpoints (`md:text-lg` -> texto grande en pantallas medianas y mayores, `lg:flex` -> display flex en pantallas grandes).
    *   `sm:` (640px), `md:` (768px), `lg:` (1024px), `xl:` (1280px), `2xl:` (1536px).
    ```html
    <div class="bg-gray-200 p-4 md:bg-blue-200 lg:bg-green-200">...</div>
    ```
3.  **Flexbox y Grid**: Integrados con clases de utilidad (`flex`, `justify-between`, `grid`, `grid-cols-3`, `gap-4`).

**Ejemplos de Componentes Comunes:**

*   **Botón:**
    ```html
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Botón
    </button>
    ```
*   **Tarjeta:**
    ```html
    <div class="bg-white shadow-md rounded-lg p-6">
      <h5 class="text-lg font-bold">Título</h5>
      <p class="text-gray-600">Contenido...</p>
    </div>
    ```

**Recursos:**
*   [Documentación Oficial de Tailwind CSS](https://tailwindcss.com/docs)

---

### JavaScript Básico 📜

Lenguaje de programación de alto nivel, dinámico y no tipado. Se ejecuta en el navegador (cliente) para añadir interactividad.

**Usos Principales:**

*   Manipular el DOM (cambiar HTML/CSS dinámicamente).
*   Responder a eventos de usuario (clics, teclado).
*   Realizar peticiones asíncronas (AJAX/Fetch API).

**Sintaxis Básica:**

*   **Variables**:
    *   `let`: Variables reasignables con ámbito de bloque. (Preferida)
    *   `const`: Constantes (no reasignables) con ámbito de bloque. (Preferida para valores fijos)
    *   `var`: Ámbito de función (evitar en código moderno).
    ```javascript
    let nombre = "Juan";
    const edad = 25;
    ```
*   **Tipos de Datos**: `String`, `Number`, `Boolean`, `null`, `undefined`, `Object`, `Symbol`, `BigInt`.
*   **Objetos**: Colección de pares clave-valor.
    ```javascript
    const persona = {
      nombre: "Ana",
      edad: 30
    };
    ```
*   **Operadores**:
    *   Aritméticos: `+`, `-`, `*`, `/`, `%` (módulo).
    *   Comparación: `===` (estricta, valor y tipo), `!==`, `<`, `>`, `<=`, `>=`. (Evitar `==` y `!=`).
    *   Lógicos: `&&` (AND), `||` (OR), `!` (NOT).
    *   Asignación: `=`, `+=`, `-=`, `*=`, `/=`.

**Estructuras de Control:**

*   **Condicionales**: `if`/`else if`/`else`, `switch`.
    ```javascript
    if (edad >= 18) {
      console.log("Mayor de edad");
    } else {
      console.log("Menor de edad");
    }
    ```
*   **Bucles**: `for`, `while`, `do...while`, `for...of` (iterar sobre iterables), `for...in` (iterar sobre propiedades de objetos).
    ```javascript
    for (let i = 0; i < 5; i++) {
      console.log(i);
    }
    ```

**Funciones:** Bloques de código reutilizables.

1.  **Declaradas**:
    ```javascript
    function sumar(a, b) {
      return a + b;
    }
    ```
2.  **Expresiones (Anónimas)**:
    ```javascript
    const restar = function(a, b) {
      return a - b;
    };
    ```
3.  **Flecha (Arrow Functions - ES6)**: Sintaxis concisa.
    ```javascript
    const multiplicar = (a, b) => a * b;
    const cuadrado = x => x * x; // Paréntesis opcionales con un solo parámetro
    ```

---

## Unidad 2: Arquitectura, DOM, Eventos, Fetch API, Almacenamiento

### Modelo Cliente-Servidor y HTTP 🌐

**Arquitectura Cliente-Servidor**: Modelo de red donde:
*   **Cliente**: Solicita recursos (navegador, app móvil).
*   **Servidor**: Proporciona recursos (servidor web, base de datos).

**Servidor Web**: Software que escucha solicitudes HTTP y responde con recursos (HTML, CSS, JS, imágenes). Ej: Apache, Nginx, IIS.

**Protocolo HTTP (HyperText Transfer Protocol)**: Protocolo de comunicación petición/respuesta en la web.

*   **Métodos HTTP Principales**:
    *   `GET`: Solicitar datos (Leer).
    *   `POST`: Enviar datos para crear un nuevo recurso (Crear).
    *   `PUT`: Enviar datos para reemplazar un recurso existente (Actualizar/Reemplazar).
    *   `PATCH`: Enviar datos para actualizar parcialmente un recurso (Actualizar/Modificar).
    *   `DELETE`: Eliminar un recurso (Borrar).
*   **Códigos de Estado HTTP**: Indican el resultado de la solicitud.
    *   `2xx` (Éxito): `200 OK`, `201 Created`.
    *   `3xx` (Redirección): `301 Moved Permanently`.
    *   `4xx` (Error del Cliente): `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`.
    *   `5xx` (Error del Servidor): `500 Internal Server Error`.

**Flujo de Comunicación:**
1.  Cliente envía **Solicitud HTTP** (Método, URL, Headers, Body opcional).
2.  Servidor **Procesa** la solicitud.
3.  Servidor envía **Respuesta HTTP** (Código de estado, Headers, Body opcional).

---

### Sitios Estáticos vs. Dinámicos 🔄

*   **Sitios Estáticos**:
    *   Contenido fijo (archivos HTML, CSS, JS predefinidos).
    *   Servidor solo envía archivos.
    *   Rápidos, sencillos, seguros (sin BD/backend).
    *   Ej: Documentación, portafolios, landing pages.
*   **Sitios Dinámicos**:
    *   Contenido generado en tiempo real (backend, base de datos).
    *   Interactivos, personalizados.
    *   Requieren lógica de servidor (PHP, Python, Node.js, etc.).
    *   Ej: Redes sociales, e-commerce, blogs con comentarios.

**Comparación Rápida:**

| Característica | Sitio Estático             | Sitio Dinámico                 |
|----------------|----------------------------|--------------------------------|
| Contenido      | Fijo, pre-creado           | Generado en tiempo real        |
| Interactividad | Baja (solo frontend JS)    | Alta (frontend + backend)      |
| Backend        | No necesita                | Necesario (lenguaje + BD)      |
| Hosting        | Simple, barato             | Más complejo                   |
| Velocidad      | Muy rápido                 | Depende del procesamiento      |
| Ejemplos       | Docs, Portafolios          | Redes Sociales, E-commerce   |

---

### DOM (Document Object Model) 🌳

Interfaz de programación que representa el documento HTML/XML como un **árbol de objetos (nodos)**. Permite a JavaScript leer y manipular la estructura, contenido y estilo de la página dinámicamente.

> El DOM es la representación *viva* del HTML en memoria que el navegador utiliza.

**Manipulación del DOM:**

1.  **Acceso a Elementos**:
    *   `document.getElementById('id')`: Selecciona por ID (único).
    *   `document.getElementsByClassName('clase')`: Colección viva por clase.
    *   `document.getElementsByTagName('tag')`: Colección viva por etiqueta.
    *   `document.querySelector('selectorCSS')`: **(Recomendado)** Primer elemento que coincide con el selector CSS.
    *   `document.querySelectorAll('selectorCSS')`: **(Recomendado)** NodeList (estática) de todos los elementos que coinciden.
    ```javascript
    const titulo = document.querySelector('#main-title');
    const botones = document.querySelectorAll('.btn');
    ```
2.  **Crear y Agregar Elementos**:
    *   `document.createElement('tag')`: Crea un nuevo nodo elemento.
    *   `elemento.textContent = 'texto'`: Define el texto interno (seguro).
    *   `elemento.innerHTML = '<h1>HTML</h1>'`: Define el HTML interno (¡cuidado con XSS!).
    *   `padre.appendChild(hijo)`: Añade `hijo` al final de `padre`.
    *   Métodos modernos: `append()`, `prepend()`, `before()`, `after()`.
    ```javascript
    const nuevoParrafo = document.createElement('p');
    nuevoParrafo.textContent = 'Este es un párrafo nuevo.';
    document.body.appendChild(nuevoParrafo);
    ```
3.  **Modificar Atributos y Propiedades**:
    *   Propiedades directas: `elemento.id`, `elemento.className`.
    *   `elemento.classList` (`add`, `remove`, `toggle`, `contains`): Manejar clases CSS (recomendado).
    *   `elemento.setAttribute('atributo', 'valor')`, `elemento.getAttribute('atributo')`, `elemento.removeAttribute('atributo')`.
    *   `elemento.style.propiedadCSS = 'valor'`: Modificar estilos inline (ej: `elemento.style.color = 'red'`).
4.  **Recorrido del DOM (Navegación)**:
    *   Padre: `elemento.parentElement`.
    *   Hijos: `elemento.children` (solo elementos), `elemento.childNodes` (todos los nodos).
    *   Hermanos: `elemento.nextElementSibling`, `elemento.previousElementSibling`.

> **Rendimiento ⚡**: Minimiza las operaciones DOM. Realiza cambios en lote o usa `DocumentFragment` para añadir múltiples elementos con una sola operación.

> **Errores Comunes 🚫**: Seleccionar mal, intentar manipular antes de que el DOM cargue (`DOMContentLoaded`), modificar en bucles intensivos, confundir `innerHTML` vs `textContent`, no limpiar listeners/elementos.

---

### Manejo de Eventos en la Web 🖱️⌨️

Los eventos son acciones que ocurren en la página (clics, teclas presionadas, carga completa, etc.) a las que JavaScript puede **reaccionar**.

**Modelo**: Patrón Observer (Elementos emiten eventos, código "escucha").

**Flujo de Eventos (Event Flow)**: Orden en que se procesa un evento en elementos anidados.

1.  **Fase de Captura (Capturing)**: El evento "baja" desde `window` hasta el elemento objetivo. (Poco común usarla).
2.  **Fase de Objetivo (Target)**: El evento alcanza el elemento donde ocurrió originalmente.
3.  **Fase de Burbujeo (Bubbling)**: El evento "sube" desde el objetivo hasta `window`. (Comportamiento por defecto).

**Agregar Manejadores (Listeners)**: `addEventListener` es la forma moderna y recomendada.

```javascript
const miBoton = document.getElementById('miBoton');

function alHacerClick(event) {
  console.log('¡Botón clickeado!', event);
  // event: objeto con info del evento (target, type, etc.)
}

// Adjunta la función 'alHacerClick' al evento 'click' del botón
miBoton.addEventListener('click', alHacerClick);

// Para removerlo:
// miBoton.removeEventListener('click', alHacerClick);
```
> **Consejo**: Usa funciones nombradas si necesitas remover el listener o si la lógica es compleja.

**Eventos Comunes:** `click`, `mouseover`, `mouseout`, `keydown`, `keyup`, `submit`, `change`, `focus`, `blur`, `load`, `DOMContentLoaded`.

**Objeto `event`**: Pasado a la función manejadora, contiene detalles del evento.
*   `event.target`: Elemento original donde ocurrió el evento.
*   `event.currentTarget`: Elemento al que se adjuntó el listener.
*   `event.preventDefault()`: Cancela la acción por defecto del navegador (ej: enviar formulario, seguir enlace).
*   `event.stopPropagation()`: Detiene la propagación del evento (captura/burbujeo).

**Delegación de Eventos**: Técnica útil para manejar eventos en múltiples elementos hijos (ej: lista de ítems) adjuntando **un solo listener** a un contenedor padre. Se verifica `event.target` dentro del manejador. Mejora rendimiento y maneja elementos añadidos dinámicamente.

```javascript
document.getElementById('listaItems').addEventListener('click', function(event) {
  if (event.target && event.target.tagName === 'LI') {
    console.log('Clic en item:', event.target.textContent);
  }
});
```

> **Errores Comunes 🚫**: Olvidar `event.preventDefault()`, confundir `target` y `currentTarget`, memory leaks por no remover listeners, problemas con `this` en callbacks.

---

### Fetch API (Peticiones HTTP desde el Navegador) 📡

Interfaz moderna para realizar peticiones HTTP asíncronas (AJAX). Basada en **Promesas**. Reemplaza a `XMLHttpRequest`.

**Uso Básico (GET):**
```javascript
fetch('https://api.example.com/data') // Retorna una Promesa
  .then(response => {
    if (!response.ok) { // Verifica si la respuesta HTTP fue exitosa (200-299)
      throw new Error(`Error HTTP: ${response.status}`);
    }
    return response.json(); // Retorna otra Promesa que resuelve con los datos JSON
  })
  .then(data => {
    console.log('Datos recibidos:', data); // Usa los datos
  })
  .catch(error => {
    console.error('Error en la petición fetch:', error); // Maneja errores de red o del throw
  });
```

**Uso con POST (enviando JSON):**
```javascript
const datosAEnviar = { nombre: 'Ana', profesion: 'Developer' };

fetch('https://api.example.com/users', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json' // Indica que enviamos JSON
  },
  body: JSON.stringify(datosAEnviar) // Convierte objeto JS a string JSON
})
  .then(response => response.json())
  .then(data => console.log('Usuario creado:', data))
  .catch(error => console.error('Error:', error));
```

**Uso con `async/await` (ES2017):** Sintaxis más limpia para manejar promesas.

```javascript
async function obtenerDatos() {
  try {
    const response = await fetch('https://api.example.com/data');
    if (!response.ok) {
      throw new Error(`Error HTTP: ${response.status}`);
    }
    const data = await response.json(); // Espera a que la promesa .json() resuelva
    console.log('Datos con async/await:', data);
  } catch (error) {
    console.error('Error:', error);
  }
}
obtenerDatos();
```

> **Errores Comunes 🚫**: Olvidar `.json()` (o `.text()`, etc.), no manejar errores HTTP (un 404 **no** entra al `.catch` por defecto, solo errores de red), problemas de **CORS** (Cross-Origin Resource Sharing), enviar `body` sin `JSON.stringify` o sin el header `Content-Type` correcto.

---

### Promesas (Promises) en JavaScript ✨

Objeto que representa la **finalización (o fallo) eventual** de una operación asíncrona. Simplifica el manejo de callbacks anidados (evita "Callback Hell").

**Estados de una Promesa:**

1.  **Pending (Pendiente)**: Estado inicial, operación no completada.
2.  **Fulfilled (Cumplida)**: La operación terminó exitosamente (`resolve`).
3.  **Rejected (Rechazada)**: La operación falló (`reject`).

**Métodos Clave:**

*   `.then(onFulfilled, onRejected)`: Registra callbacks para cuando la promesa se cumple o (opcionalmente) se rechaza. Retorna una nueva promesa, permitiendo **encadenamiento**.
*   `.catch(onRejected)`: Atajo para `.then(null, onRejected)`. Maneja rechazos en cualquier punto anterior de la cadena.
*   `.finally(onFinally)`: Ejecuta un callback cuando la promesa termina (cumplida o rechazada), útil para limpieza.

**Creación de una Promesa (manual):**
```javascript
const miPromesa = new Promise((resolve, reject) => {
  // Simular operación asíncrona
  setTimeout(() => {
    const exito = Math.random() > 0.5;
    if (exito) {
      resolve("¡Operación exitosa!"); // Cumple la promesa
    } else {
      reject(new Error("¡Operación fallida!")); // Rechaza la promesa
    }
  }, 1000);
});

miPromesa
  .then(resultado => console.log(resultado)) // Se ejecuta si resolve()
  .catch(error => console.error(error.message)) // Se ejecuta si reject()
  .finally(() => console.log("Promesa terminada.")); // Se ejecuta siempre
```

**Encadenamiento:**
```javascript
fetch('/api/user')
  .then(res => res.json()) // Promesa 1
  .then(user => fetch(`/api/orders?userId=${user.id}`)) // Usa resultado, retorna Promesa 2
  .then(res => res.json()) // Promesa 3
  .then(orders => console.log(orders)) // Usa resultado de Promesa 3
  .catch(error => console.error('Fallo en la cadena:', error));
```

> **Errores Comunes 🚫**: Anidar `.then` en lugar de encadenar (no retornar la promesa), olvidar manejar rechazos (`.catch` o `try/catch` con `async/await`), mal uso de `Promise.all` (falla si una falla), no entender que el código *después* de iniciar la promesa sigue ejecutándose de inmediato.

---

### Body y Headers en HTTP ✉️

Componentes de una solicitud/respuesta HTTP:

*   **Headers (Encabezados)**: Metadatos clave-valor sobre la petición/respuesta (tipo de contenido, autenticación, caché, etc.).
*   **Body (Cuerpo)**: Contenido real de los datos enviados (en POST, PUT, PATCH) o recibidos.

**Headers Comunes:**

*   `Content-Type`: Tipo de dato en el *body* de la petición/respuesta (ej: `application/json`, `text/html`, `multipart/form-data`).
*   `Accept`: Tipos de dato que el *cliente* puede aceptar en la respuesta.
*   `Authorization`: Credenciales para autenticar al cliente (ej: `Bearer <token>`).
*   `Cache-Control`: Directivas para el almacenamiento en caché.
*   `User-Agent`: Identifica al cliente (navegador, etc.).

**Body Comunes:**

*   **JSON**: Formato ligero y popular para APIs (`{ "clave": "valor" }`).
*   **FormData**: Para enviar datos de formularios, incluyendo archivos.
*   **XML**: Formato más antiguo, usado en SOAP.
*   **Texto plano**, **HTML**, etc.

**Ejemplo Fetch con Headers y Body (JSON):**
```javascript
fetch('/api/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Accept': 'application/json',
    'Authorization': 'Bearer miTokenSecreto123'
  },
  body: JSON.stringify({ id: 1, value: 'dato' })
})
// ... manejo de .then y .catch
```

> **Importante**: Asegúrate de que el `Content-Type` del header coincida con el formato real del `body`. Valida siempre los datos recibidos en el backend.

---

### Obtener Parámetros desde la URL ❓

Los parámetros en la URL (parte después del `?`, llamada *query string*) permiten pasar datos al servidor o al script del lado del cliente. Formato: `?clave1=valor1&clave2=valor2`.

**Estructura de una URL:**
`https://www.ejemplo.com/ruta/pagina?param1=val1&param2=val2`
*   `https://`: Scheme (protocolo)
*   `www.ejemplo.com`: Host (dominio)
*   `/ruta/pagina`: Path (ruta del recurso)
*   `?param1=val1&param2=val2`: Query String

**Extraer Parámetros en JavaScript:** Usa la API `URLSearchParams`.

```javascript
// Suponiendo que la URL actual es: ...?nombre=Juan&edad=25&tema=dark&tema=light

// 1. Obtener los parámetros de la URL actual
const params = new URLSearchParams(window.location.search);

// 2. Obtener un valor específico
const nombre = params.get('nombre'); // "Juan"
const edad = params.get('edad');     // "25" (siempre string)
const noExiste = params.get('apellido'); // null

// 3. Verificar si existe un parámetro
if (params.has('nombre')) {
  console.log('El parámetro nombre existe.');
}

// 4. Obtener todos los valores de un parámetro repetido
const temas = params.getAll('tema'); // ["dark", "light"]

// 5. Iterar sobre todos los parámetros
for (const [clave, valor] of params.entries()) {
  console.log(`${clave}: ${valor}`);
}
```

**Manipular Parámetros (y actualizar URL sin recargar):**
```javascript
const params = new URLSearchParams(window.location.search);

// Modificar o añadir
params.set('idioma', 'es'); // Añade o reemplaza 'idioma'

// Añadir otro valor a una clave existente
params.append('tema', 'blue');

// Eliminar
params.delete('edad');

// Obtener la nueva query string
const nuevaQueryString = params.toString(); // "nombre=Juan&tema=dark&tema=light&idioma=es&tema=blue"

// Actualizar la URL en el navegador sin recargar la página
const nuevaURL = `${window.location.pathname}?${nuevaQueryString}`;
history.pushState(null, '', nuevaURL);
```

> **Nota**: Los valores obtenidos de `URLSearchParams` son siempre **strings**. Necesitarás convertirlos si esperas números (`parseInt`, `parseFloat`). Valida siempre los parámetros.

---

### Web Storage API (localStorage y sessionStorage) 💾

API del navegador para almacenar datos clave-valor **localmente** en el dispositivo del usuario.

*   **Diferencia con Cookies**: No se envían automáticamente al servidor con cada petición HTTP. Mayor capacidad de almacenamiento (~5-10MB vs ~4KB).
*   **Uso**: Guardar preferencias de UI, estado de aplicación offline, datos temporales de sesión, etc.
*   **Almacena solo strings**: Usa `JSON.stringify()` para guardar objetos/arrays y `JSON.parse()` para leerlos.

**1. `localStorage`**:
*   **Persistencia**: Los datos **permanecen** incluso después de cerrar el navegador. Solo se eliminan manualmente o por código.
*   **Alcance**: Compartido entre todas las pestañas/ventanas del **mismo origen** (dominio).
*   **Uso**: Preferencias de usuario a largo plazo, tokens de autenticación (¡con precaución!), datos offline.

**2. `sessionStorage`**:
*   **Persistencia**: Los datos **se eliminan** al cerrar la pestaña o ventana del navegador. Sobreviven a recargas de página.
*   **Alcance**: Aislado por pestaña/ventana. Una pestaña no ve el `sessionStorage` de otra, incluso del mismo origen.
*   **Uso**: Datos temporales de sesión (carrito de compra no persistente, estado de un formulario multi-paso, historial de navegación dentro de la app).

**API Común (igual para ambos):**
```javascript
// Guardar dato
localStorage.setItem('clave', 'valor');
sessionStorage.setItem('usuario', JSON.stringify({ id: 1, nombre: 'Ana' }));

// Leer dato
const valor = localStorage.getItem('clave'); // "valor"
const usuarioObj = JSON.parse(sessionStorage.getItem('usuario')); // { id: 1, nombre: 'Ana' }
const noExiste = localStorage.getItem('claveInexistente'); // null

// Eliminar dato específico
localStorage.removeItem('clave');

// Eliminar todos los datos (del origen para localStorage, de la sesión para sessionStorage)
localStorage.clear();
sessionStorage.clear();

// Obtener clave por índice (menos común)
const primeraClave = localStorage.key(0);

// Número de ítems almacenados
const numItems = localStorage.length;
```

**Comparativa Rápida:**

| Característica    | `localStorage`                      | `sessionStorage`                      |
|-------------------|-------------------------------------|---------------------------------------|
| **Persistencia**  | Permanente (hasta borrado manual) | Temporal (hasta cierre de pestaña/ventana) |
| **Alcance**       | Origen (compartido entre pestañas) | Pestaña/Ventana (aislado)             |
| **Disponibilidad**| Siempre (mismo origen)              | Solo en la sesión actual              |
| **Capacidad**     | ~5-10MB por origen                  | ~5-10MB por origen (aislado)          |
| **Uso Típico**    | Preferencias, Datos offline         | Estado temporal, Carrito no persistente |

> **Seguridad ❗**: Web Storage es accesible por cualquier script en tu página. **No almacenes datos extremadamente sensibles** (contraseñas, datos bancarios) sin medidas adicionales. Es vulnerable a ataques XSS (Cross-Site Scripting). Considera cookies `HttpOnly` para tokens de sesión críticos si la seguridad es primordial. Trátalo como un almacén **conveniente pero no 100% seguro**.

> **Errores Comunes 🚫**: Asumir que `sessionStorage` se comparte, confundir "sesión" de navegador con sesión de servidor, olvidar `JSON.stringify/parse`, almacenar datos sensibles, no manejar el caso donde el storage está vacío o no disponible (navegación privada).

---

### Cookies en la Web 🍪

Pequeños fragmentos de datos que un servidor envía al navegador, el cual los almacena y los **devuelve al servidor** en futuras solicitudes a ese mismo dominio.

**Usos Principales**:
*   **Gestión de Sesión**: Identificar usuarios logueados.
*   **Personalización**: Recordar preferencias (idioma, tema).
*   **Seguimiento (Tracking)**: Analizar comportamiento del usuario (a menudo por terceros).

**Anatomía de una Cookie**: String con pares `clave=valor` y atributos opcionales separados por `;`.
`nombre=valor; Expires=fecha; Max-Age=segundos; Domain=dominio; Path=ruta; Secure; HttpOnly; SameSite=Strict|Lax|None`

*   `Expires`/`Max-Age`: Determinan la vida de la cookie (si no, es de sesión).
*   `Domain`/`Path`: Controlan a qué dominio/ruta se enviará la cookie.
*   `Secure`: Solo enviar por HTTPS. (¡Recomendado!)
*   `HttpOnly`: **Impide acceso desde JavaScript** (mitiga XSS para robo de cookies de sesión). (¡Muy recomendado para sesión!)
*   `SameSite`: Controla cuándo se envía en peticiones cross-site (mitiga CSRF). `Strict` o `Lax` son más seguros.

**Tipos de Cookies**:
*   **De Sesión**: Se borran al cerrar el navegador.
*   **Persistentes**: Tienen fecha de expiración.
*   **First-Party**: Del mismo dominio que visitas.
*   **Third-Party**: De un dominio diferente (para tracking, publicidad; cada vez más restringidas por navegadores).

**Ciclo de Vida**:
1.  Servidor envía `Set-Cookie` header en la respuesta.
2.  Navegador almacena la cookie asociada al dominio.
3.  Navegador envía `Cookie` header en solicitudes futuras al mismo dominio.
4.  Servidor lee el `Cookie` header.
5.  Cookie expira o es eliminada.

**Manejo con JavaScript**: A través de `document.cookie`. (¡No funciona si la cookie es `HttpOnly`!).

```javascript
// Establecer una cookie (simple)
document.cookie = "usuario=Juan; path=/; max-age=86400"; // Dura 1 día

// Leer cookies (devuelve un string con todas, hay que parsear)
function getCookie(nombre) {
  const nombreEQ = nombre + "=";
  const ca = document.cookie.split(';');
  for(let i = 0; i < ca.length; i++) {
    let c = ca[i];
    while (c.charAt(0) === ' ') c = c.substring(1, c.length);
    if (c.indexOf(nombreEQ) === 0) return c.substring(nombreEQ.length, c.length);
  }
  return null;
}
const usuario = getCookie('usuario'); // "Juan"

// Eliminar una cookie (establecer fecha de expiración pasada)
document.cookie = "usuario=; path=/; expires=Thu, 01 Jan 1970 00:00:00 GMT";
// O usando max-age
document.cookie = "usuario=; path=/; max-age=0";
```

> **Seguridad y Privacidad**: Las cookies, especialmente las de terceros, tienen implicaciones de privacidad. Las regulaciones (GDPR, CCPA) requieren consentimiento. Usa atributos `Secure`, `HttpOnly` y `SameSite=Strict/Lax` para mejorar la seguridad.

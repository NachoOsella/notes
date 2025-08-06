## Guion de Presentación: Proyecto Final de Bases de Datos

**Nombre del Proyecto/Aplicación:** Gestor de Tareas Interactivo

**Problema que Resuelve:** La dificultad para organizar y dar seguimiento a las tareas diarias personales, así como visualizar el progreso y la actividad a lo largo del tiempo de forma eficiente.

**Solución y Características Principales:**

1. Creación, visualización, actualización y eliminación de tareas personales.
2. Registro detallado del historial de cambios para cada tarea (creación, actualización, completado, eliminación).
3. Generación de reportes y estadísticas sobre la actividad del usuario, como tareas completadas por semana, día más activo de la semana para crear tareas, y un ranking de usuarios por tareas completadas.

**Stack Tecnológico:**

- **Frontend:** React con Vite y TypeScript.
- **Backend:** Spring Boot (Java).
- **Base de Datos:**
    - **Motor de BD:** MongoDB.
    - **Motivo de la Elección:** Elegimos MongoDB por su flexibilidad para modelar datos de tareas que pueden evolucionar, su escalabilidad horizontal y la facilidad para almacenar documentos semi-estructurados como el historial detallado de las tareas. Su naturaleza orientada a documentos se alinea bien con los objetos Java que manejamos en el backend con Spring Boot, simplificando el mapeo objeto-documento.
    - **Diseño del Esquema/Modelo:**
        - **Colecciones Principales:**
            1. `users`: Almacena la información de los usuarios (id, username, email, password). Ver `User.java`.
            2. `todos`: Contiene los detalles de cada tarea (id, text, completed, userId, createdAt, updatedAt). Ver `Todo.java`.
            3. `todo_history`: Guarda un registro de cada acción realizada sobre una tarea (id, todoId, userId, text anterior, estado anterior, acción realizada como CREATED, UPDATED, COMPLETED, DELETED, y la fecha de la acción). Ver `TodoHistory.java`.
        - **Relaciones:**
            - La colección `todos` se relaciona con `users` a través del campo [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html).
            - La colección `todo_history` se relaciona con `todos` mediante [todoId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) y con `users` mediante [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html), permitiendo un seguimiento completo de la actividad por tarea y por usuario.
    - **Consulta o Funcionalidad Interesante:** Para generar el ranking de usuarios con más tareas completadas, implementamos una consulta de agregación en MongoDB. Esta consulta, visible en `TodoHistoryRepository.java` y utilizada en `TodoHistoryService.java`, primero filtra los registros de `todo_history` por la acción 'COMPLETED' usando `$match`. Luego, agrupa los resultados por [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) y cuenta el número de tareas completadas para cada usuario usando `$group` y `$sum`. Esto nos permite obtener el ranking de forma eficiente directamente desde la base de datos, optimizando el rendimiento de la aplicación al evitar el procesamiento manual de grandes volúmenes de datos en el backend.

---

### Guion Detallado (10 minutos)

---

**Sección 1: Introducción (1 minuto)**

**(0:00-0:15) Saludo y Presentación del Proyecto**

- **Presentador:** "Buenos días, profesora y compañeros. Hoy les presentaré mi proyecto final para la materia de Bases de Datos, llamado 'Gestor de Tareas Interactivo'."
    - [Mostrar diapositiva con el título del proyecto y tu nombre]

**(0:15-0:45) Problema y Solución**

- **Presentador:** "Muchos enfrentamos el desafío de mantenernos organizados y dar seguimiento a nuestras tareas diarias. A menudo, las herramientas existentes son demasiado complejas o no ofrecen una buena visión de nuestra productividad a lo largo del tiempo."
- **Presentador:** "Mi proyecto busca solucionar esto ofreciendo una plataforma simple pero potente para gestionar tareas personales, y lo más importante, para analizar nuestra actividad y progreso mediante un sistema de historial y reportes."
    - [Mostrar diapositiva con 2-3 puntos clave del problema]

**(0:45-1:00) Breve Mención de la Solución**

- **Presentador:** "La solución es una aplicación web que permite no solo crear y gestionar tareas, sino también visualizar un historial detallado de cada una y acceder a estadísticas personalizadas."
    - [Mostrar diapositiva con 2-3 características principales de la solución]

---

**Sección 2: Demostración del Producto (3 minutos)**

**(1:00-1:15) Inicio del Walkthrough**

- **Presentador:** "Ahora, permítanme mostrarles rápidamente cómo funciona la aplicación."
    - [Cambiar a la pantalla de la aplicación en vivo o un video grabado]

**(1:15-2:00) Creación y Gestión de Tareas**

- **Presentador:** "Aquí tenemos la interfaz principal. Podemos ver nuestras tareas pendientes. [Hacer clic en 'Crear Nueva Tarea'] Para agregar una nueva tarea, simplemente ingresamos el texto y la asignamos a un usuario. [Escribir 'Preparar presentación BDII' y guardar]."
- **Presentador:** "Una vez creada, podemos marcarla como completada [Hacer clic en el checkbox de una tarea], editarla [Hacer clic en editar, cambiar texto y guardar], o eliminarla [Hacer clic en eliminar]."
    - [Mostrar el flujo de creación, marcado como completado, edición y eliminación de una tarea]

**(2:00-2:45) Visualización del Historial y Reportes**

- **Presentador:** "Una característica clave es el seguimiento del historial. Si vamos a la sección de historial de un usuario [Navegar a la vista de historial del usuario en `/api/todos/history-enriched/{userId}`], podemos ver cada acción realizada: cuándo se creó una tarea, cuándo se actualizó, o cuándo se completó, incluyendo el detalle del cambio."
- **Presentador:** "Además, la aplicación genera reportes interesantes. Por ejemplo, aquí podemos ver las tareas completadas por este usuario en la última semana [Navegar a `/api/todos/report/completed-per-week?userId=...`], el día de la semana en que es más productivo creando tareas [Navegar a `/api/todos/report/most-active-day?userId=...`], y un ranking general de usuarios por tareas completadas [Navegar a `/api/todos/report/completed-ranking`]."
    - [Mostrar brevemente la interfaz de historial y un par de reportes]

**(2:45-3:00) Cierre de la Demo**

- **Presentador:** "Este es un vistazo rápido a las funcionalidades principales, diseñadas para ser intuitivas y útiles."

---

**Sección 3: "Bajo el Capó": Cómo lo Construimos (5 minutos)**

**(3:00-4:00) Arquitectura General (1 minuto)**

- **Presentador:** "Ahora, hablemos un poco sobre cómo se construyó esta aplicación."
- **Presentador:** "Para el frontend, utilizamos React con Vite y TypeScript, lo que nos permite una interfaz de usuario moderna y reactiva."
- **Presentador:** "El backend está desarrollado con Spring Boot en Java, proporcionando una base robusta y escalable para nuestra lógica de negocio y la API REST."
    - [Mostrar diapositiva con un diagrama simple de la arquitectura: Frontend (React) -> Backend (Spring Boot) -> Base de Datos (MongoDB)]

**(4:00-8:00) Profundización en la Base de Datos (4 minutos)**

- **Presentador:** "La parte central de este proyecto, y el foco de esta materia, es la base de datos. Para este gestor de tareas, elegimos MongoDB."
    
    - [Mostrar diapositiva con el logo de MongoDB]
- **(4:15-5:00) Motivo de la Elección de MongoDB**
    
    - **Presentador:** "Optamos por MongoDB principalmente por su flexibilidad. Los datos de las tareas y su historial pueden tener una estructura que evolucione. MongoDB, al ser una base de datos NoSQL orientada a documentos, maneja esto muy bien. Además, su capacidad de escalabilidad horizontal es una ventaja para el crecimiento futuro, y el formato de documento JSON-like se integra de manera natural con nuestros objetos Java en Spring Boot, facilitando el desarrollo."
- **(5:00-6:30) Diseño del Esquema/Modelo de Datos**
    
    - **Presentador:** "Diseñamos nuestro modelo de datos en torno a tres colecciones principales:"
    - **Presentador:** "1. **`users`**: Esta colección (`User.java`) almacena la información básica de los usuarios, como su ID, nombre de usuario y credenciales."
    - **Presentador:** "2. **`todos`**: Aquí (`Todo.java`) guardamos cada tarea con su texto, estado (completada o no), el ID del usuario al que pertenece ([userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html)), y las fechas de creación y última actualización."
    - **Presentador:** "3. **`todo_history`**: Esta es crucial para nuestras funcionalidades de reporte (`TodoHistory.java`). Cada vez que se crea, actualiza, completa o elimina una tarea, se genera un documento en esta colección. Almacena el [todoId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html), [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html), el estado de la tarea en ese momento, la acción realizada (CREATED, UPDATED, COMPLETED, DELETED) y la fecha exacta de la acción ([actionAt](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html))."
    - [Mostrar diapositiva con un diagrama simple del modelo de datos, mostrando las tres colecciones y las referencias [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) y [todoId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) entre ellas. Puedes dibujar esto o usar una herramienta.]
    - **Presentador:** "Como ven, `todos` tiene una referencia a `users` mediante [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html). Y `todo_history` referencia tanto a `todos` con [todoId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) como a `users` con [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html). Este diseño nos permite consultar eficientemente las tareas de un usuario y el historial completo de una tarea o de la actividad de un usuario."
- **(6:30-8:00) Consulta o Funcionalidad Interesante: Ranking de Tareas Completadas**
    
    - **Presentador:** "Una de las funcionalidades más interesantes desde la perspectiva de la base de datos es el ranking de usuarios por tareas completadas. Para lograr esto de manera eficiente, utilizamos una consulta de agregación de MongoDB."
    - [Mostrar diapositiva con el fragmento de código de la agregación de [TodoHistoryRepository.java](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) o una representación simplificada de la misma]
    - **Presentador:** "Esta consulta, definida en nuestro `TodoHistoryRepository.java`, tiene dos etapas principales:"
    - **Presentador:** "Primero, usamos el operador `$match` para filtrar solo aquellos documentos en la colección `todo_history` donde el campo [action](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) es igual a 'COMPLETED'. Esto nos da todos los eventos de tareas completadas."
    - **Presentador:** "Luego, aplicamos el operador `$group`. Agrupamos estos documentos por el [userId](vscode-file://vscode-app/opt/visual-studio-code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) y, para cada usuario, utilizamos `$sum: 1` para contar cuántas tareas completadas tiene. El resultado es una lista de usuarios con su respectivo conteo de tareas completadas."
    - **Presentador:** "Esta aproximación es muy potente porque todo el cálculo se realiza directamente en la base de datos, lo cual es mucho más rápido y eficiente que traer todos los datos a la aplicación y procesarlos allí, especialmente si tuviéramos millones de registros de historial. El servicio `TodoHistoryService.java` luego enriquece esta información con los nombres de usuario para presentar el ranking."
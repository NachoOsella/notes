# Movimientos Básicos

## Movimiento por caracteres
- `h`: Mover el cursor un carácter a la izquierda.
- `j`: Mover el cursor una línea hacia abajo.
- `k`: Mover el cursor una línea hacia arriba.
- `l`: Mover el cursor un carácter a la derecha.

## Movimiento por palabras
- `w`: Mover el cursor al inicio de la siguiente palabra.
- `e`: Mover el cursor al final de la palabra actual.
- `b`: Mover el cursor al inicio de la palabra anterior.

## Movimiento por líneas
- `0`: Mover el cursor al inicio de la línea actual.
- `^`: Mover el cursor al primer carácter no blanco de la línea.
- `$`: Mover el cursor al final de la línea actual.

# Movimientos Avanzados

## Movimiento por párrafos
- `{`: Mover el cursor al inicio del párrafo anterior.
- `}`: Mover el cursor al inicio del siguiente párrafo.

## Movimiento por frases
- `(`: Mover el cursor al inicio de la frase actual.
- `)`: Mover el cursor al inicio de la siguiente frase.

## Movimiento por secciones
- `[[`: Mover el cursor al inicio de la sección anterior.
- `]]`: Mover el cursor al inicio de la siguiente sección.

# Movimientos por Texto

## Buscar y reemplazar
- `/texto`: Buscar "texto" hacia adelante en el documento.
- `?texto`: Buscar "texto" hacia atrás en el documento.
- `n`: Repetir la última búsqueda en la misma dirección.
- `N`: Repetir la última búsqueda en la dirección opuesta.

# Movimientos por Pantalla

## Movimiento por bloques de texto
- `Ctrl + f`: Avanzar una pantalla (page down).
- `Ctrl + b`: Retroceder una pantalla (page up).
- `Ctrl + d`: Avanzar media pantalla.
- `Ctrl + u`: Retroceder media pantalla.

## Movimiento por el buffer
- `gg`: Mover el cursor al inicio del archivo.
- `G`: Mover el cursor al final del archivo.
- `:n`: Mover el cursor a la línea n (reemplaza "n" con el número de línea deseado).

# Movimientos por Marcadores

## Uso de marcadores
- `m{letra}`: Crear un marcador en la posición actual con la letra especificada.
- `'{letra}`: Mover el cursor a la línea del marcador especificado.
- `` `{letra} ``: Mover el cursor exactamente al marcador especificado.

# Otros Movimientos Útiles

## Movimientos rápidos
- `%`: Mover el cursor al paréntesis, corchete o llave coincidente.
- `*`: Buscar la palabra bajo el cursor hacia adelante.
- `#`: Buscar la palabra bajo el cursor hacia atrás.

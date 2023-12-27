
Saber leer la documentación es una de las habilidades más importantes para cualquier desarrollador.

_A pesar de que existe una traducción, recomiendo aprender a utilizar la documentación en inglés. Las bibliotecas que se utilizan en cientos de proyectos reales casi siempre tienen solo descripciones en inglés._

La sección principal a la que los programadores vuelven constantemente es el manual de funciones del lenguaje. En primer lugar, hay muchas funciones y es imposible recordar todo. En segundo lugar, en PHP el problema de la inconsistencia de los parámetros y los valores de retorno de las funciones es especialmente agudo. Por lo tanto, constantemente hay que recordar su orden.

Para describir las funciones se utiliza una notación propia (su propia sintaxis). Se parece un poco a PHP, pero aún así es diferente, en otras palabras, no es código PHP, sino solo una descripción de la firma de la función. Veamos la función `round()`, que redondea un número:

```
round(int|float $num, int $precision = 0, int $mode = PHP_ROUND_HALF_UP): float
```

El propósito de este formato es mostrar de manera visual los tipos, la cantidad y los valores predeterminados de los parámetros de entrada, así como el tipo del parámetro de salida. Este último siempre se encuentra en la posición más a la derecha, justo después de los dos puntos. En este caso, el tipo de valor de retorno es `float`.

La enumeración de los parámetros se realiza separándolos por comas entre paréntesis después del nombre de la función. Antes de cada nombre de parámetro se encuentra su tipo. Por ejemplo, el tipo del parámetro `$num` es `float`. El valor predeterminado se establece mediante una asignación, por ejemplo, `$precision` tiene un valor predeterminado de cero.

Los parámetros con valores predeterminados son parámetros opcionales de la función, y se separan por comas entre sí. Para la función anterior, estos son `$precision` y `$mode`. `$mode`, a su vez, tiene un valor predeterminado igual al valor de la constante `PHP_ROUND_HALF_UP`. Si algún parámetro tiene un valor igual al valor de una constante, significa que en la documentación de esta función hay una enumeración y descripción de todas las constantes posibles que se pueden utilizar como valor de este parámetro.

Basándonos en lo dicho anteriormente, podemos llamar a la función de la siguiente manera:

```php
<?php

round(5.3); // 5.0
round(8.333, 1); // 8.3
round(8.333, 2, PHP_ROUND_HALF_UP); // 8.33
```

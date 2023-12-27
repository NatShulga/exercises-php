En esta lección aprenderemos a trabajar con la firma de una función. También aprenderemos cómo una función recibe y devuelve valores. Analizaremos las funciones `abs()` y `round()`.

## Función abs()

La función `abs()`, que devuelve el valor absoluto, recibe un parámetro: un número. Si llamamos a `abs()` sin parámetros, PHP mostrará el siguiente mensaje de error:

```
TypeError: abs() expects exactly 1 argument, 0 given
```

Esto indica que la función espera un parámetro, pero la llamamos sin ninguno.

Los parámetros de `abs()` solo pueden ser números. Si intentamos pasarle una cadena de texto, obtendremos el siguiente error:

```
TypeError: abs(): Argument #1 ($num) must be of type int|float, string given
```

El resultado de llamar a esta función siempre es un número. Otra función puede tener un número diferente de parámetros y diferentes tipos de parámetros. Por ejemplo, puede existir una función que reciba tres parámetros: un número, una cadena de texto y otro número.

¿Cómo sabemos cuántos y qué tipo de parámetros necesita la función `abs()` y qué tipo de valor devuelve? Lo vemos en la **firma** de la función. La firma define los parámetros de entrada y sus tipos, así como el parámetro de salida y su tipo.

Puedes leer más sobre la función `abs()` en la [documentación oficial de PHP](https://www.php.net/manual/es/function.abs.php). En la sección "Descripción" encontrarás el siguiente texto:

```txt
abs(int|float $num): int|float

Devuelve el valor absoluto de num.
```

Esta es la firma de la función y una breve explicación en español.

La información se interpreta de la siguiente manera:

* El nombre de la función es `abs`
* La función recibe un parámetro: un número (num)
* La función devuelve un número
* La función devuelve el valor absoluto de num

Si hay más de un parámetro, debemos pasarlos en el mismo orden en que están definidos en la firma. Cualquier función siempre devuelve solo un valor. Esta es una limitación del lenguaje y no puede ser violada.

## Argumentos por defecto

Veamos la función `round()`. Esta función redondea un número:

```php
<?php

$result = round(10.25, 0); // 10
```

Le pasamos dos argumentos: el número y la precisión de redondeo. El valor `0` significa que se redondeará al número entero más cercano.

La mayoría de las veces, queremos redondear al número entero, por lo que los creadores de la función `round` hicieron que el segundo argumento sea opcional y le dieron un valor predeterminado de `0`. Esto significa que podemos omitir el segundo argumento y el resultado será el mismo:

```php
<?php

$result = round(10.25); // 10
```

Y si necesitamos una precisión diferente, podemos pasar un argumento:

```php
<?php

$result = round(10.25, 1); // 10.3
```

Si una función en PHP tiene argumentos opcionales, siempre se colocan después de los argumentos obligatorios. Pueden ser cualquier cantidad de argumentos, dependiendo de la función. Pero estos argumentos siempre se colocan juntos y al final de la lista de argumentos.

Las variables son útiles no solo para almacenar y reutilizar información. También son necesarias para simplificar cálculos complejos. En esta lección aprenderemos a hacerlo.

## Usando una expresión

Supongamos que necesitamos convertir euros a yuanes a través de dólares. Estas conversiones a través de una moneda intermedia son comunes en los bancos al realizar compras en el extranjero.

Primero, convertiremos 50 euros a dólares. Supongamos que un euro equivale a 1.25 dólares:

```php
<?php

$cantidadDolares = 50 * 1.25;
print_r($cantidadDolares);
```

Anteriormente, asignábamos un valor específico a una variable. Pero aquí, en `$cantidadDolares = 50 * 1.25;`, a la derecha del signo igual hay una **expresión**. El intérprete calculará el resultado, que es `62.5`, y lo asignará a la variable.

Para el intérprete, no importa si tiene `62.5` o `50 * 1.25` delante de él. Ambas opciones son expresiones que deben calcularse. Y se calculan con el mismo valor, `62.5`.

Cualquier cadena de texto es una expresión. La concatenación de cadenas también es una expresión. Cuando el intérprete encuentra una expresión, la procesa y genera un resultado, que es el **valor de la expresión**.

Aquí tienes algunos ejemplos de expresiones, y a la derecha de cada expresión se muestra el valor resultante:

```php
<?php

62.5             // 62.5
50 * 1.25        // 62.5
120 / 10 * 2     // 24
(int) '100'      // 100

"hello"          // "hello"
"Good" . "will"  // "Goodwill"
```

Ahora vamos a asignar el valor del dólar en yuanes como una variable separada. Calcularemos el precio de 50 euros en dólares multiplicándolos por `1.25`. Supongamos que 1 dólar equivale a 6.91 yuanes:

```php
<?php

$yuanesPorDolar = 6.91;
$cantidadDolares = 50 * 1.25; // 62.5
$cantidadYuanes = $cantidadDolares * $yuanesPorDolar; // 431.875

print_r($cantidadYuanes);
```

Cualquier variable puede formar parte de cualquier expresión. En el momento del cálculo, el valor de la variable se sustituye en lugar de su nombre. El intérprete calcula el valor de `$cantidadDolares` antes de que se utilice en otras expresiones. Cuando llega el momento de usar la variable, PHP ya conoce su valor porque ya lo ha calculado.

## Usando variables con concatenación

También se pueden usar variables con concatenación. Sintácticamente, no cambia nada: sabemos cómo concatenar (unir) dos cadenas de texto:

```php
<?php

$que = "Kings" . "road";
print_r($que); // => "Kingsroad"

// Concatenamos una cadena de texto y una variable que contiene una cadena de texto
$primera = "Kings";
$que = $primera . "road";
print_r($que); // => "Kingsroad"

// Concatenamos dos variables que contienen cadenas de texto
$ultima = 'road';
$que = $primera . $ultima;
print_r($que); // => "Kingsroad"
```

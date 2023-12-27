La agregación se aplica no solo a los números, sino también a las cadenas. Estos son problemas en los que la cadena se forma dinámicamente, es decir, no se sabe de antemano su tamaño ni qué contendrá.

Imagina una función que puede multiplicar una cadena, es decir, repetirla la cantidad de veces especificada:

```php
<?php

repeat('hexlet', 3); // 'hexlethexlethexlet'
```

El principio de funcionamiento de esta función es bastante simple: en un bucle, la cadena se "acumula" la cantidad de veces especificada:

```php
<?php

function repeat($text, $times)
{
    // El elemento neutro para las cadenas es una cadena vacía
    $result = '';
    $i = 1;

    while ($i <= $times) {
        // Agregamos la cadena al resultado cada vez
        $result = "{$result}{$text}";
        $i = $i + 1;
    }

    return $result;
}
```

Veamos la ejecución de este código paso a paso:

```php
<?php

// Para llamar a repeat('hexlet', 3);
$result = '';
$result = "{$result}hexlet"; // hexlet
$result = "{$result}hexlet"; // hexlethexlet
$result = "{$result}hexlet"; // hexlethexlethexlet
```

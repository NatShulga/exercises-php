
El trabajo con bucles generalmente se reduce a dos escenarios:

1. Agregación. Acumulación de resultados durante las iteraciones y trabajo con ellos después del bucle. La inversión de una cadena es un ejemplo de este tipo de escenario.
2. Ejecución del bucle hasta que se alcance un resultado deseado y luego salir. Por ejemplo, la tarea de buscar números primos. Recordemos que un número primo es aquel que solo se divide exactamente por sí mismo y por uno.

Consideremos un algoritmo simple para verificar la primariedad de un número. Dividiremos el número buscado `x` por todos los números en el rango desde dos hasta `x - 1` y veremos el residuo. Si no se encuentra ningún divisor en este rango que divida al número `x` sin residuo, entonces tenemos un número primo.

Si lo pensamos, podemos notar que es suficiente verificar los números hasta `x - 1/2`, en lugar de `x - 1`. Por ejemplo, 11 no se divide por 2, 3, 4, 5. Pero tampoco se dividirá por números mayores que la mitad de sí mismo. Por lo tanto, podemos realizar una pequeña optimización y verificar la división solo hasta `x / 2`.

```php
<?php

function isPrime($number)
{
    if ($number < 2) {
        return false;
    }

    $divisor = 2;

    while ($divisor <= $number / 2) {
        if ($number % $divisor === 0) {
            return false;
        }

        $divisor += 1;
    }

    return true;
}

isPrime(1); // false
isPrime(2); // true
isPrime(3); // true
isPrime(4); // false
```

El algoritmo está construido de tal manera que si durante la división secuencial por números hasta `x / 2` se encuentra al menos uno que divide sin residuo, entonces el argumento pasado no es un número primo y, por lo tanto, los cálculos posteriores no tienen sentido. En este punto, se debe devolver `false`.

Y solo si el bucle se ejecuta por completo, se puede concluir que el número es primo, ya que no se encontró ningún número que divida al número sin residuo.

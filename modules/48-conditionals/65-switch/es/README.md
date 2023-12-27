Muchos lenguajes, además de la construcción condicional *if*, incluyen el **switch**. En esta lección, nos familiarizaremos con él.

Es una versión especializada del *if*, creada para algunas situaciones particulares. Por ejemplo, tiene sentido usarlo cuando hay una cadena de *if else* con comprobaciones de igualdad. Por ejemplo:

```php
<?php

if ($status === 'processing') {
    // Hacer algo
} elseif ($status === 'paid') {
    // Hacer algo más
} elseif ($status === 'new') {
    // Hacer algo más
} else {
    // Hacer algo más
}
```

Esta comprobación compuesta tiene una característica distintiva: cada rama aquí es una comprobación del valor de la variable `status`. El switch permite escribir este código de forma más corta y expresiva:

```php
<?php

switch ($status) {
    case 'processing': // status == processing
        // Hacer algo
        break;
    case 'paid': // status == paid
        // Hacer algo más
        break;
    case 'new': // status == new
        // Hacer algo más
        break;
    default: // else
        // Hacer algo más
}
```

El switch es una construcción bastante compleja en términos de la cantidad de elementos que la componen:

* Una descripción externa que incluye la palabra clave `switch`. La variable cuyos valores seleccionará el *switch* para determinar el comportamiento. Y llaves para las opciones de selección.
* Las construcciones `case` y `default`, dentro de las cuales se describe el comportamiento para diferentes valores de la variable considerada. Cada `case` corresponde a un `if` en el ejemplo anterior. `default` es una situación especial que corresponde a la rama `else` en las construcciones condicionales. No es obligatorio especificar `default`, al igual que `else`.
* `break` se utiliza para evitar la "caída". Si no se especifica, después de ejecutar el `case` correspondiente, la ejecución pasará al siguiente `case` y así sucesivamente hasta el `break` más cercano o hasta el final del *switch*.

Las llaves en el *switch* no definen un bloque de código como en otros lugares. Dentro de él solo se permite la sintaxis que se muestra arriba. Es decir, se pueden usar `case` o `default`. Pero dentro de cada `case` (y `default`) la situación es diferente. Aquí se puede ejecutar cualquier código arbitrario:

```php
<?php

switch ($count) {
    case 1:
        // Hacer algo útil
        break;
    case 2:
        // Hacer algo útil
        break;
    default:
        // Hacer algo
}
```

A veces, el resultado obtenido dentro de un `case` es el final de la ejecución de la función que contiene el *switch*. En este caso, es necesario devolverlo de alguna manera al exterior. Para resolver esta tarea, hay dos formas.

**La primera forma** es crear una variable antes del *switch*, llenarla en los *case* y luego, al final, devolver el valor de esta variable al exterior:

```php
<?php

function doSomethingGood($count)
{
    // Llenar
    switch ($count) {
        case 1:
            $result = 'uno';
            break;
        case 2:
            $result = 'dos';
            break;
        default:
            $result = null;
    }

    // Devolver
    return $result;
}
```

**La segunda forma** es más simple y corta. En lugar de crear una variable, el *case* permite hacer un retorno normal de la función dentro de sí mismo. Después de `return`, no se ejecuta ningún código, por lo que podemos eliminar el `break`:

```php
<?php

function doSomethingGood($count)
{
    switch ($count) {
        case 1:
            return 'uno';
        case 2:
            return 'dos';
        default:
            return null;
    }
}
```

Aunque el switch se encuentra en el código, técnicamente siempre se puede prescindir de él. El beneficio clave de su uso es que expresa mejor la intención del programador cuando se necesitan comprobar valores específicos de una variable. Aunque el código se haya vuelto físicamente más largo, es más fácil de leer que los bloques con *elseif*.

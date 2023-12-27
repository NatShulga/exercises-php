Independientemente del lenguaje de programación utilizado, las funciones dentro de él tienen algunas propiedades fundamentales. Si conocemos estas propiedades, es más fácil predecir el comportamiento de las funciones, las formas de probarlas y dónde utilizarlas. En esta lección, estudiaremos estas propiedades de las funciones y sus características.

## ¿Qué es el determinismo?

**Determinismo** es una de las propiedades fundamentales de las funciones. Una función será determinista cuando devuelva el mismo resultado para los mismos argumentos de entrada. Por ejemplo, la función que invierte una cadena es determinista:

```php
<?php

strrev('gato'); // otag
strrev('gato'); // otag
```

No importa cuántas veces llamemos a esta función y le pasemos el valor `'gato'`, siempre devolverá `'otag'`.

Por otro lado, una función que devuelve un número aleatorio no es determinista. En este caso, obtendremos un resultado diferente para la misma entrada.

Incluso si uno de cada millón de llamadas devuelve algo diferente, esta función se considera automáticamente no determinista:

```php
<?php

rand(); // 827606195
rand(); // 635369726
```

El determinismo afecta seriamente muchos aspectos. Las funciones deterministas son convenientes para trabajar, fáciles de optimizar y probar. Si es posible hacer que una función sea determinista, vale la pena hacerlo.

## ¿Qué son los efectos secundarios?

`print_r()` también es una función. Toma datos de cualquier tipo como entrada y los muestra en la pantalla. Sin embargo, el valor que devuelve no se utiliza.

`print_r()` muestra algo en la pantalla, pero no devuelve un valor. Es una acción que realiza la función. La salida en la pantalla y el valor devuelto por la función son operaciones diferentes e independientes.

Técnicamente, la salida en la pantalla es equivalente a escribir en un archivo. Para entender esto, es necesario comprender cómo funcionan los sistemas operativos, lo cual es muy importante para los programadores.

Desde el punto de vista del programa, la salida en la pantalla es un **efecto secundario**. Los efectos secundarios se refieren a operaciones en las que se interactúa con el entorno externo (entorno de ejecución). Estas operaciones incluyen cualquier interacción en red, la salida de información en la pantalla, la impresión en una impresora, la interacción con el sistema de archivos (lectura y escritura de archivos), entre otros.

Los efectos secundarios son una de las principales fuentes de problemas y errores en los sistemas de software. El código con efectos secundarios es difícil de probar y no es confiable. Sin embargo, sin efectos secundarios, la programación no tendría sentido. Sin ellos, sería imposible obtener el resultado del programa, como escribir en una base de datos, mostrar en la pantalla, enviar a través de la red, entre otros.

Es importante comprender los principios de trabajar con efectos secundarios. Esto afecta el estilo de programación y la capacidad de construir programas de calidad. Este tema se desarrollará por completo en el curso sobre funciones.

## ¿Qué son las funciones puras?

Cuando una función es determinista y no tiene efectos secundarios, se le llama función **pura**. Estas funciones:

* Son más fáciles de leer, depurar y probar
* No dependen del orden en que se llaman
* Se pueden ejecutar fácilmente en paralelo

Las funciones puras son independientes del tiempo. El no determinismo y los efectos secundarios agregan el concepto de tiempo. Si una función depende de algo que puede o no suceder y cambia algo fuera de sus límites, de repente se vuelve dependiente del tiempo.

Pregunta de autoevaluación. ¿Se puede determinar la presencia de efectos secundarios dentro de una función basándose únicamente en su valor de retorno?

Hay una clase de problemas que no se puede resolver sin bucles: se llama **agregación de datos**. Estos problemas incluyen la búsqueda del valor máximo y mínimo, el cálculo de la suma y el promedio aritmético, entre otros. Su característica principal es que el resultado depende de todo el conjunto de datos. Para calcular la suma, es necesario sumar **todos** los números; para calcular el máximo, es necesario comparar **todos** los números.

Aquellos que trabajan con números, como contadores o especialistas en marketing, están familiarizados con este tipo de problemas. Por lo general, los resuelven en tablas de Microsoft Excel o Google Sheets. En esta lección, estudiaremos este tema.

Comencemos con el ejemplo más simple: buscar la suma de un conjunto de números. Implementaremos una función que sume los números en un rango especificado, incluyendo los límites. En este caso, un rango es una serie de números desde un punto de inicio hasta un punto final. Por ejemplo, el rango [1, 10] incluye todos los números enteros del 1 al 10.

```php
<?php

sumNumbersFromRange(5, 7); // 5 + 6 + 7 = 18
sumNumbersFromRange(1, 2); // 1 + 2 = 3

// [1, 1] Un rango con el mismo punto de inicio y final también es un rango
// Incluye exactamente un número: el límite del rango
sumNumbersFromRange(1, 1); // 1
sumNumbersFromRange(100, 100); // 100
```

Para implementar este código, necesitaremos un bucle por dos razones:

* La suma de números es un proceso iterativo, es decir, se repite para cada número.
* El número de iteraciones depende del tamaño del rango.

Antes de ver el código, intenta responder las siguientes preguntas:

* ¿Con qué valor inicializar el contador?
* ¿Cómo cambiará el contador?
* ¿Cuándo debe detenerse el bucle?

Intenta pensar en estas preguntas primero y luego mira el código a continuación:

```php
<?php

  function sumNumbersFromRange ($start, $finish)
  {
      // Técnicamente, se puede cambiar el valor de $start
      // Pero los argumentos de entrada deben mantenerse en su valor original
      // Esto hace que el código sea más fácil de analizar
      $i = $start;
      $sum = 0; // Inicialización de la suma

      while ($i <= $finish) { // Avanzar hasta el final del rango
          $sum = $sum + $i; // Calcular la suma para cada número
          $i = $i + 1; // Pasar al siguiente número en el rango
      }

      // Devolver el resultado obtenido
      return $sum;
  };
  ```

La estructura general del bucle es estándar. Tiene tres componentes:

* Un contador que se inicializa con el valor inicial del rango.
* El bucle en sí con una condición de finalización cuando se alcanza el final del rango.
* La modificación del contador al final del cuerpo del bucle.

El número de iteraciones en este bucle es igual a `$finish - $start + 1`. Es decir, para un rango de 5 a 7, esto es 7 - 5 + 1, lo que da tres iteraciones.

Las principales diferencias con el procesamiento normal están relacionadas con la lógica del cálculo del resultado. En los problemas de agregación, siempre hay una variable que almacena el resultado del bucle. En el código anterior, esta variable es `$sum`. En cada iteración del bucle, se actualiza sumando el siguiente número en el rango: `$sum = $sum + $i`.

Todo el proceso se ve así:

```php
<?php

// Para llamar a sumNumbersFromRange(2, 5);
$sum = 0;
$sum = $sum + 2; // 2
$sum = $sum + 3; // 5
$sum = $sum + 4; // 9
$sum = $sum + 5; // 14
// 14 es el resultado de sumar los números en el rango [2, 5]
```

La variable `$sum` se inicializa con el valor 0. ¿Por qué necesitamos especificar un valor inicial? Cualquier operación repetitiva comienza con un valor inicial. No se puede simplemente declarar una variable y comenzar a trabajar con ella dentro del bucle. Esto puede llevar a errores:

```php
<?php

// el valor inicial no está especificado
// PHP lo establece automáticamente en NULL
$sum;

// primera iteración del bucle
$sum = $sum + 2; // ?
```

Como resultado de esta llamada, `$sum` contendrá el resultado correcto, pero el intérprete mostrará un error: `PHP Notice:  Undefined variable: sum`. Esto ocurre porque se intenta usar una variable no definida. Por lo tanto, necesitamos algún valor. ¿Por qué se eligió 0 en el código anterior? Es muy fácil comprobar que todas las demás opciones darán un resultado incorrecto. Si el valor inicial es 1, el resultado será 1 más de lo esperado.

En matemáticas, cada operación tiene un **elemento neutro**. Una operación con este elemento no cambia el valor sobre el que se realiza la operación:

* Cero para la suma: cualquier número + cero = el número mismo
* Cero para la resta: cualquier número - cero = el número mismo
* Cadena vacía para la concatenación: `''` + `'string'` será `'string'`

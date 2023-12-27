Supongamos que queremos imprimir la palabra "¡Padre!" en la pantalla dos veces o incluso cinco veces. Podemos resolver esta tarea de la siguiente manera:

```php
<?php

print_r('¡Padre!');
print_r('¡Padre!');
```

En casos simples, esto funciona bien, pero si la palabra "¡Padre!" se utiliza con más frecuencia y en diferentes partes del programa, tendríamos que repetirla en todas partes. Si necesitamos cambiar la palabra, tendríamos que encontrar todos los lugares donde se utiliza y realizar el reemplazo necesario. Pero hay otra forma de hacerlo. En lugar de copiar la expresión, simplemente creamos una variable con esta frase:

```php
<?php

// greeting - se traduce como saludo
$greeting = '¡Padre!';
print_r($greeting);
print_r("\n");
print_r($greeting);
// => ¡Padre!
// => ¡Padre!
```

En la línea `$greeting = '¡Padre!'`, el valor `'¡Padre!'` se asigna a la variable con el nombre `$greeting`. En PHP, los nombres de las variables comienzan con el símbolo *$*. Como resultado, la variable apunta a los datos que se han almacenado en ella.

Una vez que se ha creado la variable, podemos comenzar a usarla.

## Uso de una variable

La variable se inserta en los lugares donde solíamos tener nuestra palabra. Durante la ejecución, el intérprete llega a la línea `print_r($greeting);` y reemplaza la variable por su contenido, y luego ejecuta el código.

Para el nombre de la variable, se puede utilizar cualquier conjunto de caracteres válidos, que incluyen letras del alfabeto inglés, números y el carácter `_`. Sin embargo, no se puede colocar un número al principio. Los nombres de las variables en PHP distinguen entre mayúsculas y minúsculas, es decir, `hello` y `heLLo` son dos nombres diferentes, lo que significa que son dos variables diferentes. La distinción entre mayúsculas y minúsculas es importante en PHP, así que no olvides tenerlo en cuenta.

No hay límite en la cantidad de variables que se pueden crear. Los programas grandes contienen decenas o incluso cientos de miles de nombres de variables. Para facilitar el análisis del programa, es conveniente crear las variables lo más cerca posible del lugar donde se utilizan.

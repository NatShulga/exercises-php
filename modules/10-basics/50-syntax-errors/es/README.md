
Si un programa escrito en PHP tiene errores de sintaxis, el intérprete mostrará un mensaje correspondiente en la pantalla, junto con la indicación del archivo y la línea donde, según su opinión, se produjo el error. Un _error de sintaxis_ ocurre cuando el código se ha escrito con violación de las reglas gramaticales. En los lenguajes humanos, la gramática es importante, pero generalmente se puede entender y leer el texto con errores. En la programación, todo es estricto. Cualquier violación mínima y el programa ni siquiera se ejecutará. Un ejemplo puede ser un punto y coma olvidado, paréntesis mal colocados y otros detalles.

Aquí hay un ejemplo de código con un error de sintaxis:

```php
<?php

print_r('Hodor')
```

Si ejecutamos el código anterior, veremos el siguiente mensaje: `$ PHP Parse error:  syntax error, unexpected end of file in /private/var/tmp/index.php on line 4`. Estos errores de sintaxis en PHP se clasifican como "Parse error". Como se puede ver, al final se muestra la ruta del archivo y el número de línea.

Por un lado, los errores de "Parse error" son los más simples, porque están relacionados exclusivamente con las reglas gramaticales de escritura de código, no con el significado del código en sí. Son fáciles de corregir: solo hay que encontrar la violación en la escritura.

Por otro lado, el intérprete no siempre puede señalar claramente esta violación. Por lo tanto, a veces sucede que es necesario colocar el paréntesis olvidado no donde indica el mensaje de error.

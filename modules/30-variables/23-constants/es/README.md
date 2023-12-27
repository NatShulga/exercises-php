Los desarrolladores a menudo trabajan con datos que nunca cambian. Por ejemplo, el número π, que siempre es igual a `3.14` y no puede cambiar.

En PHP, se utilizan constantes para acceder a este tipo de datos:

```php
<?php

const PI = 3.14;
print_r(PI); // => 3.14
```

La creación de una constante es diferente a la creación de una variable. Comienza con la palabra clave `const` seguida del nombre de la constante. No se necesita el signo de dólar. Luego se le asigna el valor deseado.

Las constantes suelen nombrarse en mayúsculas con `_` como separador. Una constante también se puede utilizar en cualquier expresión. La única restricción es que no se puede modificar.

PHP tiene muchas constantes integradas que se pueden utilizar en cualquier parte del programa. Aquí hay algunas de ellas:

* `PHP_VERSION` — versión actual de PHP
* `PHP_MAXPATHLEN` — longitud máxima permitida para el nombre de archivo
* `PHP_INT_MAX` — valor máximo posible para números enteros (integer)

Además de las constantes normales en PHP, existe un grupo separado llamado **constantes mágicas**. Sus diferencias son las siguientes:

* No se pueden definir constantes mágicas por uno mismo, solo se pueden utilizar las existentes
* Las constantes mágicas comienzan y terminan con los caracteres `__` (dos guiones bajos)
* La magia radica en que estas constantes tienen el mismo valor solo dentro de una parte específica del programa

El último punto significa que existen constantes que no son muy constantes, pero sus cambios están regulados y no suelen causar problemas en la práctica. Algunas de estas constantes son:

* `__LINE__` — contiene el número de línea actual del archivo en el que se utiliza
* `__FILE__` — ruta al archivo actual
* `__DIR__` — ruta al directorio en el que se encuentra el archivo actual

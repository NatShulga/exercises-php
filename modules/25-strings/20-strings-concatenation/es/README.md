En el desarrollo web, los programas operan constantemente con cadenas de texto. Todo lo que vemos en los sitios web está representado de alguna manera como texto. Este texto suele ser dinámico, obtenido de diferentes partes que se unen entre sí. La operación de unir cadenas en programación se llama **concatenación**.

Ya conocemos la operación matemática de suma:

```php
<?php

print_r(5 + 3); // => 8
```

Este programa mostrará `8` en la pantalla, que es el resultado de la operación binaria `+` con los operandos `5` y `3`.

También podemos "sumar" dos cadenas. Este programa mostrará `Dragonstone`, que es el resultado de la operación binaria `.` con los operandos 'Dragon' y 'stone':

```php
<?php

print_r('Dragon' . 'stone'); // => Dragonstone
```

La concatenación de cadenas siempre ocurre en el mismo orden en el que se escriben los operandos. El operando izquierdo se convierte en la parte izquierda de la cadena, y el operando derecho en la parte derecha. Aquí hay algunos ejemplos más:

```php
<?php

print_r('Kings' . 'wood');     // => Kingswood
print_r('Kings' . 'road');     // => Kingsroad
print_r("King's" . 'Landing'); // => King'sLanding
```

Las cadenas se pueden concatenar incluso si están escritas con diferentes tipos de comillas.

Un espacio en blanco es un carácter igual que los demás, por lo que la cantidad de espacios en blanco que se coloque en una cadena será la misma en la cadena resultante:

```php
<?php

// Colocamos un espacio en blanco en la parte izquierda
print_r("King's " . 'Landing'); // => King's Landing

// Colocamos un espacio en blanco en la parte derecha
print_r("King's" . ' Landing'); // => King's Landing
```

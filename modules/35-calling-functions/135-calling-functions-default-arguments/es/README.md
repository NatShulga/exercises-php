
Veamos la función `round()`. Redondea el número que se le pasa:

```php
<?php

$resultado = round(10.25, 0); // 10
```

Le pasamos dos argumentos: el número y la precisión de redondeo. El valor `0` significa que se redondeará al número entero más cercano.

En la mayoría de los casos, se necesita redondear al número entero (no a los décimos, por ejemplo), por lo que los creadores de la función `round` hicieron el segundo argumento **opcional** y le dieron un **valor por defecto de `0`**. Esto significa que no es necesario especificar el segundo argumento y el resultado será el mismo:

```php
<?php

$resultado = round(10.25); // 10
```

Y si se necesita una precisión diferente, se puede pasar un argumento:

```php
<?php

$resultado = round(10.25, 1); // 10.3
```

Si una función en PHP tiene argumentos opcionales, siempre se colocan después de los argumentos obligatorios. Pueden ser cualquier cantidad (depende de la función en sí), pero siempre van juntos y al final de la lista de argumentos.

Recordemos que PHP es un lenguaje con **tipado débil**:

* Conoce la existencia de diferentes tipos (números, cadenas, etc.)
* Sin embargo, no es muy estricto en su uso, tratando de convertir la información cuando parece razonable

Se producen muchas conversiones automáticas al trabajar con operaciones lógicas. En PHP hay dos reglas simples para las conversiones:

* `0`, `null` y la cadena vacía `''` se convierten en `false`, por lo que se llaman *falsy*
* Todo lo demás se convierte en `true`

Esto también funciona en sentido contrario. Tanto `true` como `false` se convierten en otros tipos de datos según la situación:

```php
<?php

print_r(true);   // => 1
print_r(false);  // => (se muestra una cadena vacía en la pantalla)
print_r(0 || 1); // => 1
```

El operador **OR** solo funciona con el tipo *bool*, pero se le dan los números `1` y `0`:

1. `0` se convierte en `false` y `1` se convierte en `true`
2. El resultado de `false || true` es `true`
3. Ahora `print_r()` recibe `true`, pero solo funciona con cadenas
4. `true` se convierte en `1`
5. Y se muestra `1` en la pantalla

Aquí es importante destacar la diferencia entre los operadores `===` y `==`. La diferencia radica en la conversión de tipos.

La cadena vacía y `false` son valores diferentes, por lo que el operador `===` dice "¡Falso! ¡No son iguales!".

Pero el operador `==` convierte los tipos. Desde su punto de vista, la cadena vacía y `false` son iguales. Esta conversión es implícita, por lo que se recomienda evitar los operadores `==` y `!=` siempre que sea posible:

```php
<?php

var_dump('' === false); // => false
var_dump('' == false);  // => true
```

Recordemos la operación de negación. Con una doble negación `!!`, el valor final es igual al valor inicial:

```php
<?php

$respuesta = true;
var_dump(!$respuesta);  // => false
var_dump(!!$respuesta); // => true
```

Aquí también se producen conversiones de tipo adicionales. Por lo tanto, el resultado de una doble negación siempre será de tipo _bool_. Se utiliza este truco para cambiar el tipo de datos.

En diferentes lenguajes de programación, hay diferentes reglas de conversión. Algunos lenguajes no realizan conversiones de tipos por sí mismos.

En esta lección vamos a hablar sobre las cadenas de texto y por qué necesitamos comillas simples y dobles. También aprenderemos sobre las secuencias de escape y la concatenación.

## ¿Qué es una cadena de texto?

Cualquier carácter individual entre comillas es una **cadena de texto**. Por ejemplo:

```php
<?php

'Hola'
'Adiós'
'G'
' '
''
```

Una cadena de texto vacía `''` también es una cadena de texto. Es decir, consideramos como cadena de texto todo lo que está dentro de las comillas, incluso si es un espacio, un solo carácter o la ausencia total de caracteres.

Anteriormente, en las lecciones, hemos escrito cadenas de texto entre comillas simples, pero también se pueden usar comillas dobles:

```php
<?php

print_r("¡Dracarys!");
```

Veamos por qué hay dos formas de representar una cadena de texto.

## ¿Por qué necesitamos comillas dobles?

Supongamos que queremos imprimir la frase ``la madre del dragón``. El apóstrofe antes de la letra **s** es un carácter igual que una comilla simple. Intentemos:

```php
<?php

print_r('La madre del dragón');
// Error de análisis de PHP: error de sintaxis, inesperado 's' (T_STRING), esperando ',' o ')'
```

Este programa no funcionará. Desde el punto de vista de PHP, la cadena de texto comenzó con una comilla simple y terminó después de la letra **n**. Luego hubo caracteres `s mother` sin comillas, lo que significa que no es una cadena de texto. Y luego hubo una comilla de apertura de cadena que nunca se cerró: `');`. Este código es sintácticamente incorrecto.

Aquí es donde las comillas dobles nos ayudan. Esta versión del programa funcionará correctamente:

```php
<?php

print_r("La madre del dragón");
```

Ahora el intérprete sabe que la cadena de texto comenzó con una comilla doble, por lo que debe terminar con una comilla doble. Y la comilla simple dentro de la cadena se convirtió en parte de la cadena.

Lo mismo ocurre al revés. Si queremos usar comillas dobles dentro de una cadena, debemos hacer la cadena en comillas simples. Y la cantidad de comillas dentro de la cadena no importa.

Ahora imaginemos que queremos crear esta cadena:

<pre class='hexlet-basics-output'>
La madre del dragón dijo "No"
</pre>

En esta cadena hay comillas simples y dobles. En esta situación, debemos indicarle al intérprete que cada comilla debe considerarse parte de la cadena, no como el inicio o el final.

Para esto, **escapamos** los caracteres especiales. En nuestro caso, el carácter que indica el final y el inicio de la cadena, ya sea una comilla simple o doble, dependiendo de la situación. Para escapar un carácter, usamos una barra invertida `\`.

```php
<?php

// Solo se escapa ", ya que en esta situación
// las comillas dobles tienen un significado especial
print_r("La madre del dragón dijo \"No\"");
// => La madre del dragón dijo "No"
```

Tuvimos que agregar `\` para las comillas dobles, pero no para el apóstrofe, porque la cadena misma se creó con comillas dobles. Si la cadena se hubiera creado con comillas simples, entonces se necesitaría un carácter de escape antes del apóstrofe, pero no antes de las comillas dobles.

```php
<?php

// \ se muestra si después de él viene un carácter normal,
// no un carácter especial
print_r("La muerte es \tan terriblemente final");
// => La muerte es \tan terriblemente final
```

También puede ser necesario imprimir la barra invertida en sí:

```php
<?php

print_r("\\");
// => \
```

Esto también se puede hacer escapando la barra invertida.

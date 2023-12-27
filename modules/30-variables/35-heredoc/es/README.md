En PHP, se pueden definir cadenas de texto utilizando la sintaxis especial de heredoc. Después del operador `<<<`, se debe especificar un identificador con un nombre arbitrario, seguido de un salto de línea y la cadena de texto en sí. Al final, se agrega el mismo identificador que cierra la inserción. Este método es conveniente para definir cadenas de texto largas que contienen saltos de línea y comillas de diferentes tipos:

```php
<?php

$str = <<<EOT
Ejemplo de cadena de texto
que abarca varias líneas,
utilizando la sintaxis de heredoc.
Aquí no es necesario escapar ni las comillas simples ' ni las comillas dobles ".
EOT;
print_r($str);
// => Ejemplo de cadena de texto
// => que abarca varias líneas,
// => utilizando la sintaxis de heredoc.
// => Aquí no es necesario escapar ni las comillas simples ' ni las comillas dobles ".
```

Antes del identificador de cierre, en nuestro caso 'EOT', no deben haber espacios en blanco, de lo contrario, PHP mostrará un error de sintaxis.

¿Alguna vez te has preguntado cómo se almacena el tiempo en una computadora? En esta lección discutiremos cómo funcionan el tiempo y la fecha, y dónde se almacenan.

## Tiempo

Como sabes, encender y apagar la computadora no afecta los relojes. Podemos concluir que los relojes en la computadora funcionan por sí mismos.

Esto es realmente cierto. Los relojes principales de la computadora son **hardware**. Viven una vida independiente y tienen su propia batería. Al encender la computadora, lee los datos de estos relojes, los guarda en la memoria y comienza a contar el tiempo de forma independiente. Estos relojes se llaman **sistema**. Cualquier cambio en los relojes del sistema también afecta a los relojes de hardware.

En Linux, Unix, MacOS y la mayoría de otros sistemas operativos, el tiempo del sistema se representa en formato _Unix Time_. Se define como la cantidad de segundos transcurridos desde este momento:

> 00:00:00 UTC 1 de enero de 1970 (jueves)

El tiempo desde este momento se llama "época de Unix" (_Unix Epoch_). El tiempo Unix se representa como un número entero que aumenta con cada segundo transcurrido, sin necesidad de cálculos para determinar el año, mes, día, hora o minuto.

Una fecha específica en formato Unix Time se llama **timestamp** - sello de tiempo. Por ejemplo, para obtener el _timestamp_ actual en PHP, se utiliza la función `time()`:

```php
<?php

time(); // 1532435204
```

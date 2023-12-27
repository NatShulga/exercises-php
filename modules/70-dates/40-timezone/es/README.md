Una de las partes más complicadas al trabajar con fechas son las zonas horarias (_time zones_).

La Tierra se divide en 24 zonas horarias, por lo que en zonas adyacentes, la hora suele diferir en una hora. El tiempo universal coordinado (UTC) se considera el tiempo cero. Las zonas horarias alrededor del mundo se expresan como un desplazamiento positivo o negativo con respecto al UTC. Por ejemplo, en Moscú, la zona horaria es +3.

Un detalle interesante de este mecanismo es el cambio de horario de verano e invierno. Mientras que las zonas horarias son fijas, el cambio de horario de verano e invierno es una prerrogativa de los países que periódicamente lo implementan o lo cancelan. El tiempo UTC nunca se cambia, los desplazamientos ocurren en relación a él. Además, hay mil y un problema más.

La regla principal al trabajar con fechas es almacenar y comparar en formato UTC. Sin embargo, es mejor mostrar las fechas en la zona horaria del usuario.

Si necesita verificar la zona horaria actual, puede utilizar la función `date_default_timezone_get()`. Para establecer la zona, utilice la función `date_default_timezone_set()`.

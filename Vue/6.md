¡Muy bien! Ya has realizado una buena parte de nuestro curso de Vue. Como has podido ver hasta este momento, hemos usado varias **directivas**, y unas **directivas** pueden ser más largas que otras. Es por esto que Vue tiene ciertos **atajos** para estas **directivas** que son un poco más largas de escribir.

Esto parece poco importante,  sin embargo, estos **atajos** son muy usados en codificación Vue a nivel profesional, y al momento que te encuentres con código  de este tipo te resultará confuso leerlo y nosotros no queremos que pase eso, nosotros te queremos listo para el mundo actual.

Entonces, vamos a refactorizar estas **directivas** comenzando por la **directiva v-on**. Para la **directiva v-on**, removemos toda la directiva incluyendo los **dos puntos**, y lo cambiamos por un signo arroba **“@”**. Por el otro lado, para la **directiva v-bind**, removemos toda la **directiva**, pero esta vez, conservamos los dos puntos, por lo cual, nuestra directiva solo empieza con **dos puntos**:

```j
:key
@click
:class
```

En cuanto a las otras **directivas**, estas no tienen un **atajo**. Para más información respecto a este tema, puedes dar clic [aquí](https://es.vuejs.org/v2/guide/syntax.html).

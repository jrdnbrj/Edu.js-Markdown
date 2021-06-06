Debido a que Vue es un framework reactivo, Vue maneja **estados**. Nuestra aplicación renderizará data acorde al **estado** de la aplicación. Si nuestra aplicación se encuentra en un **estado** vacío en la cual no tiene ninguna **nota**; a través de un mensaje, le haremos saber al usuario que no existen **notas** guardadas.

Como sabemos, nuestras **notas** se encuentran dentro de nuestro **unordered list
(ul)**. Nuestra misión es renderizar nuestro **unordered list** solo en el caso de que existan **notas**. Para esto, nos apoyamos de una **directiva** llamada **v-if**. Nuestra **directiva** es condicional, por la cual necesita de una condición dentro de las comillas. Si la condición es verdadera, nuestro **unordered list** será renderizado, si la condición es falsa no se renderizará.

La condición que usaremos será revisar si existe alguna **nota** dentro de nuestro **Array**. Gracias a Javascript, nos podemos apoyar en la propiedad **length** de un **Array**, por ende, si no existe nada en el **Array**, **length** será igual a 0, por lo contrario, si existen **notas** dentro del **Array**, **length** tendrá un valor superior a 0.

En Javascript, el 0 es un valor considerado **false**, y cualquier otro valor superior a 0 se lo considera como un **true**. Una vez explicado esto, podemos pasar a codificar nuestra condición:

```jsx
<ul v-if=“notas.length”> 
```

En referencia al código anterior, estamos indicando que, en el caso de ser verdadero, se renderice el **unordered list** si el **length** tiene alguna **nota**. Por otro lado, debemos indicar un mensaje en el caso de que no existan notas. Para esto, igualmente con la **directiva v-if**, verificamos si nuestro **notas.length** es falso, en caso de serlo, desplegamos el mensaje **“No hay notas guardadas”**.

Colocamos un párrafo que se renderice arriba de nuestro **unordered list**, y usamos un **!** para invertir nuestra condición, y así determinar si **notas.length** es falso. El código se vería de esta forma:

```jsx
<p v-if=“!notas.length”>No hay notas guardadas</p> 
<ul v-if=“notas.length”> 
```

Podemos borrar la información momentánea dentro de nuestro **Array notas** para probarlo.

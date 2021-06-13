Los **eventos** en Vue pueden ser manejados a través de la directiva **v-on**. Esta directiva permitirá escuchar los eventos DOM y ejecutar código cuando se activan. En este caso activaremos un botón a través de un clic. A diferencia de las otras **directivas** que hemos visto, esta necesita del indicativo **click**.

Se preguntarán para que servirá el botón que vamos a crear. Vamos a permitir que, al dar un clic en el título de la **nota**, se pueda desplegar el contenido de esa **nota** que vamos a darle un clic. Sin embargo, debido a que estamos dentro de un bucle **v-for**, nuestro **nota.titulo** siempre será la **nota** en la que estemos actualmente y no queremos eso, queremos que la **nota** que desplegamos el contenido sea la nota a la cual daremos un clic. Es por esto que debemos indicarle a nuestra **directiva** que al momento de usar nuestro **evento  click**, asocie esa **nota** a una propiedad dentro del objeto **data** que llamaremos **notaActual**. De este modo, siempre que demos clic al título de una **nota**, esa será nuestra **nota** actual. Entonces primeramente vamos a declarar esa propiedad y llenaremos nuestro **Array** con información  momentánea solo para que lo puedan visualizar:

```jsx
data: function() {
	return{
		notas:  [  {titulo: "título", contenido: "contenido"}],
		notaActual: null
	}
}
```

Ahora si, en nuestro HTML, dentro de nuestro bucle insertamos el botón con su respectivo **evento**:

```jsx
<li v-for="nota in notas" v-bind:key="nota.titulo">
	<button v-on:click="notaActual = nota">{{ nota.titulo }}</button>
</li>
```

Listo, lo último que nos falta hacer es desplegar el contenido de esa **nota** con su título dentro de un contenedor. En este caso, este contenedor será una clase que desplegará el título y el contenido como un párrafo afuera de nuestro **nav**. Es importante indicar por medio de un condicional que solo renderice este contenedor si efectivamente existe una **notaActual**, de lo contrario, tendremos un error porque nuestra aplicación intentará renderizar algo que no existe. Por ende, el código quedaría de esta manera:

```jsx
<div v-if="notaActual" class= "current-note">
	<h2> {{notaActual.titulo}} </h2>
	<p > {{notaActual.contenido}} </p>
</div>
```

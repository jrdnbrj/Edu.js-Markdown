Vue maneja **directivas**, que son atributos especiales que Vue se encarga de manejarlos de una manera específica acorde a la **directiva**.

Antes de usar la directiva, primero establezcamos el tipo de dato para nuestro proyecto de ingresar notas y armemos nuestra página con HTML básico. En este caso, dentro de nuestro **data**, borraremos el **message** que teníamos y lo reemplazaremos por un **Array** vacío de notas: `notas: []`.

Por otro lado, en nuestro HTML, borramos el párrafo con nuestro message y vamos a poner nuestras notas dentro de un contenedor en el que podemos navegar. La navegación se presentará como una lista no ordenada, y la lista tendrá ítems, cada ítem es una de nuestras notas. Nuestro HTML se vería de la siguiente forma:

```jsx
<div class=“app”>
	<h1>Bienvenido al curso de Vue</h1>
	<div class=“notas”>
		<nav>
			<ul>
				<li></li>
			</ul>
		</nav>
	</div>
</div>
```

Aquí es donde entra nuestra **directiva**, en este caso usaremos la **directiva v-for**. Debido a que no queremos un solo elemento **list  item (li), v-for** me permite repetir un elemento por cada ítem que se encuentre dentro de nuestro **Array**. El **v-for** ahora necesita saber que hacer, para esto, le daremos la instrucción de **nota in notas**, que permite iterar a través de nuestro **Array  notas**, y por cada data dentro del **Array** lo está llamando **nota**. Entonces, por cada **nota** dentro del **Array**, le indicamos a Vue que queremos mostrar el título de cada **nota**:

```jsx
<li v-for=“nota in notas”>{{nota.titulo}}</li>
```

Sin embargo, vamos a tener un error debido a que cada nota dentro de notas va a necesitar un identificador. Para resolver esto, vamos a usar otra directiva llamada **v-bind** la cual va a enlazar **key** por cada **nota.titulo**:

```jsx
<li v-for="nota in notas" v-bind:key="nota.titulo">
	{{ nota.titulo }}
</li>
```

Podemos llenar nuestro **Array notas** con información momentánea para poder probarlo:

```jsx
notas: [{ titulo: "prueba 1" }, { titulo: "prueba 2" }],
```

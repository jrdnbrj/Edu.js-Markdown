Vue es un framework que trabaja de manera progresiva. Se encarga de construir interfaces de usuario. La gran ventaja de Vue, es que su diseño permite un enfoque que se adapta fácilmente al incremento de trabajo. La biblioteca principal de Vue está enfocada en la capa de vistas y puede trabajar fácilmente con otras bibliotecas. Para más información acerca de Vue, puede hacer clic [aquí](https://vuejs.org/v2/guide/).

Con Vue, es importante trabajar con **HTML** y **Javascript** de manera conjunta dentro de la carpeta **src**, tenemos el archivo **App.vue**. Entonces, vamos a demostrar cómo estas tecnologías pueden funcionar para imprimir nuestro primer **Hello World**.

En **App.vue**, el **HTML** está dentro de nuestro elemento `<template> </template>`, y nuestro **Javascript** está dentro de nuestro elemento `<script></script>`. Comenzaremos inicializando la funcionalidad de nuestro **App**, que tiene un nombre y lo haremos en nuestro **Javascript**. Una forma de hacer esto es de la siguiente manera:

```jsx
<script>
	export default {
		name: "App",
	};
</script>
```

Ahora bien, nuestro **App** está vacía, así que le pasaremos un objeto **data**, que establece datos que el componente puede usar, en este caso, ese dato es nuestro string **Hello  World**:

```jsx
export default {
	name: "App",
	data: function() {
		return { message: "Hello  World", }
	}
};
```

Ahora para poder usar esa data y poder mostrarla, pasemos a nuestro **HTML**. En nuestro **template**, encontraras un contenedor básico de **HTML**. Utilizando la etiqueta de párrafo, mostraremos nuestro mensaje que estará dentro de dos conjuntos de llaves: `{{message}}`. Se vería de esta manera:

```jsx
<template>
	<div class=“app”>
		<h1>Bienvenido al curso de Vue</h1>
		<p>{{message}}</p>
	</div>
</template>
```

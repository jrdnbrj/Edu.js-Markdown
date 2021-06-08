Nuestro proyecto va en buen camino, pero hay que tomar en cuenta que los usuarios no van a ingresar datos a través del Javascript llenando el **Array**. Eso solo lo hicimos para nosotros mismos poder visualizar como se vería en nuestra aplicación. Así que podemos borrar la data ingresada dentro de nuestro **Array notas**.

Para que nuestros usuarios ingresen las notas dentro de la pantalla, vamos a utilizar un **método** que permita establecer una **nota** con título y contenido en blanco, y posteriormente realizar un **push** dentro de nuestro **Array**. Entonces, primeramente, debemos declarar un atributo dentro de nuestro constructor Vue al cual llamaremos **methods**. **Methods** en realidad es un objeto, y dentro de este objeto, vamos a pasar un **método** llamado `crearNota()`. Dentro de nuestro **método**, necesitamos establecer la **nota** en blanco y después podemos realizar el **push** dentro de nuestro **Array notas**. Igualmente, necesitamos pasar la **notaActual** como una **nuevaNota** para que la **notaActual** siempre se establezca como la **nuevaNota**:

```jsx
methods: {
	crearNota(){
		const nuevaNota = {titulo: '', contenido: ''};
		this.notas.push(nuevaNota);
		this.notaActual = nuevaNota;
	}
}
```

En referencia al código anterior, el **this.notas** está referenciando el mismo **Array notas** que pasamos dentro de **data**.

Finalmente, tenemos que llamar a este **método** dentro de nuestro **HTML**. Así que alado de nuestro **Bienvenido al curso de Vue**, vamos a crear un elemento **botón** que al momento de realizar un evento clic, llame a nuestro **método**:

```jsx
<h1> Bienvenido al curso de Vue </h1> <button @click=“crearNota” class=“create-new-button"> Crear nota </button>
```

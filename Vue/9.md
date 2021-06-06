Al momento de hacer clic en el **botón** de **Crear nota**, podemos observar que se enfoca en el espacio de la nueva **nota**, pero no se enfoca en el punto de inserción en el campo del título. Hacer este enfoque brindará una mejor experiencia al usuario debido a que le indica en que parte puede escribir. Para realizar esto, nos vamos a ayudar de **referencias** para que se haga **referencia** a ese punto de inserción.

Para lograr esto, necesitamos que dentro de nuestro **input** del **titulo**, añadir un atributo **ref** y le pasamos un campo al cual llamaremos **notaTitulo**:

```jsx
<input v-model= “notaActual.titulo”  type="text"  ref= “notaTitulo” >
```

Entonces, hay que **referenciarlo** dentro de nuestro **método** **crearNota** en nuestro  Javascript, y para poder enfocarlo debemos usar el **método** `focus()` de Vue que permite enfocar un elemento:

```jsx
this.$refs.notaTitulo.focus();
```

Ahora si lo probamos, nos fijamos que no sirve para la primera **nota**, pero si para las que vienen después de esa. Esto es porque nuestros campos **titulo** y **contenido** no se muestran a menos que exista una **notaActual** establecida. Cuando creamos una nueva **nota** y esta realiza un **push** en el **Array**, existe una fracción de segundo entre lo que la data cambia y recibe una nueva **nota** en blanco, y el tiempo en el que Vue renderiza esos nuevos elementos porque ahora ya tiene una **notaActual** establecida. Entonces Vue, está tratando de enfocar un elemento que todavía no existe en la página. Para solucionar esto, necesitamos decirle a Vue que espere entre el tiempo en que añadimos una nueva **nota** en el **Array** y el tiempo en que tratamos de enfocar el campo de entrada del título.

Nuestra instancia Vue, tiene un método llamado **$nextTick** al cual se le puede pasar una función, y lo que hará será que mantendrá esa función hasta que se haya renderizado el DOM, y después llamará a esa función:

```jsx
methods: {
	crearNota(){
		const  nuevaNota = {titulo: ‘’, contenido: ‘’ };
		this.notas.push(nuevaNota);
		this.notaActual = nuevaNota;
		this.$nextTick(function() {
			this.$refs.notaTitulo.focus();
		});
	}
}
```

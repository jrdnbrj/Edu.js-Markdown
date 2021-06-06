Las referencias se las puede usar como un atributo llamado **ref** que se puede agregar a cualquier componente. Este atributo **ref** es un objeto que permite tener acceso a la instancia del componente o al DOM del elemento. DOM se refiere a la estructura que contiene todas las propiedades y elementos de un determinado sitio web. Gracias a los hooks de React, existe un hook dedicado de React para manipular las referencias. El hook es **useRef** que debemos importarlo dentro de nuestro **App.js**.

Este hook nos permitirá referenciar elementos dentro de nuestro JSX. En este caso, es necesario referenciar el elemento **input** en el cual la referencia se le asignará una variable para poder tomar los valores dentro de ese **input**. Nuestra variable la llamaremos **tareaNombreRef**: `<input ref= {tareaNombreRef} type=“text” />`

Debemos declarar la variable dentro del componente **App** de la manera: **const**  `tareaNombreRef = useRef()`.  Para tener acceso al valor del elemento input que está dentro de la variable **tareaNombreRef** debemos crear una variable que sea equivalente a lo mencionado. Dentro de la función **agregarTarea** defino una variable llamada **nombre**:

```jsx
const nombre = tareaNombreRef.current.value
```

En el código de arriba, la palabra **current** se refiere al elemento actual que estamos referenciando de la lista, y la palabra **value** se refiere al valor de ese elemento.

Pero... ¿Qué pasa si el usuario accidentalmente hace clic en el botón por más de que no se haya escrito algún texto? Debemos evitar esto, y lo hacemos a través de una condición en la que si nuestra variable **nombre** está vacía solo realizamos un **return** para no añadirlo a la lista:

```jsx
if (nombre === ‘’) return
```

Muy bien, sin embargo, nos falta actualizar nuestras tareas ya que no se quedarán estáticas. Por fin usaremos la función que declaramos en el **Módulo 3: Estados y Hooks**, la función **setTareas**. Para actualizar la información podemos pasar los valores previos y hacer una llamada a la función **prevTareas** la cual nos entrega todos nuestros valores previos para poder cambiarlos. En este caso, el valor **id** será establecido a la función de la librería de **uuidv4** que fue añadido para generar identificadores únicos, el valor **nombre** será establecido a **nombre** y el valor booleano **completado** será  establecido como **false** porque las tareas añadidas no están completadas apenas las agregamos:

```jsx
setTareas ( prevTareas => {
	return [...prevTareas, { id: uuidv4(), nombre: nombre, completado: false }]
})
```

En el código de arriba, los tres puntos indican que lo extendemos a través del **Array**.

Solo por eficiencia, añadimos una línea de código dentro de la función **agregarTarea** para limpiar el espacio de texto del elemento **input** cada vez que agregamos una nueva **tarea** con el **botón “Añadir Tarea”**. Y de esta manera, no tenemos que borrar lo que ya escribimos:

```jsx
tareaNombreRef.current.value = null
```

Para poder mostrar estos elementos en pantalla debemos movernos al componente **Tarea.js**, y dentro del contenedor **div** añadimos la etiqueta **label** para que dentro de esta tengamos un rótulo en donde añadimos un input de tipo **checkbox** que contenga el atributo de **checked** establecido al elemento de **completado** y después de este, se despliegue el elemento de nombre del componente de **Tarea**.

```jsx
<div>
	<label>
		<input type=“checkbox” checked={tarea.completado} />
		{tarea.nombre}
	</label>
</div>
```

Por último, dentro de **TareasLista.js** debemos cambiar la **key** de **tarea** a `tarea.id`.

Si nos fijamos en nuestra lista, no podemos modificar la caja del check. Y es imprescindible hacer esto en una agenda de tareas para marcar las que se han culminado o desmarcarlas en caso de que se haya marcado por accidente.

Utilizaremos una función llamada `marcadoTarea(`) que recibe solo el id de la tarea como parámetro. Dentro de esta función creamos una nueva lista **(nuevaListaTareas)** de las tareas que será una copia de la lista de tareas que ya tenemos, esto es debido a que no es factible modificar el estado de una variable directamente, sino que establecemos la lista en base a la copia de la lista.

Dentro de esta copia, buscamos la tarea que sea igual al **id** que pasamos como parámetro y lo establecemos a una variable **tarea**. Escribimos una línea de código que funciona como palanca del marcado de la caja `(tarea.completado = !tarea.completado)`, debemos notar que el signo **!** sirve para indicar el opuesto. Y finalmente, pasamos esta nueva lista a la función de **setTareas** que es usada para la actualización de información:

```jsx
function  marcadoTarea(id) {
	const  nuevaListaTareas = [...tareas]
	const tarea = nuevaListaTareas.find(tarea => tarea.id === id)
	tarea.completado = !tarea.completado
	setTareas(nuevaListaTareas)
}
```

Debemos considerar que aún no podemos usar esa función, por lo cual lo debemos pasar como un **prop** `(marcadoTarea= {marcadoTarea} )` dentro del componente **TareasLista** que está declarado dentro del **return** del componente **App**. Así mismo, dentro de **TareasLista.js** pasamos el **marcadoTarea** como otro parámetro y como otro **prop**.

Por último, dentro de nuestro **Tarea.js** pasamos nuevamente el **marcadoTarea** como un parámetro, pero esta vez no como un **prop**. Esto se debe a que necesitamos del evento **onChange** dentro del **input** para llamar a una función `(manejoTareaClic())` que vamos a declarar dentro del componente **Tarea**. El `manejoTareaClic()` va a ser el que llame a la función `marcadoTarea()` y asegurarnos de pasarle el **id** de la **tarea** en la que nos encontramos:

```jsx
function  manejoTareaClic  () {
	marcadoTarea(tarea.id)
}

return (
	<div>
		<label>
			<input type=”checkbox” checked={tarea.completado} onChange={manejoTareaClic} />
			{tarea.nombre}
		</label>
	</div>
)
```

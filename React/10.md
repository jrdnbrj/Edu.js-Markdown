¡Felicidades, has llegado al último módulo del curso de React!

Como podrán notar, nuestro “0 tareas por terminar” que se encuentra dentro de nuestro **div** aún sigue estático. Necesitamos que eso cambie para mostrarnos las tareas que aún no han sido marcadas como completadas. Para esto, usaremos filtros para filtrar todas las tareas que no están marcadas. Procedemos a borrar el 0 que teníamos escrito y lo cambiamos por nuestro filtro que nos entrega la extensión de elementos que no están marcados dentro de la lista:

```jsx
<div> {tareas.filter(tarea => !tarea.completado).length}  tareas por terminar </div>
```

Y finalmente, para darle uso a nuestro segundo **botón**, debemos indicarle que a través del evento **onClick** llame a la función **manejoLimpiarTareas**. Dentro de esta función, creamos una lista que reciba a través del filtro todas las tareas que no están completadas, y esta nueva lista la pasamos a nuestra función de `setTareas()` para que se actualice apropiadamente:

```jsx
function manejoLimpiarTareas(id) {
	const nuevaListaTareas = tareas.filter(tarea => !tarea.completado)
	setTareas(nuevaListaTareas)
}
```

Eso será todo por este curso, al pasar este módulo, tu prueba de certificación de React se desbloqueará. ¡Buena suerte!

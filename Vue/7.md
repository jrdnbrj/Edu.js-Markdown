Vue maneja el concepto de **enlace de datos bidireccional** que se refiere a tomar data del Javascript y enlazarlo a un elemento de la interfaz de usuario en el HTML. Esto resulta beneficioso debido a que cuando uno de los dos cambia, el otro se actualiza automáticamente.

Desafortunadamente, no funciona con todos los elementos. Así que nuestro párrafo donde renderizamos el contenido de la **nota**, lo tenemos que borrar y actualizar a **textarea**. Además, vamos a usar la **directiva v-model** y pasarle como `notaActual.contenido`, esto permite que el contenido dentro de **textarea** siempre será el **notaActual.contenido** y viceversa. También vamos a cambiar el elemento **h2** por un **input** de tipo **text**, y de la misma forma usar la **directiva v-model** y pasarle como `notaActual.titulo`:

```jsx
<div  v-if= “notaActual” class= “current-note”>
	<input v-model= “notaActual.titulo”  type="text">
	<textarea v-model= “notaActual.contenido”  > </  textarea  >
</div>
```

De esta manera se aplica el enlace de datos bidireccional, ya que si, por ejemplo, el contenido dentro de **textarea** cambia, el `notaActual.contenido` también cambiará.  Cabe aclarar que de esta forma no es necesario que `notaActual.titulo` y `notaActual.contenido` estén entre dobles llaves.

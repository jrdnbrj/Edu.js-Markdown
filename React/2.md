Los elementos en React son los bloques que permiten construir en la aplicación. Estos elementos son inmutables, y por lo general, se los usa para lo que queremos ver dentro de la pantalla. Una manera eficiente de usarlos es devolverlos a través de los componentes.

Para nuestro proyecto necesitaremos añadir varios elementos. Necesitamos:

- Un input de tipo texto para poder ingresar las tareas que sean necesarias. Etiqueta: **input**.
- Dos botones, un botón que añada lo que escribimos en el input para añadirlo a la lista y otro botón que limpie las tareas marcadas como cumplidas. El texto que vaya dentro de los botones es a gusto propio. Etiqueta: **button**.
- Un contenedor que nos despliegue un mensaje de cuantas tareas nos falta por terminar. El mensaje que despliegue el contenedor es a gusto propio. Un ejemplo de esto puede ser: “0 tareas por terminar”. Etiqueta: **div**.

Todos los elementos los añadimos dentro del **return** en la **App**, y para añadirlos lo realizamos con el uso de etiquetas. Como ya sabemos, JSX soporta elementos y atributos HTML y SVG, un ejemplo de sintaxis sobre lo mencionado es: `<input type=“text” />`. En este caso, input es el elemento HTML, type es el atributo HTML y text ese el elemento SVG. Para más información acerca de esto hacer clic [aquí](https://react-cn.github.io/react/docs/tags-and-attributes.html).

¡Pero OJO! No podemos agregar cualquier cantidad de elementos dentro del **return** debido a que el **return** solo puede devolvernos un solo elemento. Entonces, para resolverlo, podemos poner todos nuestros elementos dentro de un elemento vacío (<> </>) , este elemento vacío contiene todos nuestros elementos. La estructura puede verse  de la siguiente forma:

```jsx
function App() {
	return (
		<>
			<NombreDelComponente />
			<elemento1 />
			<elemento2 />
			<elemento3 />
			<elemento4 />
		</>
	)
}
```

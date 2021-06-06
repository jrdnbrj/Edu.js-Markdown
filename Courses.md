# Curso de React

## 1 Componentes y JSX

React es una solución simple y flexible al desarrollo de aplicaciones basadas en componentes. Se centra en ser una librería de componentes y poder manejar estos a nuestro gusto.  React maneja los estados de los componentes y la lógica dentro de ellos.

React trabaja con JSX, el cual tiene una sintaxis muy parecida a HTML y usa el poder de JavaScript. JSX se compila a llamadas `React.createElement()` que retornan objetos de JavaScript llamados “elementos de React”. Para más información acerca de React haz click [aquí](https://es.reactjs.org/docs/introducing-jsx.html).  Existen ciertas diferencias importantes de sintaxis de HTML a JSX, una de ellas es la convención de nombres en camelCase (se inicia con una minúscula y cada nueva palabra está apegada y se la inicia con una mayúscula). Un ejemplo de esto sería el tabindex se convierte en tabIndex en JSX. Además, palabras como class se convierten en className y for se convierte a htmlFor debido a que son palabras reservadas de JavaScript.

Ahora bien, comencemos a programar el clásico **Hello World**, React  ya tiene un ejemplo simple para esto encontrado [aquí](https://es.reactjs.org/docs/hello-world.html). Sin embargo, para poder aprender los conceptos de componentes y JSX pondremos en práctica ambos para sacar nuestro **Hello World**. Dentro de nuestro proyecto, tenemos el componente App que es la raíz de nuestro proyecto, dentro de este componente crearemos y llamaremos a un nuevo componente funcional llamado **TareasLista**. La estructura se vería de la siguiente forma:

```jsx
import  React  from ‘react’;

function  App() {
	return (
		<NombreDelComponente />
	)
}

export default App;
```

Ahora, dentro de la carpeta “src” crearemos un nuevo archivo llamado **TareasLista.js**, este archivo contendrá nuestro componente funcional. Dentro de este nuevo archivo podemos usar el atajo de **rfc** y Enter para poder generar la sintáxis de nuestro componente funcional el cual se ve de la siguiente manera:

```jsx
import  React  from ‘react’

export default function  NombreDelArchivo() {
	return (
		<div>
		</div>
	)
}
```

Finalmente, escribimos el texto de Hello  World dentro de las etiquetas **div** e importamos este componente dentro de nuestro componente App. Para importar un componente seguimos la sintaxis: import  NombreDelComponente  from  ‘LocaciónDelArchivo’. En este caso, nuestro componente funcional está ubicado dentro de la misma carpeta src así que la locación sería ‘./NombreDelArchivo’, una vez culminada la importación del componente procedemos a ejecutar la aplicación. ¡Y listo! De esta manera renderizamos el componente **TareasLista** dentro del componente **App**, y en el componente **TareasLista** renderizamos el texto de **Hello  World**.

## 2 Elementos

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

## 3 Estados y Hooks

React maneja el estado de nuestra aplicación. Cuando un estado cambia, vuelve a renderizar la información que cambió. Esto permite que la aplicación trabaje de manera eficaz y eficiente debido a que lo realiza instantáneamente, y solo cambia la información en la que hubo un determinado cambio.

Los Hooks, son una nueva función que permite manejar el estado y el ciclo de vida desde componentes de función sin necesidad de usar alguna clase. Existen Hooks que se encuentran incorporados en React, y también, uno mismo puede programar sus propios Hooks. Para más información acerca de Hooks echa un vistazo [aquí](https://es.reactjs.org/docs/hooks-overview.html).

Para continuar con nuestro proyecto, necesitar ser capaces de establecer el estado de nuestra aplicación. En este caso, necesitamos añadir cada tarea al estado de la aplicación para que cada vez que se actualice información con respecto a una tarea, esa información vuelva a renderizarse con el cambio realizado.

Para eso, usaremos el Hook integrado en React llamado **useState**. Primeramente, debemos importar el Hook dentro del import de React y lo hacemos de esta manera: `import  React, { useState }  from  ‘react`’;

Procedemos a llamar la función **useState dentro de nuestra función App. Después, debido a que nuestra lista de tareas inicialmente no contiene nada, le pasamos como estado inicial un **Array vació ([ ])**.  Debido a que **useState** retorna un **Array**, podemos hacer uso de la desestructuración de objetos para poder extraer propiedades de esos objetos y poder vincularlos a variables.

¡Esto suena algo confuso, pero es más fácil de lo que parece!  Lo que haremos esencialmente será establecer la función **useState** como una variable con la palabra preestablecida de **const** para poder desestructurar el **Array** donde se encuentran nuestras tareas. Esto permite que tengamos dos variables, una variable es donde se encuentra cada una de nuestras tareas, y la segunda variable es una función para actualizar cada una de las tareas. Todo lo mencionado previamente, tiene la siguiente estructura:

```jsx
const [tareas, setTareas] = useState ([])
```

## 4 Props y Maps

Los **props** son esencialmente las entradas de un componente que son pasadas desde un componente a otro componente. En este caso, dentro de App, necesitamos pasar lo que se encontraba en nuestra variable **tareas** a nuestro **props** que se encuentra dentro de nuestro componente **TareasLista**. La sintaxis de esto se lo ve de la siguiente forma:

```jsx
<NombreDelComponente  nombreDelProp={nombreDeLaVariable} />
```

El nombre del **prop** puede ser igual o diferente al nombre de la variable. En este caso, yo usaré el mismo nombre **tareas**. Una vez realizado eso, necesitamos poder mostrar las entradas que se encuentran dentro de nuestro **Array** que vendrían a ser todas las **tareas**. Para esto, dentro de **TareasLista.js** necesitamos pasar el prop que creamos, en este caso el prop **tareas**. Además, vamos a crear un componente llamado **Tarea.js** y realizamos el atajo de **rfc** para generar el código usual del componente. Dentro del componente podemos pasar un elemento **tarea**. Tendría una estructura de la siguiente forma:

```jsx
export default function Tarea( {tarea} )
```

Regresamos a nuestro **TareasLista.js** e importamos nuestro componente **Tarea** como lo aprendimos anteriormente. Podemos pasar a borrar el elemento de **div** junto al **Hello World** previamente escrito, y dentro de ese **return**, vamos a mapear todas nuestras tareas. Dentro de un bucle, indicamos que, por cada **tarea** dentro de la lista de **tareas**, vamos a retornar el componente Tarea con su respectivo **prop**:

```jsx
tareas.map(tarea => { return <Tarea tarea={tarea} /> })
```

## 5 Keys

Una **key** es un atributo que es necesario incluir cuando se tiene un **Array** de elementos. Las **keys** permiten identificar a cada uno de los elementos que se encuentran dentro del **Array**, y de esta manera, cada vez que exista algún cambio de ese respectivo elemento, simplemente se visualiza la **key** del elemento que necesita cambiar, y la aplicación solo renderizará ese elemento identificado por su **key**, en vez de renderizar cada elemento dentro del **Array**. Esto permite que la aplicación se la maneje de una manera muy eficiente.

Para declarar una **key**, lo realizamos al igual que declaramos un **prop**. En el componente TareasLista.js al componente Tarea le asignamos una **key**:

```jsx
return < Tarea key= {tarea} tarea= {tarea} />
```

Ahora, para poder generar un identificador único y randómico por cada elemento que añada a nuestra lista, usaremos la ayuda de una librería **uuid** y la importaremos dentro de nuestro **App.js** de la siguiente manera:

```jsx
import  { v4 as uuidv4 }  from 'uuid';
```

## 6 Eventos

Los eventos en React son usados de manera que,  al realizar una determinada acción dentro de un elemento, este pueda llamar a una función para que se realice lo que está dentro de esa función. En este caso, necesitamos llenar la lista de tareas con las tareas que vayamos ingresando dentro de nuestro **input**, y al momento de dar clic en nuestro **botón** de añadir la tarea, se pueda agregar la tarea que digitamos dentro de nuestra lista.

Para esto, damos uso al evento de **onClick** dentro de nuestro elemento **button** y lo establecemos igual a nuestra función. Para nuestro proyecto crearemos una función llamada **agregarTarea**:

```jsx
<button  onClick= {agregarTarea} > Añadir Tarea <  /button >
```

Finalizado esto, necesitamos declarar nuestra función dentro del componente App,  indicando el parámetro de evento, el cual por preferencia se usa la letra e:

```jsx
function  agregarTarea(e) {

}
```

## 7 Referencias

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

## 8 Persistencia

Al momento de actualizar la página web, podemos observar que las tareas no se muestran. Esto es un problema de persistencia, y con React es muy fácil solucionarlo!

Podemos guardar nuestras tareas dentro del almacenamiento local, y para esto, nos ayudaremos de otro hook. El hook que usaremos es el de **useEffect**, el cual debe ser importado dentro del **App.js** como ya lo hemos aprendido.

**useEffect** es usado como una función que tiene como su primer parámetro otra función. Esta función será llamada cada vez que exista algún cambio, y para determinar cuándo será llamada debemos pasar un **Array** de propiedades. Este **Array** contendrá nuestras dependencias, que permite que cada vez que algo cambie dentro de este **Array**, la función **useEffect** es llamada. Una vez que sea llamado, guardara todas nuestras tareas.

Para guardar nuestras tareas debemos tener un item que tenga una llave ya declarada `const ALMACENAMIENTO_LOCAL_KEY = ‘tareasApp.tareas’`. Y también, debemos pasar este item como un string ayudándonos de **JSON**:

```jsx
useEffect(() => { 
	localStorage.setItem(ALMACENAMIENTO_LOCAL_KEY, JSON.stringify(tareas))
}, [tareas])
```

Una vez que nuestras tareas ya se encuentren guardadas, debemos mostrarlas. Nos podemos ayudar nuevamente de **useEffect** para tener otro efecto en donde cargamos nuestras tareas a la página web. Lo llamaremos solo una vez, para hacer esto pasamos un **Array  vacío** como dependencia, y como el **Array vacío** no cambiará, no podrá ser llamado más de una vez. Dentro de este nuevo **useEffect**, debemos declarar una variable **tareasGuardadas** para obtener la llave del item que se ha guardado y convertirlo en un Array con la ayuda de **JSON.parse()**. Finalmente, debemos pasar esta variable a nuestra funcionalidad **setTareas** solo si existen tareas guardadas:

```jsx
useEffect(() => {
	const tareasGuardadas = JSON.parse(localStorage.getItem(ALMACENAMIENTO_LOCAL_KEY))
	if (tareasGuardadas) setTareas(tareasGuardadas)
}, [])
```

## 9 Manipular Elemento

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

## 10 Filtros

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

# Curso de VUE

## 1 Componentes y Data

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

## 2 Directivas

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

## 3 Estados

Debido a que Vue es un framework reactivo, Vue maneja **estados**. Nuestra aplicación renderizará data acorde al **estado** de la aplicación. Si nuestra aplicación se encuentra en un **estado** vacío en la cual no tiene ninguna **nota**; a través de un mensaje, le haremos saber al usuario que no existen **notas** guardadas.

Como sabemos, nuestras **notas** se encuentran dentro de nuestro **unordered list
(ul)**. Nuestra misión es renderizar nuestro **unordered list** solo en el caso de que existan **notas**. Para esto, nos apoyamos de una **directiva** llamada **v-if**. Nuestra **directiva** es condicional, por la cual necesita de una condición dentro de las comillas. Si la condición es verdadera, nuestro **unordered list** será renderizado, si la condición es falsa no se renderizará.

La condición que usaremos será revisar si existe alguna **nota** dentro de nuestro **Array**. Gracias a Javascript, nos podemos apoyar en la propiedad **length** de un **Array**, por ende, si no existe nada en el **Array**, **length** será igual a 0, por lo contrario, si existen **notas** dentro del **Array**, **length** tendrá un valor superior a 0.

En Javascript, el 0 es un valor considerado **false**, y cualquier otro valor superior a 0 se lo considera como un **true**. Una vez explicado esto, podemos pasar a codificar nuestra condición:

```jsx
<ul v-if=“notas.length”> 
```

En referencia al código anterior, estamos indicando que, en el caso de ser verdadero, se renderice el **unordered list** si el **length** tiene alguna **nota**. Por otro lado, debemos indicar un mensaje en el caso de que no existan notas. Para esto, igualmente con la **directiva v-if**, verificamos si nuestro **notas.length** es falso, en caso de serlo, desplegamos el mensaje **“No hay notas guardadas”**.

Colocamos un párrafo que se renderice arriba de nuestro **unordered list**, y usamos un **!** para invertir nuestra condición, y así determinar si **notas.length** es falso. El código se vería de esta forma:

```jsx
<p v-if=“!notas.length”>No hay notas guardadas</p> 
<ul v-if=“notas.length”> 
```

Podemos borrar la información momentánea dentro de nuestro **Array notas** para probarlo.

## 4 Eventos

Los **eventos** en Vue pueden ser manejados a través de la directiva **v-on**. Esta directiva permitirá escuchar los eventos DOM y ejecutar código cuando se activan. En este caso activaremos un botón a través de un clic. A diferencia de las otras **directivas** que hemos visto, esta necesita del indicativo **click**.

Se preguntarán para que servirá el botón que vamos a crear. Vamos a permitir que, al dar un clic en el título de la **nota**, se pueda desplegar el contenido de esa **nota** que vamos a darle un clic. Sin embargo, debido a que estamos dentro de un bucle **v-for**, nuestro **nota.titulo** siempre será la **nota** en la que estemos actualmente y no queremos eso, queremos que la **nota** que desplegamos el contenido sea la nota a la cual daremos un clic. Es por esto que debemos indicarle a nuestra **directiva** que al momento de usar nuestro **evento  click**, asocie esa **nota** a una propiedad dentro del objeto **data** que llamaremos **notaActual**. De este modo, siempre que demos clic al título de una **nota**, esa será nuestra **nota** actual. Entonces primeramente vamos a declarar esa propiedad y llenaremos nuestro **Array** con información  momentánea solo para que lo puedan visualizar:

```jsx
data: {
	notas:  [  {titulo: “título”, contenido: “contenido”}],
	notaActual: null
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
<div  v-if= “notaActual” class= “current-note”>
	<h2> {{notaActual.titulo}} </h2>
	<p > {{notaActual.contenido}} </p>
</div>
```

## 5 Clases y Estilos

Las **clases** en Vue son muy buenas para dar **estilos** a un elemento. Debido a que las **clases** y los **estilos** son atributos de un elemento, se puede usar la directiva **v-bind** para enlazar ambos atributos.

En el caso de nuestro proyecto, queremos destacar el botón del título al cual se le da un clic a través de un **estilo**. Primeramente, la **clase** que usaremos será condicional, esto se debe a que tiene que existir la condición de que la **nota** dentro de nuestro bucle **for** sea la **notaActual**:

```jsx
<button  v-on:click= “notaActual = nota” v-bind:class= “{active: nota === notaActual}”> {{nota.titulo}} </button>
```

En referencia al código anterior, le pasamos un objeto a la directiva **v-bind**. El objeto  contiene una **key** y un valor, en este caso, la **key** es la **clase active** y el valor es la condición de que **nota** debe ser equivalente a **notaActual**.

## 6 Atajos

¡Muy bien! Ya has realizado una buena parte de nuestro curso de Vue. Como has podido ver hasta este momento, hemos usado varias **directivas**, y unas **directivas** pueden ser más largas que otras. Es por esto que Vue tiene ciertos **atajos** para estas **directivas** que son un poco más largas de escribir.

Esto parece poco importante,  sin embargo, estos **atajos** son muy usados en codificación Vue a nivel profesional, y al momento que te encuentres con código  de este tipo te resultará confuso leerlo y nosotros no queremos que pase eso, nosotros te queremos listo para el mundo actual.

Entonces, vamos a refactorizar estas **directivas** comenzando por la **directiva v-on**. Para la **directiva v-on**, removemos toda la directiva incluyendo los **dos puntos**, y lo cambiamos por un signo arroba **“@”**. Por el otro lado, para la **directiva v-bind**, removemos toda la **directiva**, pero esta vez, conservamos los dos puntos, por lo cual, nuestra directiva solo empieza con **dos puntos**:

```j
:key
@click
:class
```

En cuanto a las otras **directivas**, estas no tienen un **atajo**. Para más información respecto a este tema, puedes dar clic [aquí](https://es.vuejs.org/v2/guide/syntax.html).

## 7 Enlace de datos bidireccional

Vue maneja el concepto de **enlace de datos bidireccional** que se refiere a tomar data del Javascript y enlazarlo a un elemento de la interfaz de usuario en el HTML. Esto resulta beneficioso debido a que cuando uno de los dos cambia, el otro se actualiza automáticamente.

Desafortunadamente, no funciona con todos los elementos. Así que nuestro párrafo donde renderizamos el contenido de la **nota**, lo tenemos que borrar y actualizar a **textarea**. Además, vamos a usar la **directiva v-model** y pasarle como `notaActual.contenido`, esto permite que el contenido dentro de **textarea** siempre será el **notaActual.contenido** y viceversa. También vamos a cambiar el elemento **h2** por un **input** de tipo **text**, y de la misma forma usar la **directiva v-model** y pasarle como `notaActual.titulo`:

```jsx
<div  v-if= “notaActual” class= “current-note”>
	<input v-model= “notaActual.titulo”  type="text">
	<textarea v-model= “notaActual.contenido”  > </  textarea  >
</div>
```

De esta manera se aplica el enlace de datos bidireccional, ya que si, por ejemplo, el contenido dentro de **textarea** cambia, el `notaActual.contenido` también cambiará.  Cabe aclarar que de esta forma no es necesario que `notaActual.titulo` y `notaActual.contenido` estén entre dobles llaves.

## 8 Métodos

Nuestro proyecto va en buen camino, pero hay que tomar en cuenta que los usuarios no van a ingresar datos a través del Javascript llenando el **Array**. Eso solo lo hicimos para nosotros mismos poder visualizar como se vería en nuestra aplicación. Así que podemos borrar la data ingresada dentro de nuestro **Array notas**.

Para que nuestros usuarios ingresen las notas dentro de la pantalla, vamos a utilizar un **método** que permita establecer una **nota** con título y contenido en blanco, y posteriormente realizar un **push** dentro de nuestro **Array**. Entonces, primeramente, debemos declarar un atributo dentro de nuestro constructor Vue al cual llamaremos **methods**. **Methods** en realidad es un objeto, y dentro de este objeto, vamos a pasar un **método** llamado `crearNota()`. Dentro de nuestro **método**, necesitamos establecer la **nota** en blanco y después podemos realizar el **push** dentro de nuestro **Array notas**. Igualmente, necesitamos pasar la **notaActual** como una **nuevaNota** para que la **notaActual** siempre se establezca como la **nuevaNota**:

```jsx
methods: {
	crearNota(){
		const  nuevaNota = {titulo: ‘’, contenido: ‘’};
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

## 9 Referencias

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

## 10 Almacenamiento Local

¡Felicidades, has llegado al último módulo del curso de Vue!

Para que nuestro proyecto sea **persistente**, vamos a almacenar nuestra data de manera local. Para esto necesitamos de dos cosas. Primeramente, cuando las **notas** se actualizan en la aplicación, necesitamos guardar esas nuevas **notas** dentro del **almacenamiento local**. Para esto, dentro de nuestro Javascript, necesitamos un **objeto** **watch** (el cual sirve para vigilar variables dentro de nuestra aplicación).

**Watch** tendrá un **objeto** con el nombre del atributo de data que queremos recibir en **watch**, así que nuestro **objeto** se llamará **notas**. Y not**strong text**as, tendrá un **método** llamado **handler** que permite tener una opción llamada **deep** la cual verifica si valores cambiaron dentro del **Array**. Vue pasará un valor cada vez que este **método** sea llamado, a este valor lo llamaremos **nuevaNota**. El nuevo valor necesita guardarse dentro del **almacenamiento local** convirtiéndolo a **string** con la ayuda de **JSON**, utilizamos el método **setItem** para establecer lo mencionado:

```jsx
watch: {
	notas: {
		deep: true,
		handler(nuevaNota) {
			localStorage.setItem(‘notas’, JSON.stringify(nuevaNota));
		}
	},
},
```

La segunda cosa que necesitamos es, cuando la aplicación se carga, debemos ver en el **almacenamiento local** y ver si existe data almacenada para poder cargarla en nuestra aplicación. Para esto, necesitamos un **método** de Vue llamado **mounted**, el cual permite cargar nuestras **notas** fuera del almacenamiento local cuando la instancia de  Vue esté montada.

Así que, antes que nada, debemos verificar si existen **notas** guardadas en nuestro **almacenamiento local**, en el caso de que existan, vamos a establecer la instancia de la data de las notas a lo que tenemos dentro del **almacenamiento local** para **notas**. Debido a que lo que está dentro de nuestro **almacenamiento local** son **strings**, necesitamos pasar de vuelta a un **objeto Javastring** con la ayuda de **JSON** al momento de cargarlo. Obtenemos el valor del ítem que está dentro del **almacenamiento local** con el método **getItem**:

```jsx
mounted(){
	if(localStorage.getItem(‘notas’)){
		this.notas = JSON.parse(localStorage.getItem(‘notas’));
	}
}
```

Eso será todo por este curso, al pasar este módulo, tu prueba de certificación de Vue se desbloqueará. ¡Buena suerte!

# Curso de JQuery

## 1

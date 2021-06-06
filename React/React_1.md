React es una solución simple y flexible al desarrollo de aplicaciones basadas en componentes. Se centra en ser una librería de componentes y poder manejar estos a nuestro gusto.  React maneja los estados de los componentes y la lógica dentro de ellos.

React trabaja con JSX, el cual tiene una sintaxis muy parecida a HTML y usa el poder de JavaScript. JSX se compila a llamadas `React.createElement()` que retornan objetos de JavaScript llamados “elementos de React”. Para más información acerca de React haz click [aquí](https://es.reactjs.org/docs/introducing-jsx.html).  Existen ciertas diferencias importantes de sintaxis de HTML a JSX, una de ellas es la convención de nombres en camelCase (se inicia con una minúscula y cada nueva palabra está apegada y se la inicia con una mayúscula). Un ejemplo de esto sería el tabindex se convierte en tabIndex en JSX. Además, palabras como class se convierten en className y for se convierte a htmlFor debido a que son palabras reservadas de JavaScript.

Ahora bien, comencemos a programar el clásico **Hello World**, React  ya tiene un ejemplo simple para esto encontrado [aquí](https://es.reactjs.org/docs/hello-world.html). Sin embargo, para poder aprender los conceptos de componentes y JSX pondremos en práctica ambos para sacar nuestro **Hello World**. Dentro de nuestro proyecto, tenemos el componente App que es la raíz de nuestro proyecto, dentro de este componente crearemos y llamaremos a un nuevo componente funcional llamado **TareasLista**. La estructura se vería de la siguiente forma:

```
import  React  from ‘react’;

function  App() {
	return (
		<NombreDelComponente />
	)
}

export default App;
```

Ahora, dentro de la carpeta “src” crearemos un nuevo archivo llamado **TareasLista.js**, este archivo contendrá nuestro componente funcional. Dentro de este nuevo archivo podemos usar el atajo de **rfc** y Enter para poder generar la sintáxis de nuestro componente funcional el cual se ve de la siguiente manera:

```
import  React  from ‘react’

export default function  NombreDelArchivo() {
	return (
		<div>
		</div>
	)
}
```

Finalmente, escribimos el texto de Hello  World dentro de las etiquetas **div** e importamos este componente dentro de nuestro componente App. Para importar un componente seguimos la sintaxis: import  NombreDelComponente  from  ‘LocaciónDelArchivo’. En este caso, nuestro componente funcional está ubicado dentro de la misma carpeta src así que la locación sería ‘./NombreDelArchivo’, una vez culminada la importación del componente procedemos a ejecutar la aplicación. ¡Y listo! De esta manera renderizamos el componente **TareasLista** dentro del componente **App**, y en el componente **TareasLista** renderizamos el texto de **Hello  World**.

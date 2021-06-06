React maneja el estado de nuestra aplicación. Cuando un estado cambia, vuelve a renderizar la información que cambió. Esto permite que la aplicación trabaje de manera eficaz y eficiente debido a que lo realiza instantáneamente, y solo cambia la información en la que hubo un determinado cambio.

Los Hooks, son una nueva función que permite manejar el estado y el ciclo de vida desde componentes de función sin necesidad de usar alguna clase. Existen Hooks que se encuentran incorporados en React, y también, uno mismo puede programar sus propios Hooks. Para más información acerca de Hooks echa un vistazo [aquí](https://es.reactjs.org/docs/hooks-overview.html).

Para continuar con nuestro proyecto, necesitar ser capaces de establecer el estado de nuestra aplicación. En este caso, necesitamos añadir cada tarea al estado de la aplicación para que cada vez que se actualice información con respecto a una tarea, esa información vuelva a renderizarse con el cambio realizado.

Para eso, usaremos el Hook integrado en React llamado **useState**. Primeramente, debemos importar el Hook dentro del import de React y lo hacemos de esta manera: `import  React, { useState }  from  ‘react`’;

Procedemos a llamar la función **useState dentro de nuestra función App. Después, debido a que nuestra lista de tareas inicialmente no contiene nada, le pasamos como estado inicial un **Array vació ([ ])**.  Debido a que **useState** retorna un **Array**, podemos hacer uso de la desestructuración de objetos para poder extraer propiedades de esos objetos y poder vincularlos a variables.

¡Esto suena algo confuso, pero es más fácil de lo que parece!  Lo que haremos esencialmente será establecer la función **useState** como una variable con la palabra preestablecida de **const** para poder desestructurar el **Array** donde se encuentran nuestras tareas. Esto permite que tengamos dos variables, una variable es donde se encuentra cada una de nuestras tareas, y la segunda variable es una función para actualizar cada una de las tareas. Todo lo mencionado previamente, tiene la siguiente estructura:

```jsx
const [tareas, setTareas] = useState ([])
```

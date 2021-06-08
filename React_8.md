Al momento de actualizar la página web, podemos observar que las tareas no se muestran. Esto es un problema de persistencia, y con React es muy fácil solucionarlo!

Podemos guardar nuestras tareas dentro del almacenamiento local, y para esto, nos ayudaremos de otro hook. El hook que usaremos es el de **useEffect**, el cual debe ser importado dentro del **App.js** como ya lo hemos aprendido.

**useEffect** es usado como una función que tiene como su primer parámetro otra función. Esta función será llamada cada vez que exista algún cambio, y para determinar cuándo será llamada debemos pasar un **Array** de propiedades. Este **Array** contendrá nuestras dependencias, que permite que cada vez que algo cambie dentro de este **Array**, la función **useEffect** es llamada. Una vez que sea llamado, guardara todas nuestras tareas.

Para guardar nuestras tareas debemos tener un item que tenga una llave ya declarada `const ALMACENAMIENTO_LOCAL_KEY = 'tareasApp.tareas'`. Y también, debemos pasar este item como un string ayudándonos de **JSON**:

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

Los **props** son esencialmente las entradas de un componente que son pasadas desde un componente a otro componente. En este caso, dentro de App, necesitamos pasar lo que se encontraba en nuestra variable **tareas** a nuestro **props** que se encuentra dentro de nuestro componente **TareasLista**. La sintaxis de esto se lo ve de la siguiente forma:

```jsx
<NombreDelComponente  nombreDelProp={nombreDeLaVariable} />
```



El nombre del **prop** puede ser igual o diferente al nombre de la variable. En este caso, yo usaré el mismo nombre **tareas**. Una vez realizado eso, necesitamos poder mostrar las entradas que se encuentran dentro de nuestro **Array** que vendrían a ser todas las **tareas**. Para esto, dentro de **TareasLista.js** necesitamos pasar el prop que creamos, en este caso el prop **tareas**. Además, vamos a crear un componente llamado **Tarea.js** y digitamos el código básico que se aprendió en el primer módulo para poder crear un componente funcional de React. Dentro del componente podemos pasar un elemento **tarea**. Tendría una estructura de la siguiente forma:

```jsx
export default function Tarea( {tarea} )
```

Regresamos a nuestro **TareasLista.js** e importamos nuestro componente **Tarea** como lo aprendimos anteriormente. Podemos pasar a borrar el elemento de **div** junto al **Hello World** previamente escrito, y dentro de ese **return**, vamos a mapear todas nuestras tareas. Dentro de un bucle, indicamos que, por cada **tarea** dentro de la lista de **tareas**, vamos a retornar el componente Tarea con su respectivo **prop**:

```jsx
tareas.map(tarea => { return <Tarea tarea={tarea} /> })
```

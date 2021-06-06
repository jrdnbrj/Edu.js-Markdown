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

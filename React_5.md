Una **key** es un atributo que es necesario incluir cuando se tiene un **Array** de elementos. Las **keys** permiten identificar a cada uno de los elementos que se encuentran dentro del **Array**, y de esta manera, cada vez que exista algún cambio de ese respectivo elemento, simplemente se visualiza la **key** del elemento que necesita cambiar, y la aplicación solo renderizará ese elemento identificado por su **key**, en vez de renderizar cada elemento dentro del **Array**. Esto permite que la aplicación se la maneje de una manera muy eficiente.

Para declarar una **key**, lo realizamos al igual que declaramos un **prop**. En el componente TareasLista.js al componente Tarea le asignamos una **key**:

```jsx
return < Tarea key= {tarea} tarea= {tarea} />
```

Ahora, para poder generar un identificador único y randómico por cada elemento que añada a nuestra lista, usaremos la ayuda de una librería **uuid** y la importaremos dentro de nuestro **App.js** de la siguiente manera:

```jsx
import  { v4 as uuidv4 }  from 'uuid';
```

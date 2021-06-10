**jQuery** brinda nos permite ser muy creativos de distintas formas, una de ellas, es usando **animaciones**. Vamos a usar dos **animaciones** al momento de eliminar uno de nuestros ítems de la lista de compras. Las dos **animaciones** serán las de rayar una línea encima del ítem y después desvanecerlo.  

Dentro del **método function** que está en la **sentencia** creada en el módulo previo, vamos a usar **$(this)**. **$(this)** es un **selector** que sirve para posicionarnos en el **elemento** que estamos usando actualmente y poder interactuar con sus **elementos hijos**. Después, llamamos al **método toggleClass()** que sirve para agregar o eliminar una o más **clases** de cada **elemento**, en nuestro caso, tenemos una **clase** llamada **strike** dentro del **CSS**, esta **clase** se encargará de animar la raya que pasará a través del texto del ítem: 

```jsx 

$(document).on('dblclick', 'li', function() { 

    $(this).toggleClass('strike') 

}); 

``` 

Para nuestra segunda **animación**, podemos anidar **métodos** poniendo un **punto** al final de cada **método**. El segundo **método** que usaremos será el de **fadeOut()**, que nos permite ocultar elementos desvaneciéndolos, y le pasamos como parámetro los **milisegundos** que tomará esta **animación**, y un **método function** para que una vez que lo haya desvanecido, lo remueva por completo de nuestro **document** con la ayuda del **método remove()**: 

```jsx 

$(document).on('dblclick', 'li', function() { 

    $(this) 

      .toggleClass('strike') 

      .fadeOut(500, function() { 

        $(this).remove(); 

      }); 

  }); 

 

``` 

Finalmente, dentro de nuestro **index.html**, debajo de nuestro título de bienvenida, añadimos un **párrafo** con el mensaje de que a través de un doble clic se pueden borrar ítems. Podemos usar la **etiqueta em**, para darle énfasis al mensaje: 

`<p><em> Doble clic para eliminar un ítem </em></p>` 

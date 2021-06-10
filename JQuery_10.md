¡Felicidades, has llegado al último módulo del curso de **jQuery**! 

Al borrar **list items** dentro de nuestra página, vemos que desaparecen, sin embargo, al momento de refrescar la página, los **ítems eliminados** de la **lista** de compras se siguen mostrando. Esto se debe a que siguen en **almacenamiento local** y seguimos mostrando lo que está en **almacenamiento local**. 

Para solventar esto, dentro de nuestro **método** para borrar **ítems** de la **lista**, vamos a crear una **variable indice** que será equivalente a lo siguiente: 

`var indice = $('li').index($(this));` 

Observando el código anterior, estamos seleccionando un **li**, y con el **método index()**, estamos buscando un **elemento** dado entre los **elementos**, ese **elemento** es el **elemento** que estemos usando y nos posicionamos en el gracias a `$(this)`.  

Ahora, vamos a **filtrar** nuestra **variable global**. Para **filtrarlo**, vamos a usar el **método filter()** que recibe **dos elementos**, el primer **elemento** es el **nombre** de los **elementos** que están dentro del **Array** y el segundo **elemento** es **index** que es por el cual nuestro **filter** está iterando. 

**Filter** deja pasar a todos los **elementos** de un **Array** que cumplan con la **validación** que le indico. Debido a que **indice** e **index** tiene el mismo orden en cuanto al **índice**, si borramos un elemento, solo se elimina en el **índice** de nuestra **lista**, pero no de nuestro **índice** de nuestro **almacenamiento global**. Entonces, con la **validación** `indice != index`, no va a pasar a **indice**, y queda eliminado de nuestra **variable global**: 
```jsx 
window.listaCompras = window.listaCompras.filter( 

      (compra, index) => indice != index 

); 
```
Finalmente, como nuestra **variable global** ya está **filtrada** por lo valores que son, podemos establecer sus **ítems** dentro de **almacenamiento local** con el **método setItem()** como lo hicimos en el **módulo 8**, y todo el **método** quedaría de la siguiente manera: 

```jsx 
$(document).on('dblclick', 'li', function() { 
    $(this) 
      .toggleClass('strike') 
      .fadeOut(500, function() { 
        $(this).remove(); 
      }); 
    var indice = $('li').index($(this)); 
    window.listaCompras = window.listaCompras.filter( 
      (compra, index) => indice != index 
    ); 
    localStorage.setItem('listaCompras', JSON.stringify(window.listaCompras)); 
  }); 
``` 

Eso será todo por este curso, al pasar este módulo, tu prueba de certificación de **jQuery** se desbloqueará. ¡Buena suerte! 

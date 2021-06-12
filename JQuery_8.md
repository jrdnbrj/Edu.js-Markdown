Al refrescar nuestra página, podemos observar que nuestra data ingresada no se muestra, esto pasa porque no está guardada. Vamos a guardar nuestra data en **almacenamiento local**. Vamos a ayudarnos de una **variable global** para poder usarla en cualquier **método** o **script**; en esta **variable** tendremos un **Array vacío**. 

Para declarar esta **variable global** usamos el **objeto window** de **JavaScript**, que representa la ventana que contiene un **documento DOM**. Después, declaramos el nombre de nuestro **Array**, en este caso **listaCompras**: 

`window.listaCompras = [];` 

Listo, ya tenemos nuestra **variable global**. Ahora, dentro de nuestro **método click**, vamos a empujar la **variable toAdd** a nuestro **Array**, para empujar ítems a nuestro **Array** usamos el **método push()**. Con nuestros ítems dentro del **Array**, podemos acceder al objeto **local Storage** y agregar nuestro **Array** con el método **setItem()** que tiene dos **parámetros**, el primer **parámetro** es el nombre de la llave y el segundo es el valor de la llave: 

```jsx 
$('#button').click(function() { 
    var toAdd = $('input[name=itemCompras]').val(); 
    $('ol').append('<li>' + toAdd + '</li>'); 
    $('input').val(''); 
    window.listaCompras.push(toAdd); 
    localStorage.setItem('listaCompras', JSON.stringify(window.listaCompras)); 
  }); 
``` 

En el código anterior usamos **JSON.stringify** debido a que solo podemos guardar **strings** dentro del **almacenamiento local**, entonces **JSON.stringify** nos sirve para convertir la data a **string**. 

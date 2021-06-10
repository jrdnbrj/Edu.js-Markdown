En el módulo anterior, creamos nuestra primera sentencia **jQuery**, esta sentencia contiene el método **click** el cual funciona como un **evento**, porque nos indica que, al hacer **clic** sobre un elemento, este tiene que realizar lo que esté dentro de nuestro **método function**. Ahora la pregunta es, ¿Qué exactamente hará este **evento click**? 

En este evento, necesitamos obtener la entrada del usuario. Nuestro usuario necesita un espacio en donde pueda registrar esta entrada, entonces, en nuestro **index.html**, dentro de nuestro **form**, vamos a crear un elemento **input** de tipo **text** con el nombre **itemCompras**: 

```jsx 
<form name="listaCompras"> 
        <input type="text" name="itemCompras" /> 
</form> 
``` 

Ahora, en nuestro **index.js**, dentro de nuestra función, necesitas crear una variable que la llamaremos **toAdd**, para obtener y seleccionar el valor del atributo seleccionado: 

```jsx 
$('#button').click(function() { 
    var toAdd = $('input[name=itemCompras]').val(); 
  }); 
``` 

En el código anterior, el **selector** selecciona el elemento **input** con el atributo de nombre **itemCompras**, y tiene un **método val()** el cual selecciona el valor del atributo dado.  

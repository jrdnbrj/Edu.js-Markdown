Pero **Edu.js**, en el anterior módulo, al momento de apretar **Enter** se refresca la página, ¿Qué hice mal? 

Tranquilo programador, no has hecho nada mal. Lo que pasa es lo siguiente; en nuestro **index.html** tenemos el **elemento form** que maneja por defecto el **evento submit** cuando se aprieta la **tecla Enter**, haciendo que se envíe nuestro **formulario** y se refresque la página. Debemos evitar que esto pase. 

Para evitarlo, sobre nuestro **elemento form**, utilizaremos el **método on()**, el cual adjunta uno o más controladores de **eventos** para el **elemento** que se haya seleccionado. Dentro de este **método on()**, nos ayudamos del **método preventDefault()**, el cual **cancela un evento** indicando que la acción por defecto perteneciente a ese **evento** no va a ocurrir. Esto se ve de la siguiente forma: 

```jsx 

$('form').on('submit', function(e) { 

    e.preventDefault(); 

  }); 

``` 

¡Listo, ahora al dar **Enter** no se refrescará nuestra página! 

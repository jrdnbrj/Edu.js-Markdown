Como programadores, sabemos que eficientes con nuestro código brinda muchas ventajas. Al tener un código mejor organizado, más legible y más corto, permitimos que tanto las demás personas como nosotros tengamos un mejor entendimiento de lo que estamos digitando.  

La reutilización de código brinda cierta eficiencia a la hora de codificar. Una de las maneras de reutilizar código es **llamando a un método** sin tener que escribir todas esas líneas de código que están dentro de ese método nuevamente.  

Para ejemplificar esto dentro de nuestro proyecto, vamos a **llamar** a nuestro **método click** a través de un **evento keyup**. Este **evento keyup** se envía a un **elemento HTML** cuando el usuario suelta una **tecla**. En este caso, solo cuando se presente el **evento** de que el usuario tecleé la **tecla Enter**, este **evento** llamará a nuestro **método click** y haga todo lo que se digito en ese **método**: 

```jsx 
$('input[name=itemCompras]').keyup(function(event) { 
    if (event.keyCode == 13) { 
      $('#button').click(); 
    } 
  }); 
``` 

Si nos fijamos en el código anterior, este **evento** se realiza sobre nuestro **elemento** `input[name=itemCompras]`. Además, tenemos un **condicional** que nos indica que solo si el **keyup** sea el código de la **tecla 13** (el código de la **tecla Enter**), se **llame** al **método click**. Podemos encontrar una tabla con los códigos de las **teclas** [aquí](http://www.foreui.com/articles/Key_Code_Table.htm). 

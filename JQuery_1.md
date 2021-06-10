**jQuery** es una librería de código de JavaScript que nos permite escribir de manera más rápida, fácil y efectiva **JavaScript**. **jQuery** simplifica el código de JavaScript, animaciones, AJAX y la manipulación del DOM.  

La **sintaxis** de una sentencia en **jQuery** es simple y sencilla de comprender. La sintaxis común se compone de la siguiente forma:  

`$(‘selector’).method(‘parameter’);`

Como podemos ver, existen 4 partes importantes en esta línea de código, el signo de dólar "**$**" sirve para acceder a **jQuery**, el **selector** sirve para seleccionar un elemento de nuestro **HTML** y debe estar entre comillas simples o dobles, el **method** llama a un método para que actúe sobre el elemento seleccionado, y finalmente, el **parameter** es un parámetro opcional del método, este parámetro puede ser variables de cualquier tipo, tales como: **objetos**, **arrays**, **integers**, e inclusive otros **métodos**. 

De igual manera, hay muchas formas de usar un selector, aquí tenemos 3 ejemplos de formas comúnmente utilizadas: 

`$(‘.power’) // selecciona todos los elementos con la clase “power”.`

`$(‘#about’) // selecciona un solo elemento con el id “about”.` 

`$(‘div’) // selecciona todos los elementos “div”.` 

Estos son solo 3 ejemplos de la gran variedad de formas de usar un **selector**, para más información acerca de los **selectors**, puedes hacer clic [aquí](https://api.jquery.com/category/selectors/). 

Bien, ahora para iniciar nuestro proyecto de crear una lista de compras donde se puedan ingresar ítems, vamos a ingresar a nuestro **index.html** y dentro de nuestro `<div class="container">`, y debajo de nuestro título, vamos a crear un elemento **HTML** llamado **form**, el cual nos sirve para crear un formulario que obtenga las entradas del usuario. El elemento **form** recibirá un atributo **name** el cual especifica el nombre del formulario. 

De igual manera, vamos a crear un **div** con un **id button** el cual servirá para funcionar como un botón para ingresar nuestros ítems a nuestra lista de compras, y recibirá cualquier nombre, este código se vería de la siguiente forma: 
```jsx
<div class="container"> 
      <h2>Bienvenido al curso de jQuery</h2> 
      <form name="listaCompras"></form> 
      <div id="button">Añadir ítem</div> 
</div> 
```
Finalmente, dentro de nuestro **index.js**, vamos a declarar nuestra primera sentencia **jQuery**: 
```jsx
$('#button').click(function() { 
}); 
```

Como podemos observar en el código anterior, actuamos sobre nuestro elemento con el **id** de **button** y llamamos a nuestro **método click** que, a su vez, recibe como parámetro otro **método function**. Más adelante veremos que va a realizar este **método function** al hacer clic sobre nuestro elemento **HTML**. 

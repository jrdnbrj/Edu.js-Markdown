Los **selectors** son esenciales al momento de programar con **jQuery**. El **selector** nos permite seleccionar **elementos** de nuestro **HTML**, sin embargo, en ciertos momentos, queremos trabajar con cualquier **elemento hijo** que se encuentran dentro de un **elemento padre**. Este **elemento hijo** inclusive puede irse generando mientras usamos la aplicación. Para seleccionar estos **elementos hijo**, vamos a usar lo que se conoce en **jQuery** como **childSelector**. 

En el caso de nuestro proyecto, vamos a poder borrar cualquiera de nuestros ítems de lista haciendo un doble clic sobre ellos. En este caso, los **list items** que tienen la etiqueta **li**, son un **elemento** que están dentro del **document** el cual viene a ser el **elemento padre**. El **document** es nuestro **selector**, y **li** es nuestro childSelector. Para que el childSelector responda a nuestro evento de doble clic, tanto el **evento** como el **childSelector** tienen que pasarse como parámetros. Y como aprendimos en el anterior módulo, usaremos el **método on()**, debido a que permite adjuntar uno o más controladores de **eventos**. Finalmente, la sentencia quedaría de esta manera: 

```jsx 

$(document).on('dblclick', 'li', function() { 

}); 

``` 

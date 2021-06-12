Ahora que ya obtuvimos el valor de las entradas de usuario, necesitamos poder mostrar esas entradas en alguna parte de nuestra página. En nuestro **index.html**, debajo de nuestro **div** con **id button**, vamos a crear un elemento de lista ordenada `<ol></ol>`, el cual será nuestro espacio para mostrar nuestras entradas. 

En cuanto a nuestro **index.js**, necesitamos **insertar elementos** dentro de esta lista ordenada cada vez que se realice el **evento click**. Nos ayudamos del **método append()** para hacer esta inserción, y a su vez, removemos la línea de código con el selector **h2** y lo reemplazamos por lo siguiente: 

`$('ol').append('<li>' + toAdd + '</li>');` 

Como podemos observar en el código, estamos **insertando** ítems de lista "**li**", dentro de nuestra **lista ordenada**. En este caso, pasamos como parámetro la variable **toAdd** debido a que es la variable que ya tiene el valor de la entrada de usuario.  

Finalmente, y para mejorar la experiencia de usuario, limpiamos el **input** y lo dejamos vacío cada vez que alguien realice el evento **click**: 

`$('input').val('');` 

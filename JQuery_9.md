Nuestra data se encuentra guardada en nuestro **almacenamiento local**, sin embargo, sigue sin mostrarse en nuestra página. Lo primero que debemos hacer antes de mostrar el contenido, es verificar a través de un **condicional if**, si efectivamente tenemos ítems guardados en nuestro **almacenamiento local**:

```jsx
if (localStorage.getItem('listaCompras')) {
}
```

Después, en nuestra **variable local**, obtenemos el **Array listaCompras** del **almacenamiento local**. Debido a que lo que tenemos dentro de nuestro **almacenamiento local** son **strings**, lo tenemos que convertir de vuelta al tipo de data **listaCompras**. Ahora, con la ayuda de un **forEach()**, por cada ítem dentro de nuestro **Array**, insertamos ese ítem dentro de nuestra lista ordenada con el **método append()** de la misma forma que lo hicimos en el módulo 3. El **forEach** tiene un predicado **compra**, el cual viene a ser el **nombre** de cada **elemento** en la **lista** dentro del **método**.

Debajo de la linea `window.listaCompras = [];`, coloca:

```jsx
if (localStorage.getItem('listaCompras')) {
    window.listaCompras = JSON.parse(localStorage.getItem('listaCompras'));
    window.listaCompras.forEach(compra => {
      $('ol').append('<li>' + compra + '</li>');
    });
}
```

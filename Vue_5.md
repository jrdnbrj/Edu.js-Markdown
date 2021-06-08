Las **clases** en Vue son muy buenas para dar **estilos** a un elemento. Debido a que las **clases** y los **estilos** son atributos de un elemento, se puede usar la directiva **v-bind** para enlazar ambos atributos.

En el caso de nuestro proyecto, queremos destacar el botón del título al cual se le da un clic a través de un **estilo**. Primeramente, la **clase** que usaremos será condicional, esto se debe a que tiene que existir la condición de que la **nota** dentro de nuestro bucle **for** sea la **notaActual**

```jsx
<button v-on:click="notaActual = nota" v-bind:class="{active: nota === notaActual}">
	{{nota.titulo}}
</button>
```


En referencia al código anterior, le pasamos un objeto a la directiva **v-bind**. El objeto  contiene una **key** y un valor, en este caso, la **key** es la **clase active** y el valor es la condición de que **nota** debe ser equivalente a **notaActual**.

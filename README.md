## React js

Es una librería muy popular de JS para construir interfaces de usuario reutilizables controladas por componentes, para páginas web o aplicaciones.
React combina HTML con la funcionalidad de JS para crear su propio lenguaje de marcado llamados JSX. Además, facilita la administración del flujo de datos a través de la aplicación.

## Crear un elemento JS simple

React es una librería de vistas de código abierto creada y mantenida por facebook. Es una gran herramienta para hacer la interfaz de usuario (ui) de aplicaciones web mordernas.
Además, React usa una extensión de sintaxis de JS llamadas JSX que te permite escribir HTML directamente dentro de JS. Esto tiene muchos beneficios. Te permite utilizar el poder pragmático completo de JS dentro de HTML, y ayuda a mantener tu código legible. Sin embargo, hay algunas diferencias clave que se abordarán a lo largo de estos desafíos.
Por ejemplo, dado que JSX es una extensión sintáctica de JS, se puede escribir JS directamente dentro de JSX. Para hacer esto simplemente incluye el código que deseas que sea tratado como JS entre llaves: `{ 'This is treated as JavaScript code' }`. Ten esto en cuenta, ya que se utiliza en varios desafíos futuros.
Sin embargo, debido a que JSX no es JS válido, el código de JSX debe ser compilado en JS. El transpilador *Babel* es una herramienta muy popular para este proceso.
`ReactDOM.render(JSX, document.getElementById('root))` Esta llamada de función es la que coloca tu JSX en la representación ligerea del DOM de react. React entonces utiliza capturas instantáneas de su propio DOM para optimizat actualizandolo sólo partes específicas del DOM.

## Crea un elemento JSX complejo

El último desafío fue un ejemplo sencillo de  JSX, pero JSX también puede representar HTML más complejo.
Una cosa importante que se debe saber sobre JSX anidado es que debe devolver un solo elemento.
Este elemento principal contendría a todos los demás niveles de elementos anidados.
Por ejemplos, varios elementos JSX escritos al mismo nivel sin elemento contenedor principal no se transpilarán.
Ejemplo:

JSX válido: 

```
<div>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
  <p>Paragraph Three</p>
</div>
```
JSX inválido:

```
<p>Paragraph One</p>
<p>Paragraph Two</p>
<p>Paragraph Three</p>
```
**Nota:** Al renderizar varios elementos de esta forma, puedes envolverlos todos entre paréntesis, pero no es estrictamente necesario. Observa también que este desafío usa una etiqueta `div` para envolver a todos los elementos hijos dentro de un solo elemento principal. Si eliminas el `div`, JSX ya no se podrá transpilar. Ten esto en cuenta, ya que también será así cuando devuelvas elementos JSX en los componentes de React.

## Agrega comentarios en JSX

JSX es una sintáxis que se compila en JS válido. A veces, para facilitar la lectura, es necesario añadir comentarios al código. Como la mayoría de los lenguajes de programación, JSX tiene su propia manera de hacerlo.
Para agregar comentarios dentro de JSX, se utiliza la sintaxis `{/**/}` para envolver el texto del comentario.
El editor de código tiene un elemento JSX similar al que creaste en el último desafio. Agrega un comentari en algún lugar dentro del elemento `div`, sin modificar los elementos `h1` o `p`.

## Renderiza elementos HTML al DOM

Hasta ahora, has aprendido que JSX es una herramienta conveniente para escribir HTML legible dentro de  JS. Con React, podemos rederizar este JSX directamente al DOM HTML usando la API de renderizado de React conocida como ReactDOM.
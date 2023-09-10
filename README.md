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

Hasta ahora, has aprendido que JSX es una herramienta conveniente para escribir HTML legible dentro de JS. Con React, podemos rederizar este JSX directamente al DOM HTML usando la API de renderizado de React conocida como ReactDOM.
ReactDOM ofrece un método simple para renderizar elementos  React al DOM que se ve así: `ReactDOM.render(componentToRender, targetNode)`, done el primer argumento es el elemento o componente React que deseas renderizar, y el segundo argumento es el nodo DOM al que se quiere renderizar el componente.
Como era de esperarse, `ReactDOM.render()`debe llamarse después de las declaraciones de los elementos JSX, al igual que hay que declarar las variables antes de usarlas.

Para rendererizar un elemento al DOM, usamos la siguiente sintáxis:

```
ReactDOM.render(<item to be rendered>, <where to be rendered>);
```
```
ReactDOM.render(JSX, document.getElementById("challenge-node")); 
```
## Definir una clase HTML en JSX

Una diferencia clave en JSX es que ya no puedes usar la palabra `class`para definir clases HTML. Esto es debido a que `class` e suna palabra reservada en javascript. En su lugar, JSX utiliza `className`.
De hecho, la convensión de nomenclatura para todos los atributos HTML y referencias a eventos en JSX se convierte a camelCase. Por ejemplo, un evento de click en JSX en `onClick`, en lugar de `onclick`.
Del mismo modo, `onchange` se convierte en `onChange`. Si bien se trata de una diferencia sutil, es importante tenerlo en cuenta de ahora en adelante. 

## Etiquetas JSX auto-cerradas

Hasta ahora, has visto cómo JSX difiere de HTML de una manera clave con el uso de `className` vs. `class` para definir clases en HTML.
Otra forma importante en la que JSX difiere de HTML está en la idea de la etiqueta de auto-cierre.
En HTML, casi todas las etiquetas tienen una etiqueta de apertura y cierre: `<div></div>`;la etiqueta de cierre siempre tiene una barra inclinada antes del nombre de la etiqueta que está cerrando. Sin embargo, hay instancias especiales en HTML llamadas "etiquetas auto-cerradas", o etiquetas que no requieren una etiqueta de apertura y cierre antes de que otra etiqueta pueda comenzar.
Por ejemplo, la etiqueta de salto de línea puede escribirse como `<br />`, pero nunca debe escribirse como `<br></br>`, ya que no contiene ningún contenido.
En JSX, las reglas son un poco diferentes. Cualquier elementos JSX se puede escribir con una etiqueta de auto-cierre, y cada elemento debe ser cerrado. La etiqueta de salto de línea, por ejemplo, siempre debe escribirse como `<br />` para ser un JSX válido que puede ser transpilado. Por otra parte, un `<div>` puede escribirse como `<div />` o `<div></div>`. La diferencia es que en la primera versión de sintaxis no hay forma de incluir nada en la `<div />`. Verás en desafíos posteriores que esta sintaxis es útil al rederizar componentes de React.

## Crea un componente funcional sin estado

Los componentes son el núcleo de React. Todo en React es un componente y aquí aprenderás a crear uno.
Hay dos maneras de crear un componente React. La primera forma es utilizar una función JavaScript. Definir un componente de esta manera crea un *componente funcional sin estado*. El concepto de estado en una solicitud se abordará en retos posteriores. Por ahora, piensa en un componente sin estado como que puede recibir datos y renderizarlos, pero no administra o rastrea los cambios en esos datos. (Cubriremos la segunda manera de crear un componente React en el siguiente desafío.)

Para crear un componente con una función, simplemente escribe una función JS que devuelva ya sea JSX o `null`. Una cosa importante a tener en cuenta es que en React requiere que tu nombre de función comience con una letra mayúscula. Aquí hay un ejemplo de un componente funcional sin estado que asigna una clase HTML en JSX:

```
const DemoComponent = function() {
  return (
    <div className ='customClass' />
  );
};
```
Después de ser transpilado, el `<div>` tendrá una clase CSS de `customCLass`.
Debido a que un componente JSX representa HTML, podrías poner varios componentes juntos para crear una página HTML más compleja. Esta es una de las ventajas clave de la arquitectura de componentes que React proporciona. Te permite componener tu interfaz de usuario de muchos componentes separados y aislados. Esto hace más fácil contruir y mantener complejas interfaces de usuario.

## Crea un componente de React

La otra forma de definir un componente React es con la sintaxis de clase de ES6 `class`. En el siguiente ejemplo, `Kitten` hereda de `React. Component:`

```
class Kitten extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    returnv(
      <h1>Hi</h1>
    );
  }
}
```
Esto crea una clase de ES6 `Kitten` que hereda de la clase `React.Componente`. Así que la clase `Kitten` ahora tiene acceso a muchas características útiles de React, como el estado local y el ciclo de vida de los "Hooks". No te preocupes si aún no estás familiarizado con estos términos, ya que se tratarán con más detalle en los desafíos posteriores. También ten en cuenta que la clase `Kitten` tine un `constructor` definido dentro de ella que llama a `super()`. Utiliza `super()` para llamar al constructor de la clase padre, en este caso `React.Component`. El constructor es un método especial utilizado durante la inicialización de objetos que se crean con la palabra clave `class`. Es una mejor práctica llamar al `constructor` de un componente con `super`, y pasar sus propiedades `props` a ambos. Esto asegura que el componente esté inicializado correctamente. Por ahora, sepan que es estándar que se incluya este código. Pronto verás otros usos para el constructor, así como las `props`.

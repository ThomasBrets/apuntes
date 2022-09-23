# React 0
---
# Introducción
___
## Objetivos

En ese WS aprenderas a implementar **React** y su sintaxis.

### React

Es una **libreria de JavaScript que sirve para construir interfaces de usuarios** de forma declarativa, eficiente y flexible.

Utiliza estructuras pequeñas y aisladas llamadas **componentes**. Esta libreria es multiplataforma y te servira para crear aplicaciones Web, mobile y de escritorio.

## Definiciones

### Componentes

Un componente es un bloque de código UI que puede ser una entidad en si misma. **Es el ladrillo que forma la pagina.**

Por ejemplo, en un sitio Web tradicional, tendriamos un componente para la **sidebar**, otro para la **navbar** y **footer.**

#### Ejemplo

![alt text](https://i.imgur.com/7sY1ic1.png)

Si usaramos HTML, tendriamos que crear cada bloque. En cambio, React nos permite **reutilizar cada componente.**

**importante:** Al nombrar un componente, es una convencion usar **Mayùscula**. De lo contrario ¡No funciona!

### JSX

Te permite armar bloques de código visuales usando tus conocimientos de HTML. Sin embargo, **no es HTML: Es una extension de la sintaxis de JavaScript.**

Si bien no es obligatorio usar jsx en React, es util para escribir grandes bloques de código.

#### Ejemplo

```JavaScript
<Componente>
    <h1 className="Welcome">Hello World</h1>
</Componente>
```

#### Veamos algunos de sus beneficios

- Mejora la legibilidad de tu código.
- Reduce la cantidad de errores de sintaxis.
- Facilita la lectura del código (Si estas acostumbrado a leer HTML).

### Babel

Es una "compilador" o **traductor _open source_ que convierte el código JSX a JavaScript**. De esta forma el browser lo podra interpretar.

**Recordá:** El navegadir solo interpreta HTML, CSS y JavaScript.

#### Ejemplo

![alt text](https://i.imgur.com/YRDBpQl.png)

El código a la derecha (JSX) nos permitirá escribir componentes.

Luego este codigo se transpila con Babel.

### Webpack

Es una de las **herramientas de configuración** (buld tool) que te permite declarar cómo debe interpretarse cada componente de tu proyecto: tu código JavaScript, HTML y CSS, etc. Internamente Webpack crea un **grafo de dependencias** que mapea todos los modulos.

#### ¿Que es un Grafo?

Es una estructura matemática formada por **nodos o vértices** que permite mostrar las relaciones que hay en los distintos componentes.

Webpack decidirá que compilador procesará los archivos de entrada para convertirlos en otros archivos de salida.

Por ejemplo, si el _browser_ no puede leer archivos de `.sass`, se convertirán en `.css`.

## Create React App

Es un ambiente cómodo para **aprender React**, y es la mejor manera de comenzar a contruir **una nueva aplicación de página única** usando React.

**Create React App** configura un ambiente de desarrollo de forma que puedas usar las ultimas caracterísiticas de JavaScript, brindando una nueva experiencia de desarrollo, y optimizando tu aplicacion de producción.

#### Para crear tu proyecto ejecutá:

```JavaScript
npx create-react-app my-app
cd my-app
npm start
```

**Nota:** En la primera línea `npx` no es un error de escritura. Es una herramienta de ejecución de paquetes que viene con `npm 5.2+`.

**Create React App** no se encarga de la lógica de **backend** o de bases de datos; tan solo crea un flujo de construcción para **fontend**, de manera que lo puedes usar con **cualquier backend**. Para ello internamente usa **Babel** y **Webpack**.


# React app
---

## Primer Componente

En esta sección, deberás generar un componente principal llamado `App.jsx` dentro de la carpeta `src`.

**Nota:** En muchos proyectos, encontrarás que el archivo principal se llama `Main`. Sin embargo, en la actualidad, los proyectos modernos de **React** suelen tener un archivo `App` como componente principal.

Para avanzar seguí estos pasos:

1. Importá **React** usando la sintaxis `import from`.
2. Creá una función llamada `App` que retorne un bloque de **JSX.**
3. Exportá esta función para hacerla accesible.

```JavaScript
import React from 'react';

const App = () => {
    return <h1>Hello World!</h1>;
};

export default App;
```

Aunque tu componente sea básico, es funcional. Ahora, deberás incorporarlo en el DOM usando **ReactDOM.**

**Importante:**
Dependiendo de la plataforma, necesitaremos características específicas de React. Por ejemplo, si vamos con un **browser** e interactuar con el DOM, tiene sentido usar **ReactDom.** En cambio, si desarrollamos en **mobile**, necesitaremos otra librería.

**ReactDOM:**
Dentro de React, la libreria ReactDOM nos permite crear aplicaciones **_Web._** El paquete provee métodos específicos del DOM.

En el archivo `index.js`, imortá tu nuevo componente y reemplazalo en la variable `app`.

#### ¿Que hago si mi pantalla queda en blanco?

Si tu **app** no carga, revisá la consola del **browser** que te indicará donde esta el **bug**. Probablemente sea un error de sintaxis. Puede que recibas el siguiente mensaje.

```JavaScript
Warning: Functions are not valid as a React child.
This may happen if you return a Component instead of <Component /> from render.
Or maybe you meant to call this function rather than return it.
```

#### Solución

Este error se produjo porque usamos una función como un componente regular aunque, en realidad, es una función que **retorna** un componente.

Para resolverlo, deberás instanciar la función usando los corchetes angulares `< />`. De este modo, React generará un nuevo **nodo** que será parte de nuestra UI.

Guarda tu componente instanciado en la variable `app`:

```JavaScript
const app = <App />
```

#### `index.js` deberia quedar así

```JavaScript
import React from "react";
import { render } from "react-dom";
import App from "./App"

const app = <App />

const traget = document.getElementById("root");

render(app, target);
```

## Maquetado

En esta sección deberás **maquetar** el menú para lograr la vista deseada. Para eso reemplaza el mendaje de `Hello World!` con el siguiente **JSX:**

```JavaScript
<div>
    <header>
     <h1>Coffee Shop ☕</h1>
      </header>
      <main>
       <h3>Drinks</h3>
        <ul>
          <li>
            <strong>Espresso</strong>
            <small>- Small & strong 1:2 ratio coffee</small>
            <em>$100</em>
          </li>

          <li>
            <strong>Ristretto</strong>
            <small>- Small & really strong 1:1 ratio coffee 🇮🇹</small>
            <em>$100</em>
          </li>

          <li>
            <strong>Lungo</strong>
            <small>- Popular large size espresso 1:3 1:6 ratio</small>
            <em>$120</em>
          </li>

          <li>
            <strong>Cappuccino</strong>
            <small>
              - Single espresso with steamed milk foam 1:1 coffee:milk ratio
            </small>
            <em>$150</em>
          </li>

          <li>
            <strong>Latte</strong>
            <small>
              - Weak coffee, sweat and milky is a 1:4 parts coffee:milk ratio
            </small>
            <em>$150</em>
          </li>
        </ul>
        <h3>Food</h3>
        <ul>
          <li>
            <strong>Avocado Toast</strong>
            <small>- A toast with mashed avocado, salt and black pepper</small>
            <em>$200</em>
          </li>

          <li>
            <strong>Scrambled Eggs</strong>
            <small>- 2 large whisked eggs with cream and a pinch of salt</small>
            <em>$100</em>
          </li>
          <li>
            <strong>French Toast</strong>
            <small>
              - A slice of bread toasted with milk, eggs and cinnamon, + a cover
              of syrup
            </small>
            <em>$120</em>
          </li>
        </ul>
      </main>
</div>
```

Con esto tendremos algo muy similar al producto final, pero estará **hard codeado**. Es decir, todos los datos fueron ingresados a mano. Mas adelante, muchos de ellos se generarán de manera dinámica.

## Componente `Header`

Recapitulando, ya generaste el componente `App` del menú. Este incluía el encabezado (`header`), el cuerpo del menú (`main`) y el listado de la propuesta gastronómica.

En esta sección, deberás llevar el `header` del componente `App` a un nuevo componente, también, llamado `Header`. De esta manera, el encabezado estará separado del resto del menú.

**Recordá:** Una de las características de React es que todo lo que constituya una **bloque visual** puede ser separado en un componente. Así, se puede abstraer cada vista y la funcionalidad que posea.

Ahora, generá una carpeta llamada `components` y dentro de ella un archivo para el componente `Header.jsx`(por convención los componentes se ponen con **Mayúscula**) que retorne el **JSX** del `header` actual.

**Nota:** Si escribis **rafce** generará el componente automáticamente.

```JavaScript
const Header = () => {
    return(
        <header>
        <h1>Coffee Shop ☕</h1>
        </header>
    );
};
```

Luego, dentro del componente `App.jsx`, importa el componente `Header` y llámalo dentro del **JSX** para que genere un nuevo nodo en base a tu componente. La vista será igual que la anterior.

#### Nota
Con React podremos agregar navegación, manejo de ususarios, *dark/light mode* y más. Sobre todo podremos convertir componentes en múltiples subcomponentes. Cada uno tendrá una lógica completa. Esto es lo que hace que tu aplicación sea super poderosa.

# Render Dinámico
---

## List & JSX
Hasta ahora, solo estabas operando la información del HTML. En esta sección trabajarás con el contenido del archivo `menu.json`.

Ahora veamos, como listar elementos idénticos en React.

### Listas en React
JSX facilita la escritura de los componentes. Ofrece ayudas para situaciones comunes coo listar elementos iguales. 

```JavaScript
const list = ["item1", "item2", "item3"];
```

Ahora, volvé a tu proyecto y seguí estos pasos:
1. Declará la lista antes del `return` en App.
2. Agregalo al JSX usando la sintaxis de llaves. Por ejemplo:`{ list }`.
3. Hacé una prueba con estos elementos. Inspeccioná el HTML final desde el browser:

```JavaScript
const list = [<h1>Item 1</h1>, <p>Item 2</p>, <strong>Item 3</strong>];
```

React no solo agrega los ítems del Arreglo, sino que también interpreta JSX en distintos lugares del archivo JavaScript.

### Transformar la información
El archivo `menu.json` contiene un **Arreglo de comidas y de bebidas.** Ahora, deberás transformar esa información en elementos JSX para, luego, pasarlo al DOM.

Es decir, queremos transformar el siguiente bloque de código:
```JavaScript
 {
      "name": "Espresso",
      "description": "Small & strong 1:2 ratio coffee",
      "price": 100
    }
```
En esto:
```JavaScript
<li>
    <strong>Espresso</strong>
    <small>- Small & strong 1:2 ratio coffee</small>
    <em>$100</em>
</li>
```
**Nota:** Podrás usar la Función `map` para transformar cada Objeto con información en un bloque JSX.

Ahora, seguí estos pasos:
1. Primero, dentro del componente `App` hay que desestructurar ya que sabemos que **drink y food son arreglos dentro del objeto menú.**
```JavaScript
  const { drinks, food } = menu;
```
2. Luego, dentro de la carpeta `components`, crea un archivo con el componente **drink** y otro con el componente **food**.

3. En cada uno, usá el método `map` para transformar la información del Arreglo en elementos JSX.

4. Usá la sintaxis de llaves `({})` para completar los textos con su equivalente del `.json`.

**importante:** Asegurate de que la Función enviada como parámetro del `map` retorne el JSX.

5. Guarda el arreglo final en una variable.

6. Reemplazá la lista generada por el `<ul>` por la lista creada con la data del `.json`.

#### solución 
```JavaScript
const drinks = drinks.map((drink) => (
    <li>
      <strong>{drink.name}</strong>
      <small>{drink.description}</small>
      <em>{drink.price}</em>
    </li>
  ));
```
**También podemos desestructurar:**

```JavaScript
const drinks = drinks.map(({name, description, price}) => (
    <li>
      <strong>{name}</strong>
      <small>{description}</small>
      <em>{price}</em>
    </li>
  ));
```

Si todo funciona correctamente, deberías ver una nueva bebida `Flat white`. Esta figuraba antes en el archivo `menu.json`, pero no en el maquetado.

## Props
---
Antes de avanzar, analizá el HTML para descubrir patrones. En caso de encontrarlos, generá nuevos componentes con esos elementos.

Los componentes pueden generarse a partir de elementos que tengan la misma estructura y, por lo tanto, sean reutilizables.

En este caso, tanto las **bebidas** como las **comidas** comparten la misma estructura dada por los `<li>`.

En esta sección, en la carpeta `components`, deberás **generar un componente nuevo llamado `Item` que retorne el JSX correspondiente.**

**Recorá:** Este proceso es similar al que hiciste con el componente `Header`.


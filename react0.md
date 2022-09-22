# React 0

---

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



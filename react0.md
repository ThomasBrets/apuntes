# React 0

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
``` JavaScript
<Componente>
    <h1 className="Welcome">Hello World</h1>
</Componente>    
```

#### Veamos algunos de sus beneficios
- Mejora la legibilidad de tu código.
- Reduce la cantidad de errores de sintaxis.
- Facilita la lectura del código (Si estas acostumbrado a leer HTML).

### Babel

Es una "compilador" o **traductor *open source* que convierte el código JSX a JavaScript**. De esta forma el browser lo podra interpretar.

**Recordá:** El navegadir solo interpreta HTML, CSS y JavaScript.

#### Ejemplo
![alt text](https://i.imgur.com/YRDBpQl.png)

El código a la derecha (JSX) nos permitirá escribir componentes.

Luego este codigo se transpila con Babel.

### Webpack
Es una de las **herramientas de configuración** (buld tool)  que te permite declarar cómo debe interpretarse cada componente de tu proyecto: tu código JavaScript, HTML y CSS, etc. Internamente Webpack crea un **grafo de dependencias** que mapea todos los modulos.

#### ¿Que es un Grafo?
Es una estructura matemática formada por **nodos o vértices** que permite mostrar las relaciones que hay en los distintos componentes.

Webpack decidirá que compilador procesará los archivos de entrada para convertirlos en otros archivos de salida.

Por ejemplo, si el *browser* no puede leer archivos de `.sass`, se convertirán en `.css`.  






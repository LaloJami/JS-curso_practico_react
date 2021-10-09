<div align="center">
  <h1>Curso Practico de React</h1>
</div>

# Conceptos fundamentales de React
## JSX
Es la extensión de archivos que se usa en react donde podemos hacer html dentro de js facilitando el uso sacando lo mejor de html css y js.

## Virual DOM
Es una copia del DOM real y lo que hace es compararlo, asi cuando existe algun cambio no se tiene que renderizar toda la pantalla si no solo lo que se cambio mejorando el desempeño de nuestra app, como lo comente antes esto es por que se compara el Virtual DOM con el DOM Real encontrando los cambios

## Ciclo de vida
Este concepto es ampliamente conocido en la programación, en este curso vamos a conocer cual es el ciclo de vida de los elementos que vamos a crear en react desde que nace, se combina hasta que muere

## Estado
Esto es fundamental, ya que podemos ver los estados y ver como es el flujo de la información entre componentes a travez de un imputs, botones, interacciones entre otros elementos

# Instalación de React y React DOM
Iniciar proyecto
```
git init
npm init -y
npm install react react-dom
```
# Configuración de webpack y babel
Babel:
```
npm install -D @babel/core @babel/preset-env @babel/preset-react 
```
Webpack:
```
npm install -D webpack webpack-cli webpack-dev-server 
```
HTML plugin:
```
npm install -D babel-loader html-loader html-webpack-plugin
```
# React con CSS y Sass

```
npm i mini-css-extract-plugin css-loader style-loader sass sass-loader -D
```
# React DOM
```
npm install react-router-dom
```
# ¿Qué es Atomic Design?

## Atomos
Representación de pequeños elementos o unidades claves dentro de nuestra aplicación, por ejemplo:
- Botones
- Elemendo de un texto
- comportamiento de una imagen
## Moleculas
Nos permiten unir más de un componente y crear un bloque especifico, por ejemplo un nav con su lista, o un logo donde esta una imagen y un texto.

## Organismos
Un header puede tener un componente logo, nav, entre otros, en este caso el header es el organismo

## Template
Es la combinacion de organismos aqui encontramos una combinacion que hacen a una pagina como el header, footer, sidebar.

## Pages
Creacion de paginas

Para la estructura de nuestro proyecto aplicamos de la siguiente forma

- **Components**: pieza más pequeño (átomo).
- **Containers**: Muestran la unión de uno o más componentes.
- **Pages**: Son las secciones / rutas que vamos a tener.

# Tipos de componentes en React: stateful vs. stateless
Este es un ejemplo para useState, podemos darle un valor inicial, el cual puede ser cambiado por un evento que se puede asignar a este mismo componente, o a otros componentes y hasta pasarlo por medio de un hijo para que éste cambie el inicial.

Para poder usar componentes stateful es necesario llamar useState desde React, la forma de importarlo y usarlo es la siguiente:
```js
import React, { useState } from 'react';

const Button = () => {
  const [name, setName] = useState('Hola Mundo'); 
  return (
    <div>
      <h1>{name}</h1>
    </div>
  );
}
```
Los componentes stateless servirán para pasar un estilo visual o props, pero no tendrá otra función más que esa.

Este sería un componente sin estado, stateless.
```js
import React from 'react';

const Button = ({ text }) => <ButtonRed text={text}/>;
```
También esta forma es válida:
```js
import React from 'react';

const Button = () => (
  <div>
    <h1>Hola mundo!</h1>
  </div>
);
```
Es por eso que hay que tener presente que NO todos los componentes deben de tener estado y muchos de ellos sólo llevarán información que presentar directamente al HTML con CSS, pero sí serán parte de todo lo que se está construyendo.

Los componentes Stateful y Stateless, son los componentes más utilizados hoy en día.

También hay otro tipos de componentes, que están compuestos por clases.

Aquí, tendremos una clase, con el nombre que queramos, que extiende de React.Component
```js
import React from 'react';

class App extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello world! </h1>
      </div>
    )
  }
}
```
Aunque, si importamos React Component, desde un inicio, podemos simplemente escribirlo de esta forma:
```js
import React , { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Hello world! </h1>
      </div>
    )
  }
}
```
Este tipo de componentes trabajan con constructores, aunque ya no son tan usados, pues han sido reemplazados por la propuesta de React Hooks.
```js
import React , { Component } from 'react';

class App extends Component {

  constructor() {
    super();
    this.sate = {
      count: 0
    };
  }

  render() {
    return (
      <div>
        <h1>Hello world! </h1>
      </div>
    )
  }
}
```
Es importante conocer este tipo de componentes porque si en algún momento tenemos que dar mantenimiento a alguna página que fue construida hace unos años atrás, es muy posible que nos encontremos este tipo de componentes.

Los hooks, tienen una funcionalidad particular, pues reciben un componente, extienden su funcionalidad con lo que esté dentro del componente y retornan un componente compuesto. Así podemos tener funcionalidades muy específicas con las que podemos trabajar según nuestras necesidades.

Esta sería la sintaxis:
```js
import React , { Component } from 'react';

function ComponentWrapper(WrapperComponent) {
  class Wrapper extends Component {
    render () {
      return <WrapperComponent {...this.props} />;
    }
  }

  return Wrapper;
}
```
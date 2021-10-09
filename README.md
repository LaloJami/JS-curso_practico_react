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
# Js

Introducción de JavaScript y su historia
## ¿Que es Js?

**JavaScript** es un lenguaje de programación inicialmente diseñado para interactuar con elementos de paginas web en los navegadores web, **JavaScript** consta de tres partes principales:

- **ECMAScript** que proporciona la funcionalidad principal.
- El *modelo de objeto de documento* **(DOM)** proporciona interfaces para interactuar con elementos en paginas web.
- El *médelo de objetos del navegador* **(BOM)** proporciona la API del navegador para interactuar con el navegador web.

**JavaScript** le permite agregar interactividad a una pagina web. Por lo general, utiliza **JavaScript** con **HTML** y **CSS** para mejorar la funcionalidad de una pagina web, como *validar formularios*, crear mapas interactivos y mostrar gráficos animados.

Cuando se carga una pagina web, es decir, después de que se haya descargado el **HTML** y **CSS**, el motor de **JavaScript** del navegador web ejecuta el código **JavaScript**. Luego, el código **JavaScript** modifica el **HTML** y el **CSS** para actualizar la interfaz de usuario de forma dinámica.

El motor de **JavaScript** es un programa que ejecuta al **JavaScript** al principio, los motores de **JavaScript** se implementaron como interpretes.

Sin embargo, los motores de **JavaScript** modernos generalmente se implementan como compiladores justo a tiempo que compilan código de **JavaScript** en código de **bytes** para mejorar el rendimiento.
_____________________________________________________
## JavaScript del lado del cliente vs del lado del servidor

Cuando se utiliza **JavaScript** en una pagina web, se ejecuta en los navegadores web. En este caso, **JavaScript** funciona como un lenguaje de lado del cliente.

**JavaScript** puede ejecutarse tanto en navegadores web como en servidores. Un entrono popular del lado del servidor de **JavaScript** es **Node.js**. A diferencia del **JavaScript** del lado del cliente, el **JavaScript** del lado del servidor se ejecuta en el servidor que le permite acceder a bases de datos, sistemas de archivos, etc. 

_____________________________________________________
## Historia de JavaScript

En 1995, **JavaScript** fue creado por un desarrollador de Netscape llamado **Brendan Eich**. Primero se llamo Mocha y luego cambio por LiveScript.

Netscape decidió cambiar LiveScript a **JavaScript** para aprovechar la fama de **Java**, que era popular. La decisión se tomo justo antes de que Netscape lanzara su navegador web Netscape Navigator 2. Como resultado, **JavaScript** ingreso a la versión 1.0.

Netscape lanzo **JavaScript 1.1** en Netscape Navigator 3. Mientras tanto, Microsoft introdujo un navegador web llamado Internet Explores 3 (IE 3), que competía con Netscape. Sin embargo, IE vino con su propia implementación de JavaScript llamada **JScript**. Microsoft uso el nombre de **JScript** para evitar posibles problemas de licencias con Netscape.

Por lo tanto, dos versiones diferentes de **JavaScript** estaban en el mercado:
- *JavaScript* en el navegador de Netscape
- *JScript* en Internet Explorer

**JavaScript** no tenia estándares que rigieran su sintaxis y características. Y la comunidad decidió que era hora de estandarizar el idioma.

En 1997, **JavaScript 1.1** se presento a la *Asociación Europea de Fabricantes de Ordenadores* **(ECMA)** como propuesta. Se asigno al Comité Técnico n°39 **(TC39)** para estandarizar el lenguaje a fin de convertirlo en un lenguaje de secuencias de comandos de propocito general, multiplataforma y neutral para el proveedor.

**TC39** idea **ECMA-262**, un estándar para definir un nuevo lenguaje de secuencia de comandos llamado **ECMAScript**.

Después de eso, la Organización Internacional de Normalización y las Comisiones Electrotécnicas Internacionales **(ISO/IEC)** adoptando **ECMAScript (ISO/IEC-16262)**.

_____________________________________________________
## Descripción general de JavaScript

Para definir una variable de **JavaScript**, usa la palabra `var` por ejemplo:

```js
var x = 10;
var y = 20;
```

**ES6** agrego una nueva forma de declarar variables con `let`:

```js
let x = 10;
let y = 20;
```

Hay diferencias entre `var` y `let`. Es una buena practica usar `let` para declarar variables.

Para declarar una *función*, utilizar la palabra `function`. El siguiente ejemplo define una función que calcula la suma de dos argumentos.

```js
function add(a, b){
	return a + b;
}
```

Para llamar a la función `add()` se utiliza la siguiente sintaxis:

```js
let result = add(x,y);
```

Para registrar el resultado en la ventana de la consola del navegador, utilizamos el `console.log()` :

```js
console.log(result);
```

Ahora debería ver `30` en la ventana de la consola.

**JavaScript** le proporciona de declaraciones de condición como `if-else` y  `switch`. Por ejemplo:

```js
let a = 20,
	b = 30;
	
function divide(a, b){
	if(b==0){
		throw 'Division entre cero'
	}
	return a/b;
} 
```

En la función `divide()`, verificamos si el numerador *b* es cero. Si es así, lanza una *excepción*. De lo contrario, devolvemos el resultado de *a/b*.

Para declara una matriz, utilizamos lo siguiente sintaxis:

```js
let items = [];
```

Para declarar una matriz con algunos elementos iniciales, especifique los elementos entre corchetes:

```js
let items = [1,2,3];
```

Pude acceder a la *cantidad* del elemento *ítems* a través de la propiedad `length` :

```js
console.log(items.length); // 3
```

Para iterar sobre los elementos de la matriz `items`, usando el `for` que es una declaración de bucle de la siguiente manera:

```js
for(let i = 0; i < items.length; i++){
	console.log(items[i]);
}
```

O use el `for...of` en **ES6**:

```js
for(let item of items){
	console.log(item);
}
```

**JavaScript** es un lenguaje en evolución.
_____________________________________________________
## Hello World
### Incrustar código Js en un HTML

No se recomienda colocar el código **JavaScript** dentro del elemento `<script>`directamente y debe usurarse solo en fines de prueba.

El código **JavaScript** del elemento `<script>` se interpreta de arriba a bajo. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript Hello World Example</title>
    <script>
        alert('Hello, World!');
    </script>
</head>
<body>
</body>
</html>
```

En el elemento `<script>`, usamos la función `alert()` para mostrar el mensaje  `Hello World!`. 

## Incluir un archivo Js externo

Para incluir un **JavaScript** desde un archivo externo:
- Primero, cree un archivo cuya extensión sea `.js`, `app.js` y colóquelo en la subcarpeta `js`.
- Luego, use la URL del archivo de código fuente de **JavaScript** en el atributo `src` del elemento `<script>`.

A continuacion se muestra el contenido del archivo *app.js* :

```js
alert("Hello World!");
```

Y lo siguiente muestra el archivo `helloworld.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript Hello World Example</title>
    <script src="js/app.js"></script>
</head>
<body>

</body>
</html>
```

Si inicia el archivo `helloword.html` en el navegador web, vera la alerta que muestra el mensaje *Hello world!*.

Tenga en cuenta que puede cargar un archivo Js desde un servidor remoto. Esto le permite servir Js desde varios dominós, por ejemplo, red de entrega de contenido **(CDN)** para acelerar la pagina.

**Que es una CDN?**
Una *CDN* (Content Delivery Network o Red de Distribución de Contenido), es un sistema de servidores distribuidos estratégicamente en diferentes ubicaciones geográficas para entregar contenido web de manera más eficiente a los usuarios finales. 

Cunado tiene varios archivos **JavaScript** en una pagina, el motor interpreta los archivos en el orden en que aparecen.

```html
<script src="js/service.js"></script>
<script src="js/app.js"></script>
```

En este ejemplo, el motor de **JavaScript** interpreta los archivos `service.js` y `app.js` en secuencia. Interpreta primero el archivo `service.js` antes de `app.js`.

Para paginas que incluye muchos archivos **JavaScript** externos, la pagina en blanco se muestra durante la fase de representación de la pagina.

Para evitar esto, incluya el archivo js justo antes de la etiqueta `</body>` como se muestra:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript Hello World Example</title>
</head>
<body>
 
   <!-- end of page content here-->
   <script src="js/service.js"></script>
   <script src="js/app.js"></script>
</body>
</html>
```
## Los atributos async y defer

Para cambiar la forma en que el navegador carga y ejecuta archivos **JavaScript**, utiliza uno de los dos atributos del elemento `<script>` `async` y `defer`.

Estos atributos solo surten efecto en los archivos de script externos. El atributo `async` indica al navegador web que ejecute el archivo **JavaScript** de forma **asíncrona**. El atributo `async` no garantiza que los archivos de script se ejecuten en el orden en que aparecen. Por ejemplo:

```html
<script async src="service.js"></script>
<script async src="app.js"></script>
```

El archivo `app.js` podría ejecutarse antes que el archivo `service.js`. Por lo tanto, debe asegurarse de que no exista *dependencia* ente ellos.

El atributo `defer` solicita al navegador web que ejecute el archivo de secuencia de comandos después de que se haya analizado el documento HTML.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript defer demonstration</title>
    <script defer src="defer-script.js"></script>
</head>
<body>
</body>
</html>
```

Aunque coloquemos el elemento `<script>` en la sección `<head>` el script esperar a que el navegador reciba la etiqueta de cierre `<html>` para comenzar a ejecutarse.

**Resumen**
- Utilice el elemento `<script>` para incluir un archivo JS en una pagina HTML.
- El atributo `async` del elemento `<script>` le indica al navegador web que obtenga el archivo Js en paralelo y luego lo analice y ejecute tan pronto como el archivo js este disponible. 
- El atributo `defer` del elemento `<script>` permite que el navegador web ejecute el archivo JS despues de analizar el documento.


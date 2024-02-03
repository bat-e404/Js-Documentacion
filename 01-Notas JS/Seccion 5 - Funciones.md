# Funciones

## ¿Que son las funciones?

Cuando desarrolla una aplicación, a menudo necesita realizar la misma acciona en muchos lugares. Por ejemplo, es posible que dese mostrar un mensaje cada vez que se produzca un error.

## Declarar una función

Para declarar una función, usa la palabra `function`, seguida del nombre de la función, una lista de parámetros y el cuerpo de la función de la siguiente manera:

```
function functionName (parameters) {
	// function body
}
```

El nombre de la función debe ser un identificador de **JavaScript** valido. Por conveniencia, los nombres de las funciones están en **camelCase** y comienzan con verbos como `getData()`, `fetchContents()` y `isValid()`.

Una función puede aceptar cero, uno o varios parámetros. En el caso de varios parámetros, debe usar una coma para separar dos **parámetros**.

Lo siguiente declara una función `say()` que no acepta ningún parámetro:

```js
function say(){
}
```

Lo siguiente declara una función llamada `square()` que acepta un parámetro:

```js
function square(a) {}
```

Y lo siguiente declara una función llamada `add()` que acepta dos parámetros:

```js
function add(a,b){}
```

Dentro del cuerpo de la función, puede escribir el código para implementar una acción. Por ejemplo, la siguiente función `say()` simplemente muestra un mensaje a la consola:

```js
function say(message) {
	console.log(message);
}
```

En el cuerpo de la función `say()`, llamamos a la función `console.log()` para enviar un mensaje a la consola.

## Llamar a una función

Para usar una función, debe llamarla. Llamar a una función también se conoce como invocar una función. Para llamar a una función, usa su nombre seguido de argumentos ente paréntesis como este:

```js
functionName(arguments);
```

Al llamar a una función, **JavaScript** ejecuta el código dentro del cuerpo de la función. Por ejemplo, lo siguiente muestra como llamar a la función `say()` :

```
say('Hello');
```

En este ejemplo, llamamos a la función `say()` y le pasamos una cadena literal `'Hello'`.

## Parámetros vs Argumentos

Los términos **parámetros** y **argumentos** a menudo se usan indistintamente. Sin embargo, son esencialmente diferentes.

Al declara una función, se especifica los **parámetros**. Sin embargo, al llamar a una función, pasa los **argumentos** que corresponden a los parámetros.

Por ejemplo, en la función `say()`, el **parámetro** `message` y la cadena `'Hello'` es un **argumento** que corresponde al parámetro `message`.

## Devolver un valor 

Cada función en **JavaScript** devuelve implícitamente `undefined` a menos que especifique explícitamente un valor de retorno (return). Por ejemplo:
```js
function say(message){
	console.log(message);
}

let result = say('Hello');
console.log('Result:', result);
```

```
Salida:
Hello
Result: undefined
```

Para especificar un valor de retorno para una funcion, usa la declaracion `return` seguida de una expresion o un valor, como este:

```
return expression;
```

Por ejemplo, la siguiente funcion `add()` devuelve la suma de los dos argumentos:

```js
function add(a,b){
	return a + b;
}
```

A continuacion se muestra como llamar a la funcion `add()`:

```js
let sum = add(10,20);
console.log('Sum:', sum);
```

El siguiente ejemplo usa varias declaraciones `return` en una funcion para devolver diferentes valores segun las condiciones:

```js
function compare(a,b){
	if(a>b){
		return -1;
	}else if(a<b) {
		return 1;
	}
	return 0;
}
```

La funcion `compare()` compara dos valores. Vuelve:
- -1 si el primer argumento es mayor que el segundo.
- 1 si el primer argumento es menor que el segundo.
- 0 si el primer argumento es igual al segundo.

La funcion deja de ejecutarse inmediatamente cuando llega a la declaracion `return`. Por lo tanto, puede usar la delcaracion `return` sin un valor para salir de la funcion antes de tiempo, asi:

```js
function say(message){
	// show nothing if the message is empty
	if(! message){
		return;
	}
	console.log(mesage);
}
```

En este ejemplo, si `message` esta en blanco o `(undefined)`, la funcion `say()` no mostrara nada.

La funcion puede devolver un unico valor. Si desea devolver varios valores de una funcion, debe empaquetar estos valores en una matiz o un objeto. 

## Argumentos que son objetos

Dentro de una función, puede acceder a un objeto llamado `arguments` que representa los argumentos con nombre de la función.

El objeto `arguments` se comporta como una **matriz**, aunque no se una instancia del tipo Array.

Por ejemplo, puede utilizar corchetes `[]` para acceder a los argumentos: `arguments[0]` devuelve el primer argumento, `arguments[1]` devuelve el segundo, etc.

Ademas, puede usar la propiedad `length` del objeto `argumento` para determinar la cantidad de argumentos.

El siguiente ejemplo implementa una funcion generica `add()` que caclucla la suma de cualquier numero de argumentos.

```js
function add() {
	let sum = 0;
	for(let i = 0; i < arguments.length; i++){
		sum += arguments[i];
	}	
	return sum;
}
```

Por lo tanto, puede pasar cualqier cantidad de argumentos a la funcion `add()`, asi:

```js
console.log(add(1,2)); // 3
console.log(add(1,2,3,4,5)); // 15
```

## Función hosting

En **JavaScript**, puede usar una función antes de declararla. Por ejemplo:

```js
showMe(); // a hoisting example

function showMe() {
	console.log('an hoisting example');
}
```

Esta característica se llama `hosting`.

El `hosting` es un mecanismo mediante el cual el motor de **JavaScript** mueve físicamente las declaraciones de funciones a la parte superior del código antes de ejecutarlas.

A continuación se muestra la versión del código antes de que el motor de **JavaScript** lo ejecute:

```js
function showMe(){
	console.log('a hoisting example');
}

showMe(); // a hoisting example
```


# Las funciones son ciudadanos de primera clase

Las funciones de primera clase significa que puede **almacenar funciones en variables**, pasarlas a otras funciones como argumentos y devolverlas desde otras funciones como valores.
En otras palabras se refiere a la capacidad de las funciones de ser tratadas de manera similar a otros valores, como números, cadenas o objetos.
## Almacenamiento de funciones en variables

Las funciones son ciudadanos de primera clase en **JavaScript**. En otras palabras, puede tratar funciones como valores de otros tipos. 

Lo siguiente define la función `add()` y asigna el nombre de función a la variable `sum`:

```js
function add(a,b){
	return a+b;
}

let suma = add;
```

En la declaración de asignación, no incluimos los paréntesis de apertura y cierre al final del identificador `add`. Tampoco ejecutamos la función sino que hacemos referencia a la función.

Al hacer esto, podemos tener dos formas de ejecutar la misma función. Por ejemplo, podemos llamarlo normalmente de la siguiente manera:

```js
let result = add(10,20);
```

Alternativamente, podemos toda la función `add()` a través de la variable `sum` como esta:

```js
let result = sum(10,20);
```

## Pasar una funcion a otra funcion

Como las funciones son valores, puede pasar una funcion como argumento a otra funcion.

Lo siguiente declara la funcion `average()` que toma tres argumentos. El tercer argumento es una funcion:

```js
function average(a,b,fn){
	return fn(a,b) / 2;
}
```

Ahora, puede pasar la funcion `sum` a la funcion `average()` de la siguiente manera:

```js
let result = average(10,20,sum);
```

Ejemplo completo:

```js
function add(a, b) {
    return a + b;
}

let sum = add;

function average(a, b, fn) {
    return fn(a, b) / 2;
}

let result = average(10, 20, sum);

console.log(result);
```

```js
// Otro ejemplo 
let sum = (a,b)=> {
  return a+b;
}

function pares(a,b,fn){
    return (fn(a,b)%2 == 0)? 'Es par':'Es impar';
}

console.log(pares(5,2,sum));
```

## Devolver funciones desde funciones

Dado que las funciones son valores, puede devolver una función desde otra función.

La siguiente función `compareBy()` devuelve una función que compara dos objetos por una propiedad:

```js
function compareBy(propertyName){
	return function (a,b){
		let x = a[propertyName], 
			y = b[propertyName]
		if(x>y){
			return 1;
		} else if (x<y) {
			return -1;
		} else {
			return 0;
		}
	};
}
```

Tenga en cuenta que `a[propertyName]` devuelve el valor del `propertyName` del objeto `a`. Es equivalente a `a.propertyName`. Sin embargo, si `propertyName` contiene un espacio como `'Discount Price'`, debe usar la notacion de corchete para acceder a el.

Suponga que tiene una matiz de objetos de productos donde cada objeto de producto tiene dos propiedades: `name` y `price`.

```js
let products = [
	{name: 'iPhon', price: 900},
	{name: 'Samsung Galaxy', price: 850},
	{name: 'Sony Xperia', price: 700}
];
```

Puede ordenar una matriz llamando al metodo `sort()`. El método `sort()` acepta una función que compara dos elementos de la matiz como argumento, ordena una matiz alfabéticamente.

Por ejemplo, puede ordenar los objetos del producto según el nombre pasando una función devuelta por la función `compareBy()` de la siguiente manera:

```js
console.log('Products sorted by name:');
products.sort(compareBy('name'));

console.table(products);
```

```
Resultado 
Products sorted by name:
┌─────────┬──────────────────┬───────┐
│ (index) │       name       │ price │
├─────────┼──────────────────┼───────┤
│    0    │ 'Samsung Galaxy' │  850  │
│    1    │  'Sony Xperia'   │  700  │
│    2    │     'iPhone'     │  900  │
└─────────┴──────────────────┴───────┘
```

Del mismo modo, puede ordenar los objetos de producto por precios:

```js
// sort products by prices

console.log('Products sorted by price:');
products.sort(compareBy('price'));
console.log(prodicts);
```

``` 
Resultado
Products sorted by price:
┌─────────┬──────────────────┬───────┐
│ (index) │       name       │ price │
├─────────┼──────────────────┼───────┤
│    0    │  'Sony Xperia'   │  700  │
│    1    │ 'Samsung Galaxy' │  850  │
│    2    │     'iPhone'     │  900  │
└─────────┴──────────────────┴───────┘
```

Ejemplo todo unido 

```js
function compareBy(propertyName) {
  return function (a, b) {
    let x = a[propertyName],
      y = b[propertyName];

    if (x > y) {
      return 1;
    } else if (x < y) {
      return -1;
    } else {
      return 0;
    }
  };
}
let products = [
  { name: 'iPhone', price: 900 },
  { name: 'Samsung Galaxy', price: 850 },
  { name: 'Sony Xperia', price: 700 },
];

// sort products by name
console.log('Products sorted by name:');
products.sort(compareBy('name'));

console.table(products);

// sort products by price
console.log('Products sorted by price:');
products.sort(compareBy('price'));
console.table(products);
```

## Mas ejemplos de funciones de ciudadanos de primera clase

El siguiente ejemplo define dos funciones que convierten una longitud en centímetros a pulgadas y viceversa:

```js
function cmToIn(length) {
    return length / 2.54;
}

function inToCm(length) {
    return length * 2.54;
}
```

La siguiente funcion `convert()` tiene dos parametros. El primer parametro es una funcion y el segundo es la longitud que se convertira en funcion del primer argumento:

```js
function convert(fn, length) {
    return fn(length);
}
```

Para convertir `cm` a `in`, puede llamar a la funcion `convert()` y pasar la funcion `cmToIn` function a la funcion `convert()` como primer argumento:

```js
let inches = convert(cmToIn, 10);
console.log(inches); // 3.937007874015748
```

De manera similar, para convertir una longitud de pulgadas a centímetros, puede pasar la función`inToCm` a la función` convert()`, así:

```js
let cm = convert(inToCm, 10);
console.log(cm);
```

Codigo completo: 

```js
function cmToIn(length) {
  return length / 2.54;
}

function inToCm(length) {
  return length * 2.54;
}

function convert(fn, length) {
  return fn(length);
}

let inches = convert(cmToIn, 10);
console.log(inches);

let cm = convert(inToCm, 10);
console.log(cm);
```
# Funciones anónimas

## ¿Que son?

Una función anónima es una función sin nombre. A continuación se muestra como definir una función anónima:

```
(function () {
	//...
});
```

Tengo en cuenta que si no coloca la función anónima dentro de `()`, obtendrá un error de sintaxis, hace que la función `()` anónima sea una expresión que devuelve un objeto de función.

No se puede acceder a una función anónima después de su creación inicial. Por lo tanto, a menudo necesita asignarlo a una variable.

Por ejemplo, lo siguiente muestra una función anónima que muestra un mensaje:

```js
let show = function() {
	console.log('Anonymous function');
}

show();
```

En este ejemplo, la función no tiene nombre entre la palabra `function` y los paréntesis `()`.

Debido a que necesitamos llamar a la función anónima mas tarde, asignamos la función anónima a la variable `show`.

Dado que toda la asignación de la función anónima a la variable show constituye una expresión valida, no es necesario que envuelva la función anónima ente paréntesis `()`.

## Usar funciones con argumentos

En la practica, a menudo pasa funciones anónimas como argumentos a otras funciones. Por ejemplo:

```js
setTimeout(function(){
	console.log('Execute later after 1 second')
	},1000);
```

En este ejemplo, pasamos una función anónima a la función `setimeout()`. La función `setTimeout()` ejecuta esta función anónima un segundo después.

	Tenga en cuenta que las funciones son ciudadanos de 
	primera clase en JavaScript. Por lo tanto, puede 
	pasar una funcion a otra funcion como argumento.

## IIFE ()();

Si desea crear una función y ejecutarla inmediatamente después de la declaración, puede declarar una función anónima como esta:

```js
(function() {
	console.log('IIFE');
})();
```

Como funciona.

Primero, defina una expresión de función:

```js
(function () {
    console.log('Immediately invoked function execution');
})
```

Esra expresion devuelve una funcion.

En segundo lugar, llame a la funcion agregando los parentesis finales `()`.

```js
(
function() {
	console.log('Immediately invoked function execution');
}
)();
```

y, a veces, es posible que desee pasarle argumentos, como este:

```js
let person = {
	firstName: 'John',
	lastName: 'Doe'
};

(
function () {
	console.log(`${person.firstName} ${person.lastName}`);
}
)(person);
```

## Arrow function

**ES6** introdujo expresiones de funcion de flecha que proporciona una abreviatura para declara funciones anonimas:

Por ejemplo, esta funcion:

```js
let show = function () {
	console.log('Anonymous function');
}
```

... se puede acortar usando la siguiente funcion de flecha:

```js
let show = () => console.log('Anonymus function');
```

Del mismo modo, la siguiente funcion anonima:

```js
let add = function (a,b) {
	return a + b; 
};
```

... es funcionalmente equivalente a la siguiente funcion de flecha:

```js
let add = (a,b) => a+b;
```

# Comprender el paso por valor

En **JavaScript**, todos los argumentos de función simple se pasan por valor. Significa que **JavaScript** copia los valores de las variables en los argumentos de la función.

Los cambios que realice en los argumentos dentro de la función no reflejan las variables que pasan fuera de la función. En otras palabras, los cambios realizados en los argumentos no se reflejan fuera de la función.

Si los argumentos de la función se pasan por referencia, los cambios de variables que pase a la función se reflejaran de la función. 

## Paso por valor de valores primitivos

Echemos un vistazo al siguiente ejemplo:

```js
function square(x){
	x = x * x;
	return x;
}

let y = 10;
let result = square(y);

console.log(result); // 100
console.log(y); // 10 -- no cambia
```

*Como funciona?*

Primero, defina una función `square()` que acepte un argumento `x`. La función asigna el cuadrado de `x` al argumento `x`.

A continuación, declara la variable `y` e inicialice su valor en `10`:
![[Pasted image 20231105151337.png]]

Luego, pasa la variable `y` a la función `square()`. Al pasar la variable `y` a la función `square()`, **JavaScript** copia el valor de `y` a la variable `x`.
![[Pasted image 20231105151402.png]]

Después de eso, la función `square()` cambia la variable. Sin embargo, no afecta el valor de la variable `y` porque `x` y `y` son variables separadas.
![[Pasted image 20231105151455.png]]

Finalmente, el valor de la variable `y` no cambia después de que `square()` se completa la función.
![[Pasted image 20231105151514.png]]

Si **JavaScript** usara el paso por referencia, la variable `y` cambiara a `100` después de llamar a la función.

## Paso por valor de los valores de referencia

No es obvio ver que los valores de referencia también se pasan por valores. Por ejemplo:

```js
let person = {
	name: 'John',
	age: 23,
};

function increaseAge(obj){
	obj.age += 1;
}

increaseAge(person);

console.log(person);
```

Primero, defina la variable `person` que hace referencia a un objeto con dos propiedades `name` y `age` :
![[Pasted image 20231105151536.png]]

A continuación, defina la función `increaseAge()` que acepta un objeto `obj` y aumenta la propiedad `age` del argumento `obj` en uno.

Luego, pasa el objeto `person` a la función `increaseAge()` :
![[Pasted image 20231105151554.png]]

Internamente, el motor de **JavaScript** crea la referencia `obj` y hace que esta variable haga referencia al mismo objeto al que hace referencia la variable `person`.

Después de eso, aumente la propiedad `age` en uno dentro de la función `increaseAge()` a través de la variable `obj`.
![[Pasted image 20231105151628.png]]

Finalmente, accediendo al objeto a través de la referencia `person` :
![[Pasted image 20231105151644.png]]


Parece que **JavaScript** pasa un objeto por referencia porque el cambio en el objeto se refleja fuera de la función. Sin embargo, este no es el caso. 

De hecho, cunado pasa un objeto a una función, esta pasando la referencia de ese objeto, no el objeto real. Por lo tanto, la función puede modificar las propiedades del objeto a través de su referencia. 

Sin embargo, no puede cambiar la referencia pasada a la función. Por ejemplo:
```js
let person = {
  name: 'John',
  age: 25,
};

function increaseAge(obj) {
  obj.age += 1;

  // reference another object
  obj = { name: 'Jane', age: 22 };
}

increaseAge(person);

console.log(person);
```

Resultado:
```js
{ name: 'John', age: 26 }
```

En este ejemplo, la `increaseAage()`función cambia la `age`propiedad mediante el argumento `obj`:
![[Pasted image 20231105151914.png]]

y hace la referencia `obj` a otro objeto:

![[Pasted image 20231105151943.png]]

Sin embargo, la referencia `person` todavía hace referencia al objeto original cuya propiedad `age` cambia a `26`. En otras palabras, la función `increaseAge()` no cambia la referencia `person`.

Si este concepto todavía te confunde, puedes considerar los argumentos de la función como variables locales.

# Función recursivas

## Introducción

Una función recursiva es una función llamada a si misma hasta que no lo hace. Y esta técnica se llama recursividad.

Suponga que tiene una función llamada `recurse()`. Es una función recursiva `recurse()` si se llama a si misma dentro de su cuerpo, así:

```
function recurse() {
	// ...
	recurse();
	 // ...
}
```

Una función recursiva siempre tiene una condición para dejar de llamarse a si misma. De lo contrario, se llamara a si misma indefinidamente. Entonces, una función recursiva generalmente se parece a lo siguiente:

```
function recurse(){
	if(){
		// stop calling itself
		// ... 
	}else {
		recurse();
	}
}
```

Por lo general, utiliza funciones recursivas para desglosar un gran problema en otros mas pequeños.

Por lo general, encontrar funciones recursivas en estructuras de datos como arboles, binarios, gráficos, algoritmos como búsqueda binaria y clasificación rápida.

## Ejemplo de funciones recursivas

Tenemos algunos ejemplos del uso de funciones recursivas.

### 1) Un ejemplo simple

Suponga que necesita desarrollar una función que cuente hacia atrás desde un numero especifico hasta 1. 

Por ejemplo, para contar hacia ataras del 3 al 1, a continuación se muestra la función `countDown()` :

```js
function countDown(fromNumber){
	console.log(fromNumber);
}

countDown(3);
```

Esto muestra `countDown(3)` solo el numero 3.
Para contar del numero 3 al 1, puede:

- mostrar el numero 3
- llama al `countDown(2)` que muestre el numero 2.
- llama al `countDown(1)` que muestre el numero 1.

Lo siguiente cambia a función recursiva:

```js
function countDown(fromNumber) {
    console.log(fromNumber);

    let nextNumber = fromNumber - 1;

    if (nextNumber > 0) {
        countDown(nextNumber);
    }
}
countDown(3);
```

Esto `countDown(3)`se ejecutará hasta que se exceda el tamaño de la pila de llamadas, así:

```js
Uncaught RangeError: Maximum call stack size exceeded.
```

… porque no tiene la condición de dejar de llamarse a sí mismo.

La cuenta regresiva se detendrá cuando el siguiente número sea cero. Por lo tanto, agrega una condición if de la siguiente manera:

```js
function countDown(fromNumber) {
    console.log(fromNumber);

    let nextNumber = fromNumber - 1;

    if (nextNumber > 0) {
        countDown(nextNumber);
    }
}
countDown(3);
```

Parece funcionar `countDown()` como se esperaba.

Sin embargo, como se menciona en el tipo de funciones, el nombre de la función es una referencia al objeto de función real.

Si el nombre de la función se establece en `null` algún lugar del código, la función recursiva dejará de funcionar.

Por ejemplo, el siguiente código generará un error:

```js
let newYearCountDown = countDown;
// somewhere in the code
countDown = null;
// the following function call will cause an error
newYearCountDown(10);
```
error:
```js
Uncaught TypeError: countDown is not a function
```

Cómo funciona el script:
- Primero, asigne el nombre `countDown` de la función a la variable `newYearCountDown`.
- En segundo lugar, establezca la referencia `countDown` de la función en `null`.
- En tercer lugar, llame a la función `newYearCountDown`.

El código provoca un error porque el cuerpo de la función `countDown()` hace referencia al nombre `countDown` de la función, que se configuró `null` en el momento de llamar a la función.

Para solucionarlo, puede utilizar una expresión de función con nombre de la siguiente manera:

```js
let countDown = function f(fromNumber) {
    console.log(fromNumber);

    let nextNumber = fromNumber - 1;

    if (nextNumber > 0) {
        f(nextNumber);
    }
}

let newYearCountDown = countDown;
countDown = null;
newYearCountDown(10);
```
### 2) Ejemplo de calcular la suma de n números naturales

Suponga que necesita calcular la suma de números naturales del 1 al n utilizando la técnica de recursividad. Para hacer eso, necesita definir recursivamente `sum()` de la siguiente manera:

```
sum(n) = n + sum(n-1)
sum(n-1) = n - 1 + sum(n-2)
...
sum(1) = 1
```

A continuación se ilustra la función `sum()` recursiva:

```js
function sum(n) {
  if (n <= 1) {
    return n;
  }
  return n + sum(n - 1);
}
```
# Parámetros predeterminados 

## TL;RD

```js
function say(message = 'hi'){
	console.log(message);
}
say(); // hi
say('Hello'); // Hello
```

El valor predeterminado del parámetro `message` en la función `say()` es `Hi`.

En **JavaScript**, los parámetros de función predeterminados le permiten inicializar parámetros con nombre con valores predeterminados si no se pasan valores `undefined` a la función.


## Argumentos vs Parametros

A veces, puede usar los terminos argumento y parametro indistintamente. Sin embargo, por definicion, los *parametros* son lo que especificamos en la declaracion de la funcion, mientras que los *argumentos* son lo que pasas a la funcion.

Considera la siguiente funcion `add()` :

```js
function add(x, y) {
	return x + y;
}

add(100,200);
```

En este ejemplo, `x` y `y`  son los parámetros de la función `add()`, y los valores pasados a la función `add()` `100` y `200` son los argumentos.

## Establecer parámetros predeterminados para una función

En **JavaScript**, un parámetro tiene un valor predeterminado de `undefined`. Significa que si no pasa los argumentos a la `funcion`, sus parámetros tendrán los valores predeterminados de `undefined`. 

Vea el siguiente ejemplo:

```js
function say(message){
	console.log(message);
}
say(); // undefined
```

La función `say()` toma el parámetro `message`. Debido a que no pasamos ningún argumento a la función `say()`, el valor del parámetro `message`  es `undefined`.

Suponga que desea dar al parámetro `message` un valor predeterminado de 10.

Una forma típica de lograr esto es probar el valor del parámetro y asignar un valor predeterminado si es `undefined` utiliza un operador ternario:

```js
function say(message) {
	message = typeof message !== 'undefined' ? message : 'hi';
	console.log(message);
}
say(); // 'hi'
```

En este ejemplo, no pasamos ningún valor a la función `say()`. Por lo tanto, el valor predeterminado del argumento del mensaje es `undefined`. Dentro de la función, reasignamos la variable `message` a la cadena `hi`.

**ES6** le proporciona una manera mas fácil de establecer los valores predeterminados para los parámetros de la función como esta:

```js
function fn(param1=default1, param2=default2,...){
}
```

En la sintaxis anterior, utiliza el operador de asignación `(=)` y el valor predeterminado después del nombre del parámetro para establecer un valor predeterminado para ese paramento. Por ejemplo:

```js
function say(message='hi'){
	console.log(message);
}

say() // 'hi'
say(undefined); // 'hi'
say('Hello'); // 'Hello'
```

## Mas ejemplos de parámetros predeterminados 

Veamos algunos ejemplos para conocer algunas opciones disponibles para establecer valores predeterminados de los parámetro de la función.

### 1) Pasar argumentos indefinidos

La siguiente función `createDiv()` crea una nuevo elemento `<div>` en el documento con un alto, ancho y estilo de borde específicos:

```js
function createDiv (height = '100px', width='100px', border="solid 1px red"){
	let div = document.createElement('div');
	div.style.height = height;
	div.style.width = width;
	div.style.border = border;
	document.body.appendChild(div);
	return div;
}
```

Lo siguiente no pasa ningún argumento a la función, por lo que la función `createDiv()` usa los valores predeterminados para los parámetros.

```
createDiv()
```

Suponga que desea utilizar los valores predeterminados para los parametros de alto y ancho y el estilo de borde especifico. En este caso, debe pasar valores `undefined` a los dos primeros parametros de la siguiente manera: 

```js
createDiv(undefined, undefined, 'solid 5px blue');
```

### 2) Evaluación de parámetros predeterminados

El motor de **JavaScript** evalúa los argumentos predeterminados en el momento en que llama a la función. 

```js
function put(toy, toyBox = []){
	toyBox.push(toy);
	return toyBox;
}

console.log(put('Toy Car'));
// -> ['Toy car']
console.log(put('Teddy Bear'));
// -> ['Teddy Bear'], not ['Toy car', 'Teddy Bear']
```

El parametro puede tomar un valor predeterminado que es el resultado de una funcion.

Considere el siguiente ejemplo:

```js
function date(d = today()){
	console.log(d);
}
function today(){
	return (new Date()).toLocaleDateString("en-US");
}
date();
```

La función `date()` toma un parámetro cuyo valor predeterminado es el valor devuelto por la función `toyday()`. La función `today()` devuelve la fecha de hoy en un formato de cadena especificado.

Cuando declaramos la función `date()`, la función `today()` aun no se ha evaluado hasta que la llamamos `date()`.

Podemos usar esta característica para hacer que los argumentos sean obligatorios. Si la persona que llama no pasa ningún argumento, lanzamos un error de la siguiente manera:

```js
function requiredArg() {
	throw new Error('The arguments is required');
}
function add(a = requiredArg(), y = requiredArg()){
	return x + y;
}
add(10); // error
add(10, 20); // ok
```

### 3) Uso de otros parámetros en valores

Puede asignar a un parámetro un valor predeterminado que haga referencia a otros parámetros predeterminados, como se muestra en el siguiente ejemplo:

```js
function add(x = 1, y = x, z = x + y){
	return x + y + z;
}
console.log(add()); // 4
```

La lista de parámetros parece tener su propio alcance. Sin hacer referencia al parámetro que aun no se ha inicializado, obtendrá un error. Por ejemplo:

```js
function subtract( x = y, y = 1){
	return x - y;
}

subtract(10); // Error Uncaught ReferenceError: Cannot access 'y' before initialization
```

**Uso de función**

Puede utilizar un valor de retorno de una función como valor predeterminado para un parámetro. Por ejemplo:

```js
let taxRate = () => 0.1;
let getPrice = function(price, tax = price * taxRate()){
	return price + tax;
}

let fullPrice = getPrice(100);
console.log(fullPrice); //110
```

En la función `getPrice()`, llamamos a la función `taxRate()` para obtener la tasa de impuestos y usar esta tasa de impuestos para calcular el monto del impuesto a partir del precio.

**El objeto de los argumentos**

El valor del objeto `arguments` dentro de la función es el numero de argumentos reales que pasa a la función. Por ejemplo:

```js
function add(x, y = 1, z = 2){
	console.log(arguments.length);
	return x + y + z;
}
add(10); // 1 
add(10, 20); // 2 
add(10, 20, 30); // 3
```
Ahora, debes comprender los parámetros de función predeterminados de JavaScript y cómo usarlos de manera efectiva.

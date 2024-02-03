# if
La instrucción `if` ejecuta el bloque si una condición es `true`. A continuación se muestra la sintaxis de la condición `if`:

```js
if(condition)
	statement;
```

La `condition` puede ser un valor o una expresión. Normalmente, la condición se evalúa como un valor `booleano`, que es `true` o `false`.

Si el `condition` se evalúa como `true`, la declaración `if` se ejecuta el `statement`. De lo contrario, la sentencia `if` pasa el control a la sentencias siguiente.

El siguiente diagrama de flujo ilustra como funciona la instrucción `if`:

![[Pasted image 20231105133754.png]]

Si `condition` se evalúa como un valor no booleano, **JavaScript** implícitamente convierte su resultado en un valor booleano llamado a la función `Boolean()`.

Si tiene mas de una declaración para ejecutar, debe envolverlas en un bloque usando un par de llaves de la siguiente manera:

```js
if ( condition ) {
	// statements to execute
}
```

Sin embargo, es una buena practica usar siempre llaves con la declaración `if`. Al hacer esto, hace que su código sea mas fácil de mantener y evita posibles errores.

## Ejemplo de declaración if

El siguiente ejemplo usa la declaración `if` para verificar si la edad es igual o mayor que `18` :

```js
let age = 18;
if( age >= 18 ){
	console.log('You can sign up');
}
```

## if anidados

Es posible usar una declaración `if` dentro de otro `if` declaración. 

```js
let age = 18;
let state = 'CA';

if( state == 'CA'){
	if( age >= 16){
		console.log('You can drive.');
	}
}
```

En la práctica, debe evitar el uso `if` de sentencias anidadas tanto como sea posible. Por ejemplo, puede usar el operador `&&` para combinar las condiciones y usar `if` declaraciones de la siguiente manera:

```js
let age = 16;
let state = 'CA';

if (state == 'CA' && age == 16) {
  console.log('You can drive.');
}
```

# if else

## if else 

La declaración `if` ejecuta un bloque si una condicion es `true`. Cunado la condición es `false`, no hace nada. Pero si desea ejecutar una declaración si la condición es `false`, puede usar una declaración `if ...  else`.

A continuación se muestra la sintaxis  de la sentencia `if ... else` :

```js
if( condition ){
	// ...
} else {
	// ...
}
```

En esta sintaxis, el `condition` es un valor o una expresión que se evalúa como  `true` o `false`. Si la condición es `true`, la declaración `if...else` ejecuta el bloque que sigue a la rama `if`.

Si la condición es `false`, la declaración `if ... else` ejecuta el bloque que sigue a la rama `else`.

Por lo general, `condition` se evalúa como un valor booleano, que es `true` o `false`. Sin embargo, si se evalúa como un valor no booleano, la declaración `if...else` lo convierte al valor booleano.

El siguiente diagrama de flujo ilustra como funciona la instrucción `if...else`:

![[Pasted image 20231105134026.png]]
## Ejemplos de sentencias if...else

El siguiente ejemplo utiliza la declaración `if...else` para verificar si la edad es mayor o igual a 18:

```js
let age = 18;

if (age >= 18) {
  console.log('You can sign up.');
} else {
  console.log('You must be at least 18 to sign up.');
}
```

# if else if

## Declaración if else if

Las declaraciones `if` y `if else` aceptan una sola condición y ejecuta el bloque `if` o `else` en consecuencia según la condición.

Para verificar múltiples condiciones y ejecutar el bloque correspondiente si una condición es `true`, use la declaración `if...else...if` como esta:

```js
if (condition1) {
  // ...
} else if (condition2) {
  // ...
} else if (condition3) {
  //...
} else {
  //...
}
```

En esta sintaxis, la declaración `if...else...if` tiene tres condiciones. En teoría, puedes tener tantas condiciones como quieras, donde cada rama `else...if` tiene una condición.

La declaración `if...else...if` verifica las condiciones de arriba a abajo y ejecuta el bloque correspondiente si la condición es `true`.

La declaración `if...else...if` deja de evaluar las condiciones restantes tan pronto como una condición es `true`. Por ejemplo, si `condition2` es `true`, la declaración `if...else...if` no evaluará el `condition3`.

Si todas las condiciones son `false`, la `if...else...if`declaración ejecuta el bloque en la rama `else`.

El siguiente diagrama de flujo ilustra cómo funciona la instrucción `if...else...if`:

![[Pasted image 20231105134130.png]]
## Ejemplo de sentencia if ... else if

El siguiente ejemplo utiliza la declaración `if...else` para verificar si la edad es mayor o igual a 18:

```js
let age = 18;

if (age >= 18) {
  console.log('You can sign up.');
} else {
  console.log('You must be at least 18 to sign up.');
}
```

# Operadores ternarios 

![[Pasted image 20231105134236.png]]

## Operadores ternarios

Cuando desea ejecutar un bloque si una condición se evalúa como `true`, a menudo usa una instrucción `if...else`. Por ejemplo:

```js
let age = 18;
let message;

if (age >= 16) {
  message = 'You can drive.';
} else {
  message = 'You cannot drive.';
}

console.log(message);
```

En este ejemplo, mostramos un mensaje que indica que una persona puede conducir si la edad es mayor o igual a 16 años. Alternativamente, puede usar un operador ternario en lugar de la declaración `if-else` como esta:

```js
let age = 18;
let message;

age >= 16 ? (message = 'You can drive.') : (message = 'You cannot drive.');

console.log(message);
```

O puede usar el operador ternario en una expresion de la siguiente manera:

```js
let age = 18;
let message;

message = age >= 16 ? 'You can drive.' : 'You cannot drive.';

console.log(message);
```

Aqui esta la sintaxis del operador ternario:

`condition ? expressionIfTrue : expressionIfFalse;`

En esta sintaxis, el `condition` es una exprecion que se evalua como un valor booleano, ya sea `true` o `false`.

Si la condición es `true` la primera expresión ( ). `expresionIfTrue` si es falso, se ejecuta la segunda expresión ( ).

A continuación se muestra la sintaxis del operador ternario utilizando en una expresión:

```js
let variableName = condition ? expressionIfTrue : expressionIfFalse;
```

En esta sintaxis, si `condition` es `true`, `variableName` tomará el resultado de la primera expresión ( `expressionIfTrue` ) o de `expressionIfFalse` lo contrario.

## Operadores ternarios 

Tenemos algunos ejemplos del uso del operador ternario.

### 1) Usar el operador ternario de js para hacer múltiples declaraciones

El siguiente ejemplo usa el operador ternario para realizar múltiples operaciones, donde cada operación está separada por una coma. Por ejemplo:

```js
let authenticated = true;
let nextURL = authenticated
  ? (alert('You will redirect to admin area'), '/admin')
  : (alert('Access denied'), '/403');

// redirect to nextURL here
console.log(nextURL); // '/admin'
```

En este ejemplo, el valor devuelto por el operador ternario es el último valor de la lista separada por comas.

### 2) Operador ternario simplificado

Vea el siguiente ejemplo:

```js
let locked = 1;
let canChange = locked != 1 ? true : false;
```

Si `locked` es 1, entonces la variable `canChange` se establece en `false` ; de lo contrario, se establece en `true` . En este caso, puede simplificarlo usando una expresión booleana de la siguiente manera:

```js
let locked = 1;
let canChange = locked != 1;
```

### 3) Ejemplo de uso de múltiples operadores ternarios 

El siguiente ejemplo muestra como utilizar dos operadores ternarios en la misma expresión:

```js
let speed = 90;
let message = speed >= 120 ? 'Too fast': speed >= 80 ? 'Fast' : 'OK';

console.log(message); // Fast
```

Es una buena practica usar el operador ternario cuando facilita la lectura del código. Si la lógica contiene muchas declaraciones `if...else`, debe evitar el uso de operadores ternarios.

En resumen utilice el operador ternario de Js `(?:)` para que le código sea mas conciso.

# switch

La declaración `switch` evalúa un `expression`, compara su resultado con `case` los valores y ejecuta la declaración asociada con el valor `case` coincidente.

A continuación se ilustra la sintaxis de la `switch`: 

```js
switch (expression) {
    case value1:
        statement1;
        break;
    case value2:
        statement2;
        break;
    case value3:
        statement3;
        break;
    default:
        statement;
}
```

La sentencia `switch` es como la sentencia `if...else if` . Pero tiene una sintaxis mas legible.

El siguiente diagrama de flujo ilustra el flujo de `switch`:

![[Pasted image 20231105134535.png]]

En la práctica, a menudo usa una declaración `switch` para reemplazar una declaración `if...else...if` compleja para hacer que el código sea más legible.

Técnicamente, la declaración `switch` es equivalente a la siguiente `if...else...if` declaración:

```js
if (expression === value1) {
  statement1;
} else if (expression === value2) {
  statement2;
} else if (expression === value3) {
  statement3;
} else {
  statement;
}

```

# while

## Declaración while

La declaración de **JavaScript** `while` crea un bucle que ejecuta un bloque siempre que una condición se evalué como `true`.

A continuación se ilustra la sintaxis de la instrucción `while`:

```
while (expression) {
    // statement
}
```

La instrucción `while` evalúa `expression` antes de cada iteración del ciclo.

Si la `expression` se evalúa como `true`, la declaración `while` ejecuta el `statement`. De lo contrario, el bucle `while` sale.

Debido a que el bucle `while` evalúa `expression` antes de cada iteración, se conoce como bucle de prueba previa. 

Si `expression` se evalúa `false` antes de que ingrese el ciclo, el ciclo `while` nunca se ejecutar.

El siguiente diagrama de flujo ilustra la declaración `while` :

![[Pasted image 20231105134646.png]]


	Tenga en cuenta que si desea ejecutar la delcarion
	 al menos una vez y vereficar la condicion despues 
	 de cada iteracion, debe usar la declaracion 
	 do ... while

## Ejemplo

El siguiente ejemplo usa la declaración `while` para enviar los números impares entre 1 y 10 a la consola:

```js
let count = 1;
while (count < 10) {
    console.log(count);
    count +=2;
}
```

Como funciona el guion
- Primero, declare e inicialice la variable `count` a  `1`.
- En segundo lugar, ejecute la declaración dentro del ciclo si la  variable `count` es menor que `10`. En cada iteración, envíe el conteo a la consola y aumente el conteo en `2`.
- En tercer lugar, después `5` de las iteraciones, el `count` es `11`. Por lo tanto, la condición `count < 10` es `false`, el bucle sale.

# do while

## Declaración de do while

La declaración `do while` crea un bucle que ejecuta un bloque hasta que una condición se evalúa como `false`. La siguiente instrucción ilustra la sintaxis del ciclo `do while`:

```js
do {
	statement;
} while ( expression );
```

A diferencia del bucle `while`, el `do while` siempre ejecuta `statement` al menos una vez antes de evaluar el `expression`.

Debido a que el `do ... while` evalúa la expresión después de cada iteración, a menudo se le denomina ciclo posterior a la prueba.

Dentro del cuerpo del ciclo, debe realizar cambios en algunas variables para asegurarse de que `expression` esta `false` después de algunas iteraciones. De lo contrario, tendrás un bucle indefinido.

Tenga en cuenta que parte de **ES6+**, el punto y coma final `(;)` despues de `while(expression)` es opcional. Asi que puedes usar la siguiente sintaxis:

```js
do{
	statement;
} while(expression)
```

El siguiente diagrama de flujo ilutara la declaración `do-while`:

![[Pasted image 20231105134756.png]]

En la practica, a menudo usa la declaración `do while` cuando desea ejecutar el cuerpo del ciclo al menos una vez antes de verificar la condición.

## Ejemplo de instrucciones do while

Tomemos algunos ejemplos del uso de la declaración `do while`.

### 1) Ejemplo simple de instrucción do while

El siguiente ejemplo usa la instrucción `do while` para enviar cinco números del 0 al 4 a la consola:

```js
let count = 0;
do{
	console.log(count);
	count++;
} while( count < 5)
```

### 2) Usar la declaración do while para hacer un juego simple de adivinanzas de números

El siguiente ejemplo usa la declaración `do while` para generar un juego de adivinanzas.

El script genera un numero entero aleatorio entre 1 y 10. Y tiene que hacer una serie de conjeturas hasta que tu numero coincida con el numero aleatorio. 

```js
// generate a secret number between 1 and 10
const MIN = 1;
const MAX = 10;

let secretNumber = Math.floor(Math.random() * (MAX - MIN + 1)) + MIN;

let guesses = 0; // for storing the number of guesses
let hint = ''; // for storing hint
let number = 0;
do {
  // get input from user
  let input = prompt(`Please enter a number between ${MIN} and ${MAX}` + hint);

  // get the integer
  number = parseInt(input);

  // increase the number of guesses
  guesses++;

  // check input number with the secret number provide hint if needed
  if (number > secretNumber) {
    hint = ', and less than ' + number;
  } else if (number < secretNumber) {
    hint = ', and greater than ' + number;
  } else if (number == secretNumber) {
    alert(`Bravo! you're correct after ${guesses} guess(es).`);
  }
} while (number != secretNumber);

```

Como funciona

Primero, declare las constantes MIN y MAX e inicialice sus valores en 1 y 10:

```js
const MIN = 1;
const MAX = 10;
```

En segundo lugar, use la funcion `Math.random()` para generar un numero aleatorio de punto flotante con el valor en el rango de 0 y 1 ( incluido cero pero no uno ).

Para generar un numero aleatorio entre MIN y MAX (exclusivo), utiliza la siguiente expresión:

```js
Math.random() * (MAX - MIN + 1)
```

Sin embargo, el resultado es un numero de punto flotante. Por lo tanto, debe usar la funcion `Math.floor()` para convertirlo en un numero entero:

```js
Math.floor(Math.random() * (MAX - MIN + 1))
```

Para generar un numero aleatorio entre min y max, utiliza la siguiente expresion:

```js
let secretNumber = Math.floor(Math.random() * (MAX - MIN + 1)) + MIN;
```

En tercer lugar, defina tres variables para almacenar la cantidad de conjeturas, sugerencias y el numero de entradas del usuario:

```js
let guesses = 0; // for storing the number of guesses
let hint = ''; // for storing hint
let number = 0;
```

Cuatro, use la funcion `input()` para obtener la entrada del usuario:

```js
let input = prompt(`Please enter a number between ${MIN} and ${MAX}` + hint);
```

Tenga en cuenta que la función `input()` solo funciona en los navegadores web. Si ejecuta el código en otro entorno, como **node.js**, verifique la función correspondiente.

La función `input()` devuelve una cadena, por lo tanto, debe usar la función `parseInt()` para convertirla en un numero entero:

```js
number = parseInt(input);
```

Quinto, aumente el numero de conjeturas en cada iteracion:

```js
guesses++;
```

Sexto, verifique el numero de entrada con el numero secreto (aleatorio) y de una pista. Si los números coinciden, muestra el mensaje usado la función `alter()`:

```js
if (number > secretNumber) {
  hint = ', and less than ' + number;
} else if (number < secretNumber) {
  hint = ', and greater than ' + number;
} else if (number == secretNumber) {
  alert(`Bravo! you're correct after ${guesses} guess(es).`);
}
```

Séptimo, realice la siguiente iteración hasta que el numero coincida con el numero secreto.

```js
while (number != secretNumber);
```

# Bucle for

## bucle for

La declaracion `for` crea un bucle con tres expresiones opcionales. A continuacion se ilustra la sintaxis de la delcaracion `for` de bucle:

```
for (initializer; condition; iterator) {
    // statements
}
```

### 1) Inicializacion

La declaración `for` se ejecuta `initializer` solo una vez comienza el bucle. Por lo general, declara e inicializa una variable de bucle local en el inicializador.

### 2) condición

El `for` evalúa `condition` antes de cada iteración. Si la condición esta `true` ( o no esta presente). ejecuta la siguiente iteración. De lo contrario, terminara el bucle.

### 3) Iterador

La instrucción `for` ejecuta `iterator` después de cada iteración.

El siguiente diagrama de flujo ilustra el `for` :

![[Pasted image 20231105135047.png]]

En el ciclo `for`, las tres expresiones son opcionales. A continuación se muestra el bucle `for` sin ningún expresión:

```
for(;;){
	// statements
}
```


# break

## Declaración de label

En **JavaScript**, una declaración para su uso posterío. Aquí esta la sintaxis de la declaración `label`:

```
label: statement;
```

En esta sintaxis, la etiqueta puede ser cualquier identificador valido. Por ejemplo, lo siguiente muestra como un bucle `for` usa la etiqueta `outer`:

```js
outer: for( let i = 0; i < 5; i++) {
	console.log(i);
}
```

Una vez que define una etiqueta, puede hacer referencia a ella en la declaración `break` o `continue`.

## break
La declaración de `break` finaliza prematuramente un bucle como `for`, `do while` y `while`, un `switch` o una declaración `label`. Aquí esta la sintaxis de la declaración `break`:

```js
break [label];
```

En esta sintaxis, el `label` es opcional si usa la instruccion `break` en un bucle o `switch`. Sin embargo, si usa la declaración `break` con una declaración de etiqueta, debe especificarla.

## Usar el break para la ruptura de bucle for

La siguiente declaracion `for` genera cinco numeros del `0` a `4` :

```js
for( let i = 0; i < 5; i++){
	console.log(i);
}
```

Para terminar el `for` antes de tiempo, puede usar una declaracion `break` . Por ejemplo, lo siguiente ilustra como usar una declaracion `break` dentro de un `for` :

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
  if (i == 2) {
    break;
  }
}
```

En este ejemplo, usamos una instrucion `if` dentro del ciclo. Si el valor actua de `i` es `2`, la sentencia `if` ejecuta la setencia `break` que finaliza el bucle.

Este diagrama de flujo ilustra como funciona la instrucción `break` en un `for`:

![[Pasted image 20231105135347.png]]


## Uso de la sentencia break para un bucle anidado

Un bucle anidado tiene un bucle dentro de otro. Por ejemplo, lo siguiente usa un bucle anidado `for` para generar un par de números de `1` a `3`:

```js
for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    console.log(i, j);
  }
}
```

Si usa una declaración `break` dentro de un ciclo interno, solo termina el ciclo que lo contiene. Por ejemplo:

```js
for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    if (i + j == 4) {
      break;
    }
    console.log(i, j);
  }
}
```

```
Resultado: 
1 1
1 2
2 1
```

En este ejemplo, si la suma de `i` y `j` es `4`, la declaracion `break` finaliza el ciclo interno. Para terminar el ciclo anidado, usa una declaración de etiqueta. Por ejemplo

```js
outer: for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    if (i + j == 4) {
      break outer;
    }
    console.log(i, j);
  }
}
```

```
Resultado
1 1
1 2
```

En este ejemplo, etiquetamos el bucle externo con la etiqueta `outer`. Dentro del ciclo interno, específicamente la etiqueta `outer` en la instrucción `break`. La declaración `break` para terminar el bucle anidado si la suma de `i` y `j` es `4`.

## Uso de la declaración break en un ciclo while

La siguiente envía cinco números del 1 al 5 a la consola mediante el bucle `while`:

```js
let i = 0;

while(i < 5){
	i++;
	console.log(i);
}
```

Al igual que el bucle `for`, la instrucción `break` finaliza un bucle `while` de forma prematura. Por ejemplo:

```js
let i = 0;

while(i<5){
	i++;
	console.log(i);
	
	if(i==3){
		break;
	}
}
```

El siguiente diagrama de flujo ilustra como funciona la instrucción break en un bucle `while`.

![[Pasted image 20231105135422.png]]

# continue

## Declaración de continue

La declaración de `continue` finaliza la ejecución de la declaración en la iteración actual de un bucle, como un bucle `for`, `while` y `do while`, e inmediatamente continua con la siguiente interacción.

Aquí esta la sintaxis de la declaración `continue`:

```
continue [label];
```

En esta sintaxis, la etiqueta es opcional. Es un identificador valido asociado a la etiqueta de una sentencia.

Por lo general, se usa `continue` con un declaración `if` como esta:

```
// inside a loop
if(condition){
	continue;
}
```

En esta sintaxis, la sentencia `if` especifica una condición para ejecutar la sentencia `continue` dentro de un bucle.

## Instrucción continúe en bucle for

Cuando se usa la declaración `continue` en un ciclo `for`, no termina el ciclo por completo. En su lugar, salta a la expresión `iterator`.

El siguiente diagrama de flujo ilustra como funciona la instrucción `continue` 

![[Pasted image 20231105135649.png]]


El siguiente ejemplo utiliza `continue` un bucle `for` para mostrar el número impar en la consola

```js
for(let i = 0; i < 10; i++){
	if(i%2 === 0){
		continue;
	}
console.log(i);
}
```

## Usando la declaración continue en un bucle while

Cuando se utiliza la declaración `continue` en un bucle `while`, no finaliza por completo le ejecución del bucle. En cabio, vuelve a la condición. 

El siguiente diagrama de flujo muestra cómo funciona la instrucción de `continue` en un `while`:

![[Pasted image 20231105140221.png]]

El siguiente ejemplo utiliza la declaración `continue` en un bucle `while` para mostrar los números impares del 1 al 10:

```js
let i = 0;
while (i < 10) {
  i++;
  if (i % 2 === 0) {
    continue;
  }
  console.log(i);
}
```

# Comma operator

**JavaScript** usa una coma `(,)` para representar el operador de coma. Un operador de coma toma dos expresiones, las evalua de izquierda a derecha y devuelve el valor de la expresion correcta.

```
leftExpression, rightExpression
```

Por ejemplo:

```js
let result = (10,10+20);
console.log(result); // 30
```

En este ejemplo, 10, 10 + 20 devuelve el valor de la expresión correcta, que es 10 + 20. Por lo tanto, el valor del resultado es 30.

```js
let x = 10;
let y = (x++, x+1);

console.log(x,y); // 11  12
```

En este ejemplo, aumentamos el valor de `x` en uno `(x++)`, sumamos uno a `x` `(x+1)` y asignamos `x` a `y`. Por lo tanto, `x` es `11`, y `y` esta `12` después del enunciado.

Sin embargo, para que el código sea mas explicito, puede usar dos declaraciones en lugar de una declaración con un operador de coma como esta:

```js
let x = 10;
x++;
let y = x+1;

console.log(x,y);
```

Este código es mas explicito.

En la practica, es posible que desee utilizar el operador de coma dentro de un ciclo `for` para actualizar varias variables cada vez que se ejecuta el ciclo.

El siguiente ejemplo usa el operador coma en un bucle for para mostrar una matriz de nuevos elementos como una matriz de 3 filas y tres columnas:

```js
// *Ejemplo chido*
let board = [1, 2, 3, 4, 5, 6, 7, 8, 9];

let s = '';

for (let i = 0, j = 1; i < board.length; i++, j++) {
  s += board[i] + ' ';
  if (j % 3 == 0) {
    console.log(s);
    s = '';
  }
}
/*
Resultado:
	1 2 3
	4 5 6
	7 8 9
*/
```

# Sintaxis
## Espacio en blanco

Los espacios en blanco se refiere a los caracteres que proporciona el espacio entre otros caracteres. **JavaScript** tiene el siguiente espacio en blanco:

- Retorno de carro
- Espacio
- Nueva linea
- Tab

El motor de **JavaScript** ignora los espacios en blanco. Sin embargo, puede usar espacios en blanco para formatear el código para que sea fácil de leer y mantener.

El siguiente código **JavaScript** no usa espacios en blanco:

```js
let formatted = true; if(formatted) { console.log('The code is easy to read');}
```

Es equivalente al siguiente código que usa espacios en blanco. Por lo tanto, este código es mucho mas fácil de leer:

```js
let formatted = true;

if(formatted){
	console.log('The code is easy to read');
}
```

Tenga en cuenta que los paquetes de **JavaScript** elimina todos los espacios en blanco de los archivos de **JavaScript** y los coloca en un solo archivo para su implementación. Al hacer esto, los paquetes de **JavaScript** hacen que el código **JavaScript** sea mas ligero y rápido de cargar en los navegadores web.

## Declaractiones

Una declaración es un código que declara una variable o le indica al motor de **JavaScript** que realice una tarea. Una declaración simple termina con un punto y coma `(;)`.

Anuqué el punto y coma `(;)` es opcional simplemente debe usarlo para terminar un declaración. Por ejemplo, lo siguiente declara una variable y la muestra en la consola:

```js
let message = "Welcome to JavaScript";
console.log(message);
```

## Bloques

Un **bloque** es una secuencia de cero o mas declaraciones simples. Un bloque esta delimitado por un para de corchetes `{}`. Por ejemplo:

```js
if(window.localStorage){
	console.log('The local storage is supported');
}
```

## Identificadores

Un identificador es un nombre que elige para variables, parámetros, funciones, clases, etc. Un nombre de identificador comienza con una letra `(a-z A-Z)`, un guion bajo `(_)` o un signo de dólar `($)` y es seguido por una secuencia de caracteres que incluyen `(a-z A-Z)`, un números `(0-9)`, guiones bajos `(_)` y signos de dólar `($)`.

Tenga en cuenta que la letra no se limita al carácter **ASCII** y puede incluir **ASCII** extendido o Unicode, aunque no se recomienda.

Los identificadores distinguen entre mayúsculas y minúsculas. Por ejemplo, el `message` es diferente del `Message`.

## Comentarios

Los comentarios le permiten agregar notas o sugerencias al código **JavaScript**. Al ejecutar el código, el motor de **JavaScript** ignora los comentarios.

**JavaScript** admite comentarios de una sola lineal y de bloque.

### Comentarios de una sola línea

Un comentario de una sola línea comienza con dos caracteres de barras diagonales `(//)`.

Un comando de una sola línea convierte todo el texto que sigue `//` en la misma línea en comentario. Por ejemplo:

```js
// This is a single-line comment
```

### Comentarios de bloque

Un comentario delimitado comienza con una barra inclinada y un asterisco `/*` y termina con lo contrario `*/`, como en el siguiente ejemplo:

```js
/*
	This is a block comment
	that can span multiple lines
*/
```

## Expresiones

Una expresión es una pieza de código que se evalúa como un valor. Por ejemplo:

```js
2 + 1
```

La expresión anterior devuelve tres.

![[Seccion_3_operadores_aritmeticos_1.PNG]]
## Palabras clave y palabras reservadas

**JavaScript** define una lista de palabras clave reservadas que tiene usos específicos. Por lo tanto, no puede usar las palabras clave reservadas como identificadores o nombres de propiedad por reglas.

La siguiente tabla muestra las palabras reservadas de **JavaScript** definidas en **ECMA-262**:

Además de las palabras clave reservadas, ECMA-252 tan bien define una lista de futuras palabras reservadas que no se puede usar como identificadores o nombres de propiedad:

![[reserves words.png]]

# Variables

## Declarar una variable

Para declarar una variable, utilice la palabra `var` seguido del nombre de la variable de la siguiente manera:

```js
var message;
```

Un nombre de variable puede ser cualquier identificador valido. Por defecto, la variable `message` tiene un valor especial `undefined` si no ha asignado un valor.

Los nombres de variables siguen estas reglas:

- Los nombres de las variables distinguen entre mayúsculas y minúsculas. Esto significa que las variables `message` y `Message` son variables diferentes.
- Los nombres de variables solo pueden contener letras, números, guiones bajos o signos de dólar y no pueden contener espacios. Además, los nombres de las variables deben comenzar con una letra, un guion bajo `(_)` o un signo de dólar `($)` .
- Los nombres de variables no puéden usar las palabras reservadas.

Por convención, los nombres de variables usan mayúsculas y minúsculas como `message`, `yourAge` y `myName`.

**JavaScript** es un lenguaje de tipado dinámico. Esto significa que no necesita especificar el tipo de variable en la declaración como otros lenguajes estáticos como Java o C#.

A partir de **ES6**, puede usar la palabra `let` para declara una variable como es:

```js
let message;
```

Es una buena practica usar la palabra `let` para declarar una variable. Mas adelante aprenderemos las diferencias entre las palabras clave `let` y `var`. Y no debes de preocuparte de eso por ahora.

## Inicializar una variable

Una vez que haya declarado una variable, puede inicializarla con un valor. Para inicializar una variable, especifique el nombre de la variable, seguido de un signo igual `(=)` y su valor después.

Por ejemplo, lo siguiente declara la variable `message` y la inicializa con una cadena literal `"Hello"`:

```js
let message;
message = "Hello";
```

Para delcara e inicializar una variable al mismo tiempo, utilice la siguiente sintaxis:

```js
let variableName = value;
```

Por ejemplo, la siguente declaracion declara la variable `message` y la inicializa con la cadena literal `"Hello"` :

```js
let message = "Hello";
```

**JavaScript** le permite declarar dos o mas variables usando una sola declaracion. Para separar dos declaraciones de variables, usa una coma `(,)` como esta:

```js
let message = "Hello",
	counter = 100;
```

Dado que **JavaScript** es un lemguaje de tipo dinamico, puede asignar un valor de un tipo diferente a una variable. Anque, no es recomendable. Por ejemplo:

```js
let message = 'Hello';
message = 100;
```

## Cambiar una variable 

Una vez que inicializa una variable, puede cambiar su valor asigandole un valor diferente. Por ejemplo:

```js
let message = "Hello";
message = 'Bye';
```

## Variables no definidas vs no declaradas

Es importante distinguir entre variables no definidas y no declaradas.

Una variable indefinida es una variable que se ha declarado pero que no se ha inicializado con un valor. Por ejemplo:

```js
let message;
console.log(message); // undefined
```

En este ejemplo, la variable `message` se declara pero no se inicializa. Por lo tanto, la variable `message` no esta definida.

Por el contrario, una *variable no declarada* es una variable que no ha sido declarada. Por ejemplo:

```js
console.log(counter);
```

Error: la variable counter no ha sido declarada. Por lo tanto, acceder a el provoca un archivo `ReferenceError`.

### Constantes

Una constante tiene un valor que no cambia. Para declarar una constante, usa la palabra clave `const`. Al definir una constante, debe inicializarla con un valor. Por ejemplo:

```js
const workday = 5;
```

Una vez definida una constante, no puede cambiar su valor.

El siguiente ejemplo intenta cambiar el valor de la constante de jornada laboral a 4 y provoca un error:

```js
workday = 2;
```

Error: Mas adelante aprenderás que la palabra clave `const` en realidad define una referencia de solo lectura a un valor en el titulo de constantes.

# Tipos de datos

**JavaScript** tiene los tipos de datos primitivos:

- null
- undefined
- boolean
- number
- string
- symbol - disponible desde ES2015
- bigint - disponible a partir de ES2020

y un tipo de datos complejo `object`.

![[JavaScript-data-types.svg]]


**JavaScript** es un lenguaje de tipado dinámico. Significa que una variable no se asocia con un tipo de dato en si. En otras palabras, una variable puede contener un valor de diferentes tipos. Por ejemplo:

```js
let counter = 120; // counter is a number
counter = false;   // counter is now a boolean
counter = "foo";   // counter is now a string
```

Para obtener el tipo actual del valor que almacena la variable, utiliza el operador `typeof`: 

```js
let counter = 120;
console.log(typeof(counter)); // "number"

counter = false; 
console.log(typeof(counter)); // "boolean"

counter = "Hi";
console.log(typeof(counter)); // "string"
```

Salida 
```js
"number"
"boolean"
"string"
```

## El tipo undefined

El tipo `undefined` es un tipo primitivo que tiene un solo valor `undefined`. Por defecto, cuando se declara una variable pero no se inicializa, se le asigna el valor de `undefined`.

Considere el siguiente ejemplo:

```js
let counter;
console.log(couneter);       //undefined
console.log(typeof counter); //undefined
```

En este ejemplo, el `counter` es una variable. Como `counter` no ha sido inicializado, se le asigna el valor `undefined`. El tipo de `counter` también es `undefined`.

Es importante tener en cuenta que el operador `typeof` tambien regresa `undefined` cuando llamas en una variable que no ha sido declarada:

```js
console.log(typeof undeclaredVar); // undefined
```

## El tipo null

El tipo `null` es el segundo tipo de datos primitivos que también tiene un solo valor `null`. Por ejemplo:

```js
let obj = null;
console.log(typeof obj); // object
```

	El tipo de objeto de retorno null es un error
	conocido en JS. Se propuso una propuesta para
	solucionar esto, pero se rechazo. La razon fue que 
	la solucion romperia muchos sitios existentes.

**JavaScript** define que `null` es igual a `undefined`:

```js
console.log(null == undefined); // true
```

## El tipo de numero

**JavaScript** usa el tipo `number` para representar tanto numeros enteros como de punto flotante.

La siguiente declaración declara una variable e inicializa su valor con un numero entero:

```js
let num = 100;
```

Para representar un numero de punto flotante, incluir un punto decimal seguido de al menos un numero. Por ejemplo:

```js
let price = 12.5;
let discount = 0.05;
```

Tenga en cuenta que **JavaScript** convierte automáticamente un numero de punto flotante en un numero entero si el numero parece ser numero entero.

La razon es que **JavaScript** siempre quiere usar menos memoria ya que un valor de punto flotante usa el doble de memeoria que un valor entero. Por ejemplo:

```js
let price = 200.00; // interoreted as an integer 200
```

Para obtener el rango del tipo de numero, usa `Number.MIN_VALUE` y `Number.MAX_VALUE`. Por ejemplo:

```js
console.log(Number.MAX_VALUE); //1.7976931348623155557e+308
console.log(Number.MIN_VALUE); // 5e-324
```

Ademas, puede usar `Infinity` y `-Infinity` para representarr el numero infinito. Por ejemplo:

```js
console.log(Number.MAX_VALUE + Number.MAX_VALUE); 
// Infinity
console.log(-Number.MAX_VALUE - Number.MAX_VALUE); 
// -Infinity
```

## NaN

*NaN* significa No es un numero. Es un valor numérico especial que indica un numero invalido. Por ejemplo, la división de una cadena por un numero devuelve `NaN` :

```js
console.log('a'/2); // NaN
```

`NaN` tiene dos caracteristicas especiales:
- Cualquier operacion con `NaN` devuelve `NaN`.
- El `NaN` no es igual a ningun valor, incluido el mismo.

Aqui hay unos ejemplos:

```js
console.log(NaN/2); // NaN
console.log(NaN == NaN); // false
```

## El tipo de cadena

En **JavaScript**, una cadena es una secuencia de cero o mas caracteres. Un literal de cadena comienza y termina con una comilla simple `'` o una comilla doble `"` .

Una cadena que comienza con comillas dobles debe terminar con comillas dobles. Del mismo modo, una cadena que comienza con una comilla simple también debe terminar con una comilla simple:

```js
let greeting = 'Hi';
let message = "Bye";
```

Si desea usar comillas simples o dobles en una cadena literal, debe usar la barra invertida.

```js
let message = 'I\'m also a valid string';
```

Las cadenas de **JavaScript** son inmutables. Esto significa que no se puede modificar una vez creada. Sin embargo, puede crear una nueva cadena a partir de una cadena existente. Por ejemplo:

```js
let str = 'JavaScript';
str = str + ' String';
```

En este ejemplo:
- Primero, declare la variabel `str` e inicialice en una cadena de `JavaScript`.
- En segundo lugar, use el operador `+` para combinar `JavaScript` con `String` para hacer su valor como  `"JavaScript String"` .

Detras de escena, el motor de **JavaScript** crea una nueva cadena que contiene la nueva cadena ``JavaScritp String`` y destruye la cadena original.

El siguiente ejemplo intenta cambiar el primer caracter de la cadena **JavaScript** :

```js
let s = 'JavaScript';
s[0] = 'j';
console.log(s);
```

La salida es: `JavaScript`
Pero no: `javaScript`

## El tipo boolean

El tipo de dato `boolean` tiene dos valores los cuales son `true` y `false`. El siguiente ejemplo declara dos variables que contiene los valores booleanos.

```js
let inProgress = true;
let completed = false;

console.log(typeof completed); // boolean
```

**JavaScript** permite convertir valores de otros tipos en valore booleano tomando el valor de `true` o `false`.

Para convertir un valor de otro tipo de datos en un valor booleano, utilice la función Boolean(). La siguiente tabla muestra las reglas de conversión:


|Tipo   | true  |  false |
|---|---|---|
| string  | cadena no vacia  | cadena vacia  |
|  number | numero distinto de cero e infinito  | 0, NaN  |
| object  | Objeto no null  | null  |
| undefined  |   |  undefined |

Por ejemplo:

```js
console.log(Boolean('Hi'));// true
console.log(Boolean(''));  // false

console.log(Boolean(20));  // true
console.log(Boolean(Infinity));  // true
console.log(Boolean(0));  // false

console.log(Boolean({foo: 100}));  // true on non-empty object
console.log(Boolean(null));// false
```

## El tipo de símbolo

**JavaScript** agrego un tipo primitivo en ES6: el `symbol`. A diferencia de otros tipos primitivos, el tipo `symbol` no tiene una forma literal.

Para crear un símbolo, llama a la función `Symbol()` de la siguiente manera:

```js
let s1 = Symbol();
```

La función `Symbol` crea un nuevo valor único cada vez que lo llama.

```js
console.log(Symbol() == Symbol()); // false
```

Tenga en cuenta que aprenderá mas sombre los símbolos mas adelante.

## El tipo bigint

El tipo `bigint` representa los números enteros que son mayores que 2 a la 53 - 1. Para formar un numero literal `bigint`, agregamos una letra `n` al final del numero:

```js
let pageView = 9007199254740991n;
console.log(typeof(pageView)); //bigint
```

## Tipo de dato object

En **JavaScript**, un objecto es una colección de propiedades, donde cada propiedad se define como un par clave-valor.

El siguiente ejemplo define un objeto vacío utilizando la sintaxis literal de objeto:

```js
let emptyObject = {};
```

El siguiente ejemplo define un objeto vacío utilizando la sintaxis literal de objeto:

```js
let emptyObject = {};
```

El siguiente ejemplo define el objeto `person` con dos propiedades:  `firstName` y `lastName`.

```js
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
```

Un nombre de propiedad de un objeto puede ser cualquier cadena. Puede usar comillas alrededor del nombre de la propiedad si no es un identificador valido.

Por ejemplo, si el objeto persona tiene una propiedad `first-name`, debe colocar entre comillas como `"first-name"`.

Una propiedad de un objeto puede contener un objeto. Por ejemplo:

```js
let contact = {
	firstName: 'John',
	lastName: 'Doe',
	email: 'john.doe@example.com',
	phone: '(408)-55-9999',
	address: {
		building: '40000',
		street: 'North 1st street',
		city: 'San Jose',
		state: 'CA',
		contry: 'USA'
	}
}
```

El objeto `contact` tiene las propiedades `firstName, lastName, email, phone, address`.

La propiedad `address` y contiene un objeto que tiene las propiedades `building, street, city, state y country`.

Para acceder a la propiedad de un objeto, puede utilizar 
- La notación de punto `(.)`.
- La notación tipo matriz `([])`.

El siguiente ejemplo usa la notación de punto `(.)` para acceder a las propiedades.

```js
console.log(contact.firstName);
console.log(contact.lastName);
```

Si hace referencia a una propiedad que no existe, obtendra un valor `undefined`. Por ejemplo: 

```js
console.log(contact.age); // undefined
```

El siguiente ejemplo utiliza la notación tipo matriz para acceder a las propiedades `email` y `phone` del objeto `contact`.

```js
console.log(contact['phone']); // '(408)-555-9999'
console.log(contact['email']); // 'john.doe@example.com'
```
# Números

## Introducción a los números en JS

**JavaScript** usa el tipo `number` para representar tanto valores enteros como de punto flotante. Técnicamente, el tipo de dato `number` utiliza el formato de IEEE-754.

ES2020 introdujo un nuevo tipo primitivo que representa `bigint` números grandes con valores mayores que 2 a la 53-1.

Para admitir varios tipos de números, **JavaScript** utiliza diferentes formatos de literales numéricos.

## Números enteros

A continuación se muestra cómo declarar una variable que contiene un entero decimal:

```js
let counter = 100;
```

Los números enteros se pueden representar en los siguientes formatos:

-   octales (base 8)
-   Hexadecimal (basado en 16)

Cuando usa números octales y hexadecimales en operaciones aritméticas, JavaScript los trata como números decimales.

### Números octales

Un número literal octal comienza con el dígito cero (0) seguido de una secuencia de dígitos octales (números del 0 al 7). Por ejemplo:

```js
let num = 071;
console.log(num); // 57
```

Si un número octal contiene un número que no está en el rango de 0 a 7, el motor de JavaScript ignora el 0 y trata el número como un decimal. Por ejemplo:

```js
let num = 080;
console.log(num); // 80
```

Este comportamiento implícito podría causar problemas. Por lo tanto, ES6 introdujo un nuevo literal octal que comienza con `0o`seguido de una secuencia de dígitos octales (del 0 al 7). Por ejemplo:

```js
let num = 0o71;
console.log(num); // 57
```

Si escribe un número no válido después de `0o`, JavaScript generará un error de sintaxis.

```js
let num = 0o80;
console.log(num); // Invalid or unexpected token
```

### Números hexadecimales

Los números hexadecimales comienzan con ``0x`` o ``0X`` seguidos de cualquier número de dígitos hexadecimales (del 0 al 9 y de la a a la f). Por ejemplo:

```js
let num = 0x1a;
console.log(num); // 26
```

## Números de punto flotante

Para definir un numero literal de punto flotante, incluye un punto decimal y al menos un numero después de eso. Por ejemplo:

```js
let price = 9.99;
let tax = 0.08;
let discount = .05; // valid but not recommeded
```

Cuando tienes un numero muy grande, puedes usar la notación electrónica. La notación indica que un numero debe multiplicarse por 10 elevado a una potencia dada. Por ejemplo:

```js
let amount = 3.14e7;
console.log(amount); // 31400000
```

La notacion `3.14e7` significa que toma `3.14` y multiplica por `10` a la `7`.

Del mismo modo, puede usar la notacion `E` para representar un numero muy pequeño. Por ejemplo:

```js
let amount = 5e-7; 
console.log(amount); // 0.000005
```

## Enteros grandes

**JavaScript** introdujo el tipo `bigint` a partir de ES2022. El tipo `bigint` almacena números enteros cuyos valores son mayores que 2 a la 53-1.

Un literal entero grande tiene el carácter `n` al final de un literal entero como este:

```js
let pageView = 9007199254740991n;
```
# Separador numérico

## Introduccion al separador numerico de Js

El separador numérico le permite crear una separación visual entre grupos de dígitos utilizando guiones bajos `(_)` como separadores.

Por ejemplo, el siguiente número es muy difícil de leer, especialmente cuando contiene repeticiones de dígitos largos:

```js
const budget = 1000000000;
```

¿Son mil millones o cien millones?

El separador numérico corrige este problema de legibilidad de la siguiente manera:

```js
const budget = 1_000_000_000;
```

Como puede ver, el número ahora es muy fácil de interpretar.

JavaScript le permite usar separadores numéricos tanto para números enteros como de punto fltante. Por ejemplo:

```js
let amount = 120_201_123.05; // 120201123.05
let expense = 123_450; // 123450
let fee = 12345_00; // 1234500
```
# Tipo booleano

## Introducción al tipo booleano

El tipo primitivo `boolean` tiene dos valores literales: `true` y `false`.

El siguiente ejemplo declara dos variables e inicializa sus valores en `true` y `false`:

```js
let completed = true;
let running   = false;
```

Los valores literales booleanos distinguen entre mayúsculas y minúsculas. Esto significa que `True` y `False`.

**JavaScript** permite convertir los valores de otros tipos en valores booleanos. Para converitir un valor no booleano en un valor booleano, utilice la funcion `Boolean()`. Por ejemplo:

```js
let error = 'An error occurred';
let hasError = Boolean(error);

console.log(hasError); // true
```

Si cambia el valor de la variable `error` a una cadena vacía `("")`, no vera nada en la salida porque la declaración `if` lo evalúa como `false`:

```js
let error = '';
if (error) {
	console.log(error);
}
```


# String

## Introducción a String

Las cadenas de **JavaScript** son valores primitivos. Además, las cadenas son inmutables. Significa que si modifica una cadena, siempre obtendrá una nueva cadena. La cadena original no cambia.

Para crear cadenas literales, utilice comillas simples `(')` o comillas dobles `(")` como esta:

```js
let str = 'Hi';
let greeting = "Hello";
```

**ES6** introdujo *templates literals* que le permiten definir una cadena de *backtick* 

```js
let name = `John`;
```

Además, puede colocar las variables y expresiones dentro de un literal de plantilla. **JavaScript** reemplazará las variables con su valor en la cadena. Esto se llama interpolación de cadenas. Por ejemplo:

```js
let name = 'John';
let message = `Hi, I'm ${name}.`;

console.log(message);
```

## Obtener la longitud de la cadena

La propiedad `length` devuelve la longitud de una cadena:

```js
let str = "Good Moring!";
console.log(str.length); // 13
```

## Convertir valores a cadena

Para convertir un valor que no es una cadena en una cadena, utilice uno de los siguientes:
- String(n)
- + n
- n.toString()

Tenga en cuenta que el método `toString()` no funciona para `undefined` y `null`.

Cunado convierte una cadena en un valor booleano, no puede volver a convertirla. Por ejemplo:

```js
let status = false;
let str = status.toString(); // "false"
let back = Boolean(str); // true
```

En este ejemplo:

- Primero, declare la variable `status` e inicialícela con el valor de `false`.
- En segundo lugar, convierta la variable de estado en una cadena utilizando el método `toString()`.
- Tercero, convierta la cadena nuevamente a un valor booleano usando la `Boolean()`función. La función Boolean() convierte la cadena `"false"`en un valor booleano. El resultado es verdadero porque `"false"`es una cadena no vacía.

## Comparando cadenas

Para comparar dos cadenas, utilice los operadores de comparación `>`, `>=`, `<`, `<=` y `==`.

Los operadores de comparación comparan cadenas en función de los valores numéricos de los caracteres. Y puede devolver el orden de las cadenas que es diferente al que se usa en los diccionarios. Por ejemplo:

```js
let result = 'a'<'b';
console.log(result); // true
```

Sin embargo:

```js
let result = 'a' < 'B';
console.log(result); // false
```


# Objetos

## Introducción a los objetos

En **JavaScript**, un objeto es una colección desordenada de pares de **clave - valor**. Cada par de **clave - valor** se le denomina propiedad.

La clave de una propiedad puede ser una cadena. Y el valor de una propiedad puede ser cualquier valor, por ejemplo. una cadena, un numero, una matriz  e incluso una función.

**JavaScript** le proporciona muchas formas de crear un objeto. El mas comúnmente usado es usar la **notación literal de objeto**.

El siguiente ejemplo crea un objeto vacio utilizando la notación literal de objeto:

```js
let empty = {};
```

Para crear un objeto con propiedades, utilice `key:value` dentro de las llaves. Por ejemplo, lo siguiente crea un nuevo objeto `person`.

```js
let person = {
	firstName: 'John',
	lastName: 'Doe'
};
```

El objeto `person` tiene dos propiedades `firstName` y `lastName` con los valores correspondientes `'John'` y `'Doe'`.

Cuando un objeto tiene múltiples propiedades, usa una coma `(,)` para separarlas como en el ejemplo anterior.

## Accediendo a las propiedades

Para acceder a una propiedad de un objeto, utiliza una de dos notaciones: la notación de punto y la notación tipo matriz.

### 1) La notación de punto (.)

A continuación se ilustra como utilizar la notación de puntos para acceder a una propiedad de un objeto:

```js
objectName.propertyName
```

Por ejemplo, para acceder a la propiedad `firstName` del objeto `person`, utiliza la siguiente expresión:

```js
person.firstName
```

Este ejemplo crea un objeto `person` y muestra el nombre y el apellido en la consola:

```js
let person = {
	firstName: 'John',
	lastName: 'Doe'
}

console.log(person.firstName);
console.log(person.lastName);
```

### 2) Notación tipo matriz ([])

A continuación se ilustra como acceder al valor de la propiedad de un objeto a través de la notación tipo matriz:

```js
objectName['proppertyName']
```

Por ejemplo:

```js
let person = {
	firstName: 'John',
	lastName: 'Doe'
};

console.log(person['firstName']);
console.log(person['lastName']);
```

Cunado el nombre de una propiedad contiene espacios, debe colocarlo entre comillas. Por ejemplo, el siguiente objeto `address` tiene como propiedad `building no`.

```js
let address = {
	'building no': 3960,
	street: 'North 1st street',
	state: 'CA',
	contry: 'USA'
}
```

Para acceder a la propiedad  `building no` , debe usar la notacion similar a una matriz :

```js
address['building no'];
```

Si usa la notacion de puntos, obtendra un error:

```js
address.'building no'
```

Error: `SyntaxError` : Unexpected string 

	Tenga en cuenta que no es una buena practica
	utilizar espacios en los nombres de propiedad 
	de un objeto.

La lectura de una propiedad que no existe dara como resultado un archivo `undefined`

```js
console.log(address.district); // undefined
```

## Modificar el valor de una propiedad

Para cambiar el valor de una propiedad, utilice el operador de asignacion *(=)*. Por ejemplo:

```js
let person = {
	firstName: 'John',
	lastName: 'Doe'
};

person.firstName = 'Jane';

console.log(person); 

/* 
	{firstName: 'John', lastName: 'Doe'} 
*/
```

En este ejemplo, combinamos el valor de la propiedad `firstName` del objeto `person` de `John` a `Jane`.

## Agregar una nueva propiedad a un objeto

A diferencia de los objetos en otros lenguajes de programación como JAVA y C#, puede agregar una propiedad a un objeto después de la creación del objeto.

La siguiente declaración agrega la propiedad `age` al objeto `person` y le asigna 25.

```js
person.age = 25;
```

## Eliminar una propiedad de un objeto

Para eliminar una propiedad de un objeto, utiliza el operador `delete`.

```js
delete objectName.propertyName;
```

El siguiente ejemplo elimina la propiedad `age` del objeto `person`:

```js
delete person.age;
```

Si intenta volver a acceder a la propiedad de edad, obtendra un valor `undefined`.

## Comprobar si existe una propiedad

Para comprobar si existe una propiedad en un objeto, utiliza el operador `in`:

```js
propertyName in objectName
```

El operador `in` devuelve `true` si `propertyName` existe en el `objectName`.

El siguiente ejemplo crea un objeto `employes` y usa el operador `in` para verificar si las propiedades existen `ssn` y `employeeId`:

```js
let employee = {
	firstName: 'Peter',
	lastName: 'Doe',
	employeedId: 1
};

console.log('ssn' in employee); // false
console.log('employeeId' in employee); // true
```


# Valores primitivos vs valores por referencia

## Memoria de pila (Stack) y montón (heap) 

Cuando declaramos variables, el motor **JavaScript** les asigna memoria en dos ubicaciones de memoria: *pila* y *montón*.

Los **datos estáticos** son los datos cuyo tamaño se fija en el **momento de la compilación**. Los datos estáticos incluyen: 
- Valores primitivos  (null, undefined, boolean, number, string, symbol, and BigInt)
- Valores de referencia que hacen referencia a objeto

Debido a que los datos estáticos tiene un tamaño que no cambia, el motor de **JavaScript** asigna una cantidad fija de espacio de memoria a los datos estáticos y los almacena en la pila (stack).

Por ejemplo, lo siguiente declara dos variables e inicializa sus valores en una cadena literal y un numero: 

```js
let name = 'John';
let age = 25;
```

Debido a que `name` y `age` son valores primitivos, el motor de **JavaScript** almacena estas variables en la pila (stack) como se muestra en la siguiente imagen:
![[Pasted image 20231022202235.png]]

	Tenga en cuenta que las cadenas son objetos en muchos lenguajes de programación, incluidos Java y C#. Sin embargo, las cadenas son valores primitivos en JavaScript.
 
A diferencia de la pila (stack), **JavaScript** almacena **objetos (y funciones)** en el montón (heap). El motor de **JavaScript** no asigna una cantidad fija de memoria para estos objetos. En cambio, asignara mas espacio según sea necesario. 

El siguiente ejemplo define las variables `name`, `age` y `person`:

```js
let name = 'John';
let age = 25;

let person = {
	name: 'John',
	age: 25,
}
```

Internamente, el motor de **JavaScript** asigna la memoria como se muestra en la siguiente imagen:
![[Pasted image 20231022202518.png]]

En esta imagen, JavaScript asigna memoria en la pila (stack) para las tres variables `name`, `age` y `person`.

El motor de JavaScript crea un nuevo objeto en la memoria del montón (heap). Además, vincula la variable `person` en la memoria de la pila (stack) con el objeto en la memoria del montón.

Por eso decimos que la variable `person` es una referencia que se refiere a un objeto.

## Propiedades dinámicas

Un valor de referencia le permite agregar, cambios o eliminar propiedades en cualquier momneto. Por ejemplo:

```js
let person = {
  name: 'John',
  age: 25,
};

// add the ssn property
person.ssn = '123-45-6789';

// change the name
person.name = 'John Doe';

// delete the age property
delete person.age;


console.log(person);
```

Resultado `{ name: 'John Doe', ssn: '123-45-6789' }`

A diferencia de un valor de referencia, un valor primitivo no puede tener propiedades. Esto significa que no puede agregrar una propiedad a un valor primitivo. 

**JavaScript** le permite agregar una propiedad a un valor primitivo. Sin embargo, no tendra ningun efecto. Por ejemplo:

```js
let name = 'John';
name.alias = 'Knight';

console.log(name.alias); // undefined
```

En este ejemplo, agregamos la propiedad `alias` al valor primitivo `name`. Pero cuando accedemos a las propiedad `alias` a través del valor primitivo `name`, devuelve `undefined` . 

## Copiando valores

Cunado asigna un valor primitivo de una variable a otra, el motor de **JavaScript** crea una copia de ese valor y lo asigna a la variable. Por ejemplo:

```js
let age = 25;
let newAge = age;
```

En este ejemplo:
- Primero, declare una nueva variable `age` e inicia su valor en 25.
- En segundo ligar, declara otra variable `newAge` y le asigne ala variable `age`.

Detrás de escenas, el motor de **JavaScript** crea una copia del valor primitivo `25` y lo asigna a la variable `newAge`.

La siguiente imagen ilustra la memoria de pila después de la asignación:

![[Pasted image 20231105125756.png]]


En la memoria de la pila (stack), `newAge` y `age` son variables separadas. Si cambia el valor de una variable, no afectara a la otra.

Por ejemplo:

```js
let age = 25;
let newAge = age;

newAge = newAge + 1;
console.log(age, newAge);
```
![[Pasted image 20231105130029.png]]

Cunado asigna un *valor de referencia* de una variable a otra, el motor de **JavaScript** crea una referencia para que ambas variables se refieran al mismo objeto en la memoria del montón.
Esto significa que si cambia una variable, afectara a la otra.

```js
let person = {
  name: 'John',
  age: 25,
};

let member = person;

member.age = 26;

console.log(person);
console.log(member);
```

¿Cómo funciona?

Primero, declare una variable `person` e inicialice su valor con un objeto con dos propiedades `name` y `age`.

En segundo lugar, asigne la variable `person` a la variable `member`. En la memoria, ambas variables hacen referencia al mismo objeto, como se muestra en la siguiente imagen:
![[Pasted image 20231105130114.png]]

Tercero, cambie la propiedad `age` a través de la variable `member`:
![[Pasted image 20231105130145.png]]


Dado que ambas variables hacen referencia al mismo objeto `person` y `member`, cambia el objeto a través de la variable `member` también se refleja en la variable `person`.
# Matrices

## Introducción a las matrices 

En **JavaScript**, una matriz es una **lista ordenada** de valores. Cada valor se denomina elemento especificado por un índice:

![[Pasted image 20231105130324.png]]

Una matriz en **JavaScript** tiene las siguientes características:
- Primero, una matriz puede contender valores de tipo mistos. Por ejemplo, puede tener una matriz que almacene elementos con los tipos numerico, cadena, booleano y null.
- En segundo lugar, el tamaño de una matriz es dinámico y de crecimiento automático. En otras palabras, no necesita especificar el tamaño de la matriz por adelantado. 

## Creacion de matices

**JavaScript** le proporciona dos formas de crear una matriz. El primero es usar el constructor `Array` de la siguiente manera:

```js
let scores = new Array();
```

La matriz `scores` esta vacia, lo que contiene elementos.

Si conoce la cantidad de elementos que contendra la matriz, puede crear una matriz con un tamaño inicial como se muestra en el siguiente ejemplo:

```js
let scores = Array(10);
```

Para crear una matriz e inicializar con algunos elementos, pasa los elementos como una lista separada por comas al constructor `Array()`.

Por ejemplo, lo siguiente crea la matriz `scores` que tiene cinco elementos.

```js
let scores = new Array(9,10,8,7,6);
```

📝**Nota:** Tenga en cuenta que si utiliza el constructor *Array()* para crear una matriz y le pasa un numero, está creando una matriz con un tamaño inicial. 

Sin embargo, cuando pasas un valor de otro tipo, como una cadena, al constructor *Array()*, creas una matriz con un elemento de ese valor. 

Por ejemplo:

```js
let athletes = new Array(3);
let scores = new Array(1,2,3);
let signs = new Array('Red');
```

JS le permite omitir el operador *new* cuando usa el constructor **Array()**.

Por ejemplo:

```js
let artists = Array();
```

En la practica, rara vez utilizaras el constructor *Array()* para crear una matriz.

La forma preferida de crear una matriz es usar la notación literal de matriz:

```js
let arrayName = [element1, element2, element3, ...];
```

La forma literal de matriz usa los corchetes `[]` para envolver una lista de elementos separados por comas.

El siguiente ejemplo crea la matriz `colors` que contiene elementos de cadena:

```js
let colors = ['red','green','blue'];
```

Para crear una matriz vacía, usa corchetes sin especificar ningún elemento como este:

```js
let emptyArry = [];
```

## Acceso a elementos

Las matrices de **JavaScript** están **indexadas** en base cero, En otras palabras, el primer elemento de una matriz comienza en el índice 0, el segundo elemento comienza en el índice 1 y así sucesivamente.

Para acceder a un elemento en una matriz, especifica un índice ente corchetes `[]`:

```js
arrayName[index]
```

A continuación se muestra como acceder a los elementos del arreglo `mountatins`:

```js
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];

console.log(mountains[0]); // 'Everest'
console.log(mountains[1]); // 'Fuji'
console.log(mountains[2]); // 'Nanga Parbat'
```

Para cambiar el valor de un elemento, asigna ese valor al elemento de esta manera:

```js
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
mountains[2] = 'K2';

console.log(mountains); // [ 'Everest', 'Fuji', 'K2' ]
```

## Obtener el tamaño de la matriz

Normalmente, la propiedad `length` de una matriz devuelve el numero de elementos. El siguiente ejemplo muestra como usar la propiedad `length`.

```js
let mountains = ['Everest', 'Fuji', 'Nanga Parbat'];
console.log(mountains.length); // 3
```

## Operaciones básicas en arreglos

A continuación se explica algunas operaciones básicas en arreglos. Y aprenderá operaciones avanzadas como `map()`,`filter()`, y `reduce()`.

### Agregar un elmento al final de una matriz

Para agregar un elemento al final de una matriz, utiliza el metodo `push()`:

```js
let seas = ['Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea'];

seas.push('Red Sea');

console.log(seas); 
```

Resultado: `[ 'Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea', 'Red Sea' ]`

### Agregar un elemento al comienzo de una matriz

Para agregar un elemento al comienzo de una matriz, utiliza el metodo `unshift()`:

```js
let seas = ['Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea'];

seas.unshift('Red Sea');

console.log(seas);
```

Resultado: `[ 'Red Sea', 'Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea' ]`

### Eliminar un elemento del final de una matriz

Para eliminar un elemento del final de una matriz, utiliza el método `pop()`.

```js
let seas = ['Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea'];

const lastElement = seas.pop();

console.log(lastElement); // Baltic Sea
```

### Eliminar un elemento del comienzo de una matriz

Para eliminar un elemento del comienzo de una matriz, utiliza el metodo `shift()` : 

```js
let seas = ['Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea'];

const firstElement = seas.shift();

console.log(firstElement); // Black Sea
```

### Encontrar un indice de un elemento en la matriz

Para encontrar el indice de un elemento, utiliza el metodo `indexOf()` :
```js
let seas = ['Black Sea', 'Caribbean Sea', 'North Sea', 'Baltic Sea'];

let index = seas.indexOf('North Sea');

console.log(index); // 2
```

### Comprobar si un valor es una matriz 

Para verficar si un valor es una matriz, usa el metodo `Array.isArray()` :


```js
console.log(Array.isArray(seas)); // true
```

	# Operadores aritméticos

## Operadores aritméticos
![[Seccion_3_operadores_aritmeticos_1.PNG]]
## Uso de operadores aritméticos

Si un valor es un objeto, el motor de **Js** llama al método `valueOf()` del objeto para obtener el valor para el calculo. Por ejemplo:

```js
let energy = {
  valueOf() {
    return 100;
  },
};

let currentEnergy = energy - 10;
console.log(currentEnergy);

currentEnergy = energy + 100;
console.log(currentEnergy);

currentEnergy = energy / 2;
console.log(currentEnergy);

currentEnergy = energy * 1.5;
console.log(currentEnergy);

```


# Operador de residuo 

## Operador %

**JavaScript** usa el `%` para representar el operador resto. El operador de resto devuelve el resto que queda cuando un valor se divide por otro valor.

Esta es la sintaxis del operador resto: `dividend % divisor`

A continuación se muestra la ecuación para el residuo:

`dividend = divisor * quotient + remainder`
`where |remainder| < |divisor|`

En esta ecuación, `dividend`, `divisor`, `quotient` y `remainder` son todos números enteros. El signo de `remainder` es el mismo que el signo de `dividend` .

El signo de `remainder` es el mismo que el signo de `dividend`.

## Operador de residuo vs modulo

En **JavaScript**, el operador de residuo `(%)` no es el operador de modulo.

Si ha estado trabajando con **Python**, puede encontrar `%` que representa el operador de modulo en este idioma. Sin embargo, no es el caso en **JavaScript**.

Para obtener un modulo en **JavaScript**, utiliza las siguientes expresiones:

```js
((dividend % divisor) + divisor) % divisor
```

o envuélvelo en una función:

```js
const mod = (dividend, divisor) =>  ((dividend % divisor) + divisor) % divisor;
```

```js
const dividendo = 17; const divisor = 5; 
// Cálculo del residuo positivo 
const residuoPositivo = ((dividendo % divisor) + divisor) % divisor; 
// Imprimir el resultado 
console.log(`El residuo positivo de ${dividendo} dividido por ${divisor} es: ${residuoPositivo}`);
```

El residuo positivo de 17 dividido por 5 es: 2

Si la división y el divisor tienen el mismo signo, los operadores de resto y modulo devuelven el mismo resultado. De lo contrario, devuelven resultados diferentes.

Por ejemplo:

```js
const mod = (dividend, divisor) => ((dividend % divisor) + divisor) % divisor;

// dividen and divisor have the same sign
console.log('remainder:', 5 % 3); // 2
console.log('modulo:', mod(5, 3)); // 2

// dividen and divisor have the different signs
console.log('remainder:', -5 % 3); // -2
console.log('modulo:', mod(-5, 3)); // 1
/*
Resultados:
	- remainder: 2
	- modulo: 2
	- remainder: -2
	- modulo: 1
*/
```

# Operadores de asignación


![[Seccion_3_operadores_aritmeticos_2.PNG]]
## Encadenamiento de operaciones de asignación 

Si desea asignar un solo valor a varias variables, puede encadenar los operadores de asignación. Por ejemplo:

```js
let a = 10, b = 20, c = 30;
a = b = c; // all variables are 30
```

En este ejemplo, **JavaScript** evalúa de derecha a izquierda. Por lo tanto, hace lo siguiente:

```js
let a = 10, b = 20, c = 30;

b = c; // b is 30
a = b; // a is also 30 
```

# Operadores de incremento

## Operadores de incremento

Estos operadores trabajan en un valor. La siguiente tabla muestra los operadores unarios y sus significado:

![[Seccion_3_operadores_aritmeticos_3.PNG]]

# Operadores de comparación

## Operadores de comparación

Para comparar dos valores, utiliza un operador de comparación. La siguiente tabla muestra los operadores de comparación de **JavaScript**.

![[Seccion_3_operadores_aritmeticos_4.PNG]]
# Operadores lógicos

## Operadores Lógicos

Los operadores lógicos son importantes porque te permiten comparar variables y hacer algo basado en el resultado de esa comparación.

Por ejemplo, si el resultado de la comparacion es `true`, puede ejecutar un bloque de codigo: si es `false`, puede ejecutar otro bloque de codigo.

**JavaScript** proporciona tres operadores lógicos:
- ! (No lógico)
- || (OR lógico)
- && (AND lógico)

## El operador lógico NOT(!)

**JavaScript** usa un signo de exclamación `!` para representar el operador lógico `NOT`. El operador `!` se puede aplicar a un solo valor de cualquier tipo, no solo a un valor booleano.

Cunado aplica el operador `!` a un valor booleano, `!` devuelve `true` si el valor es `false` y viceversa.
Por ejemplo:

```js
let eligible = false,
    required = true;

console.log(!eligible); // true
console.log(!required); // false
```

Lo siguiente demuestra los resultados del operador logico `!` cuando se aplica a un valor no booleano:

```js
console.log(!undefined); // true
console.log(!null); // true
console.log(!20); //false
console.log(!0); //true
console.log(!NaN); //true
console.log(!{}); // false
console.log(!''); //true
console.log(!'OK'); //false
console.log(!false); //true
console.log(!true); //false
```

## Operador lógico AND (&&)

**JavaScript** usa el doble apersonad `(&&)` para representar el operador `AND`. La siguiente expresión utiliza el operador  `&&`:

```js
let result = a && b;
```

Si `a` se puede convertir a `true`, el operador `&&` devuelve el `b` ; de lo contrario, devuelve el `a`. De hecho, esta regla se aplica a todos los valores booleanos.

La siguiente tabla de verdad ilustra el resultado del operador `&&` cuando se aplica a dos valores booleanos:

![[Pasted image 20231105133216.png]]


El resultado del operador `&&` es verdadero solo si ambos valores son `true`, de lo contrario, es `false`. Por ejemplo:

```js
let eligible = false,
    required = true;

console.log(eligible && required); // false
```

## El operador lógico OR (||)

**JavaScript** usa este operador `||` para representar el operador logico `OR`. Puede aplicar el operador `||` a dos valores de cualquier tipo:

```js
let result = a || b;
```

Si  `a` se puede convertir a  `true`, devuelve  `a`; de lo contrario, vuelve  `b`. Esta regla también se aplica a los valores booleanos.

La siguiente tabla de verdad ilustra el resultado del `||` operador basado en el valor de los operandos:

![[Seccion_3_operadores_aritmeticos_6.PNG]]
## Precedencia de operadores lógicos

Cuando mezcla operadores lógicos en una expresión, el motor de **JavaScript** evalúa los operadores según un orden especifico. Y este orden se llama `precedencia de operadores`.

En otras palabras, la precedencia de operadores es el orden de evaluación de los operadores lógicos en una expresión.

La precedencia del operador lógico es en el siguiente orden de mayor a menor:
- Not lógico (!)
- AND lógico (&&)
- OR lógico (||)

# Operadores de asignación lógica

## ES2021 

ES2021 presenta tres operadores de asignación lógica que incluyen:
- Operador de asignación OR lógico `(||=)`
- Operador de asignación AND lógico `(&&=)`
- Operador de asignación **coalescente nulo** `(??=)`

La siguiente tabla muestra el equivalente del operador de asignaciones lógicas:

![[Seccion_3_operadores_aritmeticos_7.PNG]]
## El operador de asignación OR

El operador de asignación Or lógico `(||=)` acepta dos operandos y asigna el operando derecho al operando izquierdo si el operador izquierdo es **falso**: `x ||= y` .

En esta sintaxis, el operador `||=` solo asigna si es falso. Por ejemplo: `yxx`

```js
let title; // false
title ||= 'untitled';

console.log(title); // untitled
```

En este ejemplo, la variable `title` es `undefined`, por lo tanto, es falso. Dado que el `title` es falso, el operador `||=` asigna el `untitled` a `title`. La salida muestra el `untitled` como se esperaba. 

```js
let title = 'JavaScript Awesome'; // true
title ||= 'untitled';

console.log(title); // 'JavaScript Awesome'
```

En este ejemplo, el `title` es `'JavaScript Awesome'`por lo que es **true**. Por lo tanto, el operador de asignación OR lógico ( `||=`) no asigna la cadena `'untitled'`  a la variable `title`.

Al igual que el operador lógico OR, la asignación lógica OR también provoca cortocircuitos. Significa que el operador de asignación OR lógico solo realiza una asignación cuando `x` es falso.

El siguiente ejemplo utiliza el operador de asignación lógica para mostrar un mensaje predeterminado si el elemento del resultado de la búsqueda está vacío:

```js
document.querySelector('.search-result').textContent ||= 'Sorry! No result found';
```

## El operador de asignacion AND

La lógica del operador de asignación `AND` solo se asigna el valor de `y` a `x` si solo si `x` es `true` . `x &&= y;`

El operador de asignación AND también genera cortocircuitos. Esto significa que:

```js
x &&= y;
// es equivalente a 
x && (x = y);
```

El siguiente ejemplo utiliza el operador de asignacion lofica `AND` para cambiar el apellido de un objeto `person` si el apellido es verdadero.

```js
let person = {
	firstName: 'Bryan',
	lastName: 'Aguirre',
};

person.lastName &&= 'Tudon';

console.log(person); // {firstName: 'Jane', lastName: 'Smith'}
```

## El operador de asignación nullish coalescing

El operador de *nullish coalescing* el valor de `y` solo se asigna a `x` si `x` es `null` or `undefined` : `x ??= y;`

Es equivalente a la siguiente declaración que usa el operador
`x ?? (x = y);`

El siguiente ejemplo utiliza el operador de asignación de fusión null para agregar una propiedad faltante a un objeto:

```js
let user = {
	userName: 'Bryan'
}

user.nickName ??= 'bat-e404'

console.log(user.nickName);
```

# Operador Nullish Coalescing

**ES2020** introdujo el operador *Nullish Coalescing* indicando por los signos de interrogante doble `(??)`. El operador es un operador lógico que acepta dos calores: `value1 ?? value2` .

El operador devuelve el segundo valor `(value2)` si el primero valor `(value2)` es `null` or ``undefined``.

```js
const result = value1;
if(result === null || result === undefined) {
   result = value2;
}
```

El siguiente ejemplo usa el operador coalescente nulo (`??`) para devolver la cadena `'John'`porque el primer valor es `null`:

```js
const name = null ?? 'John';
console.log(name); // 'John'
```

Y este ejemplo regresa `28` porque el primer valor es `undefined`:

```js
const age = undefined ?? 28;
console.log(age);
```

# Operador exponencial 

Para elevar un numero a la poetencia de un exponente, a menudo usa el metodo estatico `Math.pow()` con la siguiente sintaxis: `Math.pow(base, exponente)` .

Por ejemplo:

```js
let result = Math.pow(2,2);
console.log(result); // 4

result = Math.pow(2,3);
console.log(result); // 8
```

**ECMAScript 2016** proporciono una forma alternativa de obtener una base para la potencia del exponente mediante el uso del operador `(**)` con la siguiente sintaxis: `x**n`.

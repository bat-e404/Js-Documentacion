# Métodos de objeto
## Introducción a los métodos de objetos de JavaScript.

Un objeto es una colección de propiedades o pares clave / valor.
Cuando el valor es una función, la propiedad se convierte en un método. Normalmente, utiliza métodos para describir los comportamientos del objeto.

Por ejemplo, lo siguiente agrega el método `greet` al objeto `person`:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

person.greet = function () {
    console.log('Hello!');
}

person.greet();
```

**Resultado:**
```
Hello!
```

**En este ejemplo:**
- Primero, use una expresión de función para definir una función y asignarla a la propiedad `greet` del objeto `person`
- Luego, llame al método `greet()`.

Además de usar una expresión de función, puedes definir una función y asignarla a un objeto como este:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

function greet() {
    console.log('Hello, World!');
}

person.greet = greet;

person.greet();
```

**En este ejemplo:**
- Primero, defina la función `greet()` como una función regular.
- En segundo lugar, asigne el nombre de la función a la propiedad `greet` del objeto `person`.
- En tercer lugar, llame al método `greet()`.

## Taquigrafía del método de objeto - Object method shorthand

JavaScript le permite definir métodos de un objeto utilizando la sintaxis literal del objeto como se muestra en el siguiente ejemplo:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet: function () {
        console.log('Hello, World!');
    }
};
```

ES6 le proporciona la sintaxis de método concisa que le permite definir un método para un objeto.

```js
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet() {
        console.log('Hello, World!');
    }
};

person.greet();
```

Esta sintaxis parece mucho más limpia y menos detallada.

**El valor this**

Normalmente, los métodos necesitan acceder a otras propiedades del objeto.

Por ejemplo, es posible que desee definir un método que devuelva el nombre completo del objeto persona concatenando el nombre y el apellido.

Dentro de un método, el valor `this` hace referencia al objeto que invoca el método. Por lo tanto, puede acceder a una propiedad utilizando el valor `this` de la siguiente manera:

```js
this.propertyName
```

El siguiente ejemplo utiliza el valor `this` en el `getFullName()`método:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe',
    greet: function () {
        console.log('Hello, World!');
    },
    getFullName: function () {
        return this.firstName + ' ' + this.lastName;
    }
};


console.log(person.getFullName());
```

**Resultado:**
```
'John Doe'
```

# Funciones constructoras

Sintaxis literal de objeto para crear un nuevo objeto.

Por ejemplo, lo siguiente crea un nuevo objeto persona con dos propiedades `firstName` y `lastName`:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
```

En la práctica, a menudo es necesario crear muchos objetos similares al objeto `person`.

Para hacer eso, puede usar una función constructora para definir un tipo personalizado y el operador `new` para crear múltiples objetos a partir de este tipo.

Técnicamente hablando, una función constructora es una **función** normal con la siguiente convención:
- El nombre de una función constructora comienza con una letra mayúscula como `Person`, `Document`, etc.
- Una función constructora debe llamarse sólo con el operador `new`

 🗒️Tenga en cuenta que ES6 introduce la palabra clave `class`  que le permite definir un tipo personalizado. Las clases son simplemente azúcar sintáctico sobre las funciones constructoras con algunas mejoras.


El siguiente ejemplo define una **función constructora** llamada `Person`:

```js
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}
```

En este ejemplo, `Person` es lo mismo que una función normal excepto que su nombre comienza con la letra mayúscula `P`.

Para crear una nueva instancia de `Person`, utiliza el `new`operador:

```js
let person = new Person('John','Doe');
```

Básicamente, el operador `new` hace lo siguiente:
- Crea un nuevo objeto vacío y asígnalo a la variable `this`.
- Asigne los argumentos `'John'` y `'Doe'` a las propiedades `firstName`y `lastName`del objeto.
- Devuelve el valor `this`.

Es funcionalmente equivalente a lo siguiente:

```js
function Person(firstName, lastName) {
    // this = {};

    // add properties to this
    this.firstName = firstName;
    this.lastName = lastName;

    // return this;
}
```

Por lo tanto, la siguiente afirmación:

```js
let person = new Person('John','Doe');
```

... devuelve el mismo resultado que la siguiente declaración:

```js
let person = {
    firstName: 'John',
    lastName: 'Doe'
};
```

Sin embargo, la función constructora `Person` le permite crear varios objetos similares. Por ejemplo:

```js
let person1 = new Person('Jane','Doe')
let person2 = new Person('James','Smith')
```

## Agregar métodos a funciones constructoras de Js

Un objeto puede tener métodos que manipulen sus datos. Para agregar un método a un objeto creado mediante la función constructora, puede usar la palabra clave `this`. Por ejemplo:

```js
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;

    this.getFullName = function () {
        return this.firstName + " " + this.lastName;
    };
}
```

Ahora puedes crear un nuevo objeto `Person` e invocar el método `getFullName()`:

```js
let person = new Person("John", "Doe");
console.log(person.getFullName());
```

**Resultado:**

```
John Doe
```

El problema con la función constructora es que cuando creas varias instancias de `Person`, se duplica `this.getFullName()` en cada instancia, lo que no ahorra memoria.

Para resolver esto, puede utilizar el **prototipo** para que todas las instancias de un tipo personalizado puedan compartir los mismos métodos.

## Regresando de funciones constructoras

Normalmente, una función constructora devuelve implícitamente `this` ese conjunto al objeto recién creado. Pero si tiene una declaración `return`, estas son las reglas:
- Si `return` se llama con un objeto, la función constructora devuelve ese objeto en lugar de `this`.
- Si `return` se llama con un valor distinto de un objeto, se ignora.

## Llamar a una función constructora sin la new 

Técnicamente, puedes llamar a una función constructora como una función normal sin usar la palabra clave `new` como esta:

```js
let person = Person('John','Doe');
```

En este caso, simplemente `Person` se ejecuta como una función normal. Por lo tanto, el interior `this` de la función `Person` no se vincula a la variable `person` sino al **objeto global**.

Si intenta acceder a la propiedad `firstName` o `lastName`, obtendrá un error:

```js
console.log(person.firstName);
```

**Error:**

```js
TypeError: Cannot read property 'firstName' of undefined
```

De manera similar, no puede acceder al `getFullName()`método ya que está vinculado al objeto global.

```js
person.getFullName();
```

**Error:**

```js
TypeError: Cannot read property 'getFullName' of undefined
```

Para evitar que se invoque una función constructora sin la palabra clave `new`, ES6 introdujo la propiedad `new.target`.

Si se llama a una función constructora con la palabra clave `new`, `new.target` devuelve una referencia de la función. De lo contrario, regresa `undefined`.

Lo siguiente agrega una declaración a la función `Person` para mostrarla `new.target` en la consola:

```js
function Person(firstName, lastName) {
    console.log(new.target);

    this.firstName = firstName;
    this.lastName  = lastName;

    this.getFullName = function () {
        return this.firstName + " " + this.lastName;
    };
}
```

Lo siguiente devuelve `undefined` porque la función constructora `Person`  se llama como una función normal:

```js
let person = Person("John", "Doe");
```

**Resultado:**

```js
undefined
```

Sin embargo, lo siguiente devuelve una referencia a la función `Person` porque se llama `new`:

```js
let person = new Person("John", "Doe");
```

**Resultado:**

```js
[Function: Person]
```

Al usar `new.target`, puede obligar a quienes llaman a la función constructora a usar la palabra clave `new`. De lo contrario, puedes arrojar un error como este:

```js
function Person(firstName, lastName) {
    if (!new.target) {
        throw Error("Cannot be called without the new keyword");
    }

    this.firstName = firstName;
    this.lastName = lastName;
}
```

Alternativamente, puedes hacer la sintaxis más flexible creando un nuevo objeto `Person` si los usuarios de la función constructora no usan la palabra clave `new`:

```js
function Person(firstName, lastName) {
    if (!new.target) {
        return new Person(firstName, lastName);
    }

    this.firstName = firstName;
    this.lastName = lastName;
}

let person = Person("John", "Doe");

console.log(person.firstName);
```

Este patrón se usa a menudo en bibliotecas y marcos de **JavaScript** para hacer que la sintaxis sea más flexible.

# Prototipos
## Introducción al prototipo de JavaScript

En JavaScript, los objetos pueden heredar características entre sí mediante **prototipos**. Cada objeto tiene su propia propiedad llamada `prototype`.

Como el mismo `prototype` es también otro objeto, `prototype`tiene el suyo propio `prototype`. Esto crea algo llamado **cadena prototipo**. La cadena de prototipos termina cuando un prototipo tiene su propio prototipo null.

Supongamos que tiene un objeto `person`con una propiedad llamada `name`:

```js
let person = {'name':'John'}
```

Al examinar el objeto `person` en la consola, encontrará que el objeto `person` tiene una propiedad llamada `prototype`indicada por `Prototype`:

![[Pasted image 20240127211339.png]]

El prototipo en sí es un objeto con sus propias propiedades:

![[Pasted image 20240127211439.png]]

Cuando accede a una propiedad de un objeto, si el objeto tiene esa propiedad, devolverá el valor de la propiedad, El siguiente ejemplo accede a la propiedad `name` del objeto `person`.

![[Pasted image 20240127211650.png]]

Devuelve el valor de la propiedad `name` como se esperaba.

Sin embargo, si accede a una propiedad que no existe en un objeto, el motor **JavaScript** buscará en el prototipo del objeto.

Si el motor **JavaScript** no puede encontrar la propiedad en el prototipo del objeto, buscará en el **prototipo del prototipo** hasta que encuentre la propiedad o llegue al final de la cadena del prototipo.

Por ejemplo, puedes llamar al método `toString()` del objeto `person` así:

![[Pasted image 20240127211830.png]]

El método `toString()` devuelve la representación de cadena del objeto `person`. Por defecto, es `[object Object]`lo que no es obvio.

```
Tenga en cuenta que cuando una funcion es un valor de la propiedad de un objeto, se llama método. Por tanto, un método es una propiedad con valor como función.
```

En este ejemplo, cuando llamamos al método `toString()` en el objeto `person`, el motor **JavaScript** lo encuentra en el objeto `person`.

Como el objeto `person` no tiene el método `toString()`, buscará el método `toString()` en el **objeto prototipo** de la persona.

Dado que el prototipo de la persona tiene el `toString()`método, **JavaScript** llama al  prototipo `toString()` del objeto persona.

![[Pasted image 20240127212458.png]]

## Js prototipo illustration

**JavaScript** tiene la función incorporada `Object()`. El operador `typeof`  regresa `'function'` si le pasas la función `Object`. Por ejemplo:

```js
typeof(Object)
```

Resultado:

```js
'function'
```

```
Tenga en cuenta que Object() es una función, no un objeto. Es confuso si es la primera vez que aprende sobre el prototipo de Js.
```

Además, Js proporciona un objeto anónimo al que se puede hacer referencia mediante la propiedad `prototype` de la función `Object()`:

```js
console.log(Object.prototype);
```

![[Pasted image 20240127213105.png]]

El objeto `Object.prototype` tiene algunas propiedades y métodos útiles como `toString()` y `valueOf()`.

También tiene `Object.prototype` una propiedad importante llamada `constructor` que hace referencia a la función `Object()`.

La siguiente declaración confirma que la propiedad `Object.prototype.constructor` hace referencia a la función `Object`:

```js 
console.log(Object.prototype.constructor === Object); // true
```

Supongamos que un círculo representa una función y un cuadrado representa un objeto. La siguiente imagen ilustra la relación entre la función `Object()` y el objeto `Object.prototype`:

![[Pasted image 20240127213415.png]]


Primero, define una `funcion constructora` llamada `Person` de la siguiente manera: 

```js
function Person (name) {
	this.name = name;
}
```

En este ejemplo, la función `Person()` acepta un argumento `name` y lo asigna a la propiedad `name` del objeto `this`.

Detrás de escena, **JavaScript** crea una nueva función `Person()` y un objeto anónimo:

![[Pasted image 20240127213849.png]]

Al igual que la función `Object()`, la función `Person()` tiene una propiedad llamada `prototype` que hace referencia a un **objeto anónimo**. El **objeto anónimo** tiene la propiedad `constructor` que hace referencia a la función `Person()`.

A continuación se muestra la función `Person()` y el objeto anónimo al que hace referencia `Person.prototype`:

```js
console.log(Person);
console.log(Person.prototype);
```

![[Pasted image 20240127214141.png]]

Además, **JavaScript** vincula un objeto `Person.prototype` a otro `Object.prototype` a través de `[[Prototype]]`, lo que se conoce como _**vínculo de prototipo_**.

El **enlace prototipal** se indica `[[Prototype]]` en la siguiente figura:

![[Pasted image 20240127214359.png]]

## Definición de métodos en el objeto prototype de Js

A continuación se define un nuevo método llamado `greet()` en el objeto `Person.prototype`:

```js
Person.prototype.greet = function() {
	return "Hi, I'm" + this.name + "!";
}
```

En este caso, el motor **JavaScript** agrega el método `greet()` al objeto `Person.prototype`:

![[Pasted image 20240127214745.png]]

Lo siguiente crea una nueva instancia de `Person`:

```js
let p1 = new Person('John');
```

Internamente, el motor **JavaScript** crea un nuevo objeto llamado `p1` y vincula el objeto `p1` al objeto `Person.prototype` a través del enlace prototipo:

![[Pasted image 20240127215630.png]]

El vínculo entre `p1`, `Person.prototype` y `Object.protoype` se llama __cadena prototipo__.

Lo siguiente llama al método `greet()` en el objeto `p1`:

```js
let greeting = p1.greet();
console.log(greeting);
```

Como `p1` no tiene el método `greet()`, **JavaScript** sigue el enlace del **prototipo** y lo encuentra en el objeto `Person.prototype`.

Dado que **JavaScript** puede encontrar el método `greet()` en el objeto `Person.prototype`, ejecuta el método `greet()` y devuelve el resultado:

Lo siguiente llama al método `toString()` en el objeto `p1`:

```js
let s = p1.toString();
console.log(s);
```

En este caso, el motor **JavaScript** sigue la cadena del **prototipo** para buscar el método `toString()` en el archivo `Person.prototype`.

Como `Person.prototype` no tiene el método `toString()`, el motor **JavaScript** sube a la cadena del **prototipo** y busca el método `toString()` en el objeto `Object.prototype`.

Dado que JavaScript puede encontrar el método `toString()` en `Object.prototype`, ejecuta el método `toString()`.

![[Pasted image 20240127220831.png]]

Si llama a un método que no existe en el objeto `Person.prototype` y `Object.prototype`, el motor **JavaScript** seguirá la **cadena del prototipo** y arrojará un error si no puede encontrar el método. Por ejemplo:

```js
p1.fly();
```

Debido a que el método `fly()` no existe en ningún objeto de la cadena del prototipo, el motor de **JavaScript** genera el siguiente error:

```
TypeError: p1.fly is not a function
```

Lo siguiente crea otra instancia de cuyo nombre `Person`  la propiedad es `'Jane'`:


```js
let p2 = new Person('Jane');
```

![[Pasted image 20240127221726.png]]

El objeto `p2` tiene las mismas **propiedades** y **métodos** que el objeto `p1`.

En conclusión, cuando define un método en el objeto `prototype`, este método es compartido por todas las instancias.

## Definir métodos en un objeto individual.


# Patrón constructor / prototipo
# Herencia de prototipos
# ¿Qué es esto en Js?
# globalThis
# Propiedades del objeto
# for ... in loop
# Propiedades enumerarles
# Propiedades propias
# Object.values()
# Object.entries()
# Object.assign()
# Object.is()
# Funciones de fábrica
# Desestructuración de objetos
# Operadores de encadenamiento opcional
# Extensiones de sintaxis de literales de objetos
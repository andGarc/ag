+++
title = 'JS Overview'
date = 2023-12-07
draft = false
tags = ['js']
Description = 'Quick Javascript Overview - Reference'
ShowToc = true
+++


## Data Types
- Number
- BigInt
- String
- Boolean
- Symbol
- Undefined
- Null

## Variables
Variables can be defined using `let`, `const`, or `var`.

### `let`
Block-level variables

### `const`
Variables whose values are never intended to change.
The variable is available from the block it is declared.

### `var`
Not block-scoped and are **discouraged** in modern JS code

## Operators
- `+`
- `-`
- `**`
- `/`
- `%`
- `**`
- `==`
- `===`

Numbers can be added to strings and vice versa:
```js
4 + 3 + "5"; // "75"
"3" + 4 + 5; // "345"
// useful to convert strings
```

### Comparision 
#### `==`
Does type coercion if given different types

#### `===`
Does not do type coercion if given different types. **Preferred**.

## Control Structures
### `if` and `else`
``` js
if () {
} else if () {
} else {
}
```

### `while`
```js
do {

} while (true) {
}
```

### `for`
```js
for (let i = 0; i < 5; i++) {
// do something
}
```

#### `for...of`
Iterates over iterables (arrays, etc...)
```js
for (conts value of array) {
// do something with value
}
```

#### `for...in`
Visits enumerable properties of an object
```js
for (const property in object) {
//do somthing with object prooerty
}
```

### `switch`
Based on equality.
Comparison takes palce using the `===` operator.
```js
switch (action) {
	case "draw":
		drawit();
		break;
	case "eat":
		eat();
		break;
	default:
		doNothing();
}
```

### `try..catch`
Handles errors.
```js
try {
	buildMysite();
} catch (e) {
	console.error("Build failed.", e);
}
```

#### `throw`
Errrors can also be thrown.
```js
function myFunction(a){
	if(!a) {
		throw new Error("Error");
	}
}
```

## Objects
Object can be thought as a collection of key-value pairs. 
Similar to dictionaries in Python. 
**Properties can be added, deleted, re-ordered, mutated, or dynamically queried at any time.**
Keys are always strings or symbols.

### Create an object
```js
const obj = {
	name: "Carrot",
	for: "Max",
	details: {
		color: "orange",
		size: 12,
	},
};
```

#### Access properties
Properties can be accessed using dot notation or brackets. 
When using dot notation the key must be a valid identifier. Brackets allow indexing. 

```js
// dot notation
obj.name = "Simon";
const name = obj.name;

// Bracket notation
obj["name"] = "Simon";
const name = obj["Simon"];

// Can use a varibale to define a key
const userName = prompt("what is your key?");
obj["userName"] = prommpt("what is the value?");
```

Properties can be chained together.
```js
obj.details.color;  //orange
```

**Object are alwats references.**

## Arrays
Array are a special type of object in JS. They have one magical property called `lenght`.

### Create array
```js
const a = ["dog", "cat"];
a.length; //3
```

### Grow or Shrink an array
Arrays can grow or shrink
```js
const arr = [1, "foo"]
arr.push({}) // [1, "foo", {}]
```

### Some array methods
#### `map()`
Applies a callback to every array element and returns a new array.
```js
const babies = ["dog", "cat"].map((name => 'baby ${name}'));
// babies = ["baby dog", "baby cat"]
```

## Functions

### Basic function declaration

```js
function add(x, y) {
	const total = x + y;
	return total;
}
```

A function can take 0 or more arguements. The return statement can return a value at any time.
If no return stement is used or an empty return with no value is used, then JS returns `undefined`.

Functions parameters do onot have to be specified when calling a function, but:
- Parameters that are not set will be set to `undefined`
- If you pass more parameters than a funciton expects, the function will ignore the extra parameters 

#### Rest paramter systax
Similar to `**args` in Python.
Parameters are collected into an array.

```js
function avg(...args) {
	let sun = 0;
	for(const item of args) {
		sum += item;
	}
	return sum / args.length.;
}

avg(2, 3, 5); //3.5
```

The rest parameter stores all arguments after where it is declared. 
`function avg(firstValue, ...args)` will store ther first value passed into `firstValue` and the remaining in `args`.

#### Object destruction 
Allows object to be packed and unpacked. 

```js
// use {} braces to decustruct an object
function area({w, h}) {
	return w * h
}

// {} here create an object
console.log(area({w: 3, h: 4}));
```

#### Default parameters
```js
function name(w, h, x=1) {
	return w * h * x
}

name(1, 2); //2 instead of NaN
```

### Anonymous functions
Functions without names.
In practice, anonymous functions are typically used as argument to other functions. They are assigned to a variable that can be used to invoke the function. 

```js
// there is no function name
const avg = function (...args){
	let sum = 0;
	for (const item of args) {
		sum += item;
	}
	return sum/args.length;
};

// function call
avg(1,2)
```

Anonymous functions can also be defined by using arrow function expression.

```js
const avg = (...args) => {
	let sum = 0;
	for (const item of args) {
		sum += item;
	}
	return sum/args.length;
};
```

### Inner functions
Nested functions can share variables in their parent. 

## Classes
Class syntax is similar to Java.
```js
class Person {
	constructor(name) {
		this.name = name;
	}
	sayHello() {
		return 'Hello, I'm ${this.name}.';
	}
}

const p = new Person("Maria");
console.log(p.sayHello());
```

#### Static properties 
Use `static` when declaring. 

#### Private properties
Use `#` when declaring. 

## Asynchronous programming 
JS does not support paralleling, only concurrency. 
There are 3 ways to write asynchronous code:
- Callback-based
- Promise-based
- async/await

```js
//async/await
async function readFile(filename) {
	const content = await fs.readFile(filename);
	console.log(content);
}
```

## Modules
`import` and `export` statements are used to exchange data between modules. 

```js
import { foo } from "./foo.js"

// unexported  variables are local to the module 
const b = 2; 

export const a = 1;
```
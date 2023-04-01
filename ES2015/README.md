## ECMAScript 2015 also known as ES6 was the second major revision to JavaScript.
Following are the new features included in ES6:


- [ECMAScript 2015 also known as ES6 was the second major revision to JavaScript.](#ecmascript-2015-also-known-as-es6-was-the-second-major-revision-to-javascript)
  - [Let keyword](#let-keyword)
  - [Const keyword](#const-keyword)
  - [Arrow Functions](#arrow-functions)
  - [The Spread (...) Operator](#the-spread--operator)
  - [The For/Of Loop](#the-forof-loop)
  - [JavaScript Maps](#javascript-maps)
  - [JavaScript Sets](#javascript-sets)
  - [JavaScript Classes](#javascript-classes)
    - [The Constructor Method](#the-constructor-method)


___

### Let keyword
The `let` keyword allows you to declare a variable with block scope i.e _the variable defined within a block will not be accessible from outside the block_. The variables defined with let can't be redeclare and must be declared before use

```Javascript
var x = 10; // Here x is 10
{
  let x = 2; // Here x is 2
}
// Here x is 10
```

___

### Const keyword

The `const` keyword allows you to declare a _constant reference value_(a variable whose location can't be changed). A const variable is similar to `let` variable like it can't be redeclare and have block level scoping, the only difference is that it can't be reassigned a value. A `const` variable must be assigned a value when they are declared.

```Javascript
var x = 10; // Here x is 10
{
  const x = 2; // Here x is 2
}
// Here x is 10
```

```Javascript
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```
**In ES2015 _block level scope_ was introduced and before it only _global level_ and _function level_ scope was available.**

___

### Arrow Functions

Arrow functions allows a short syntax for writing function expressions. You don't need the `function, return` keyword and the **curly brackets**. 

```Javascript
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;
```

Following are the few things to note while using Arrow functions.
- Arrow functions don't have their own `this`. Hence they are not well suited for defining **object methods**.
- Arrow functions are not hoisted. They must be defined before they are used.
- Using `const` is safer than using `var`, as a function expression is always a constant value.
- You can only omit the `return` keyword and the curly brackets if the function is a single statement and because of this, it might be a good habit to always keep them.
 
 ```Javascript
const x = (x, y) => { return x * y };
 ```
___

### The Spread (...) Operator

The `...` operator allows to quickly copy all or part of an existing array or object into another array or object.

```Javascript
const numbersOne = [1, 2];
const numbersTwo = [4, 5];
const numbersCombined = [...numbersOne, ...numbersTwo];
// output will be-> numbersCombined = [1, 2, 4, 5];
```

The spread operator is often used in combination with destructuring. When destructuring arrays, the order that variables are declared is important while object properties don't have to be declared in a specific order.

```Javascript
// assign the first and second items from numbers to variables and put the rest in an array:
const numbers = [1, 2, 3, 4, 5, 6];

const [one, two, ...rest] = numbers;
// output -> one = 1; two = 2; rest = [3, 4, 5, 6];
```

The `...` operator can be used to expand an iterable into more arguments for function calls:

```Javascript
const numbers = [23,55,21,87,56];
let maxValue = Math.max(...numbers);
```
___

### The For/Of Loop
The Javascript `for/of` statement loops through the values of an iterable objects. `for/of` lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists and more. 

**Syntax:**
```Javascript
for(variable of iterable){
  // code to be executed
}
```
`variable` - For every iteration the value of the next property is assigned to the variable. Variable can be declared with `const`, `let`, or `var`.

`iterable` - An object that has iterable properties.

**Example:**

```Javascript
const fruits = ["apple", "banana", "mango"];
let output = "";
for(let x of fruits){
  output += x + " ";
}
// output will be -> "apple banana mango"
```

_It is better to use a `for`, `for of` loop when the order in which the elements are accessed is important over `for in` loop._

___

### JavaScript Maps

Map objects are collections of key-value pairs. A key in the Map may only occur once; it is unique in the Map's collection. A Map object is iterated by key-value pairs — a for...of loop returns a 2-member array of [key, value] for each iteration. Iteration happens in insertion order, which corresponds to the order in which each key-value pair was first inserted into the map by the set() method (that is, there wasn't a key with the same value already in the map when set() was called).

**Example:**
```Javascript
// Create a Map
const fruits = new Map();

// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200);
```
**Object vs Maps quick comparison**


| Objects | Maps |
|---------|------|
| Not directly iterable |	Directly iterable|
|Do not have a size property	| Have a size property|
|Keys must be Strings (or Symbols)	| Keys can be any datatype|
|Keys are not well ordered	| Keys are ordered by insertion|
|Have default keys	| Do not have default keys|
___

### JavaScript Sets
A JavaScript set is a collection of unique values. Each value can only occur once in a set and a set can only hold value of any data type. `forEach()` method can be used to fetch teach Set element.

**Example:**

```Javascript
// Create a Set
const letters = new Set(["a","b","c"]);

// List all entries
let text = "";
letters.forEach (function(value) {
  text += value;
})
// output will be -> abc
```
___

### JavaScript Classes

Classes in JavaScript were introduced in ES6. They are the templates for JavaScript Objects.

**Syntax:**

Use the keyword `class` to create a class and always add a method named `constructor`()

```Javascript
class ClassName{
  constructor(){}
}
```
**Example:**

```Javascript
class Car{
  constructor(name, year){
    this.name = name;
    this.year = year;
  }
}
// the above code will creates a class named `Car` with 2 initial properties: `name` and `year`.
```
- _A Javascript class in not an object. It is the temple that is used to create the object._
- The constructor method is called automatically when a new object is created.

```Javascript
const myCar1 = new Car("Ford", 2014);
const myCar2 = new Car("Audi", 2019);
// the above code will create 2 Car objects using the Car class.
```
#### The Constructor Method
The constructor method is a special method:
- It has to have the exact name `constructor`
- It is executed automatically when a new object is created
- It is used to initialize object properties
- If you don't define a constructor method, Javascript will add an empty constructor method.

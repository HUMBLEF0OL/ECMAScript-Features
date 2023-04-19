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
  - [Promises](#promises)
  - [The Symbol Type](#the-symbol-type)
  - [Default Parameter Values](#default-parameter-values)
  - [Function Rest Parameter](#function-rest-parameter)
  - [String.includes()](#stringincludes)
  - [String.startsWith()](#stringstartswith)
  - [String.endsWith()](#stringendswith)
  - [Array.from()](#arrayfrom)
  - [Array.keys()](#arraykeys)
  - [Array.find()](#arrayfind)
  - [Array.findIndex()](#arrayfindindex)
  - [New Math Methods](#new-math-methods)
  - [New Number Properties](#new-number-properties)
  - [New Number Methods](#new-number-methods)
  - [New Global Methods](#new-global-methods)
  - [Object entries()](#object-entries)
  - [Javascript Modules](#javascript-modules)
    - [Export](#export)
    - [Import](#import)

---

### Let keyword

The `let` keyword allows you to declare a variable with block scope i.e _the variable defined within a block will not be accessible from outside the block_. The variables defined with let can't be redeclare and must be declared before use

```Javascript
var x = 10; // Here x is 10
{
  let x = 2; // Here x is 2
}
// Here x is 10
```

---

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

---

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

---

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

---

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

---

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

| Objects                           | Maps                          |
| --------------------------------- | ----------------------------- |
| Not directly iterable             | Directly iterable             |
| Do not have a size property       | Have a size property          |
| Keys must be Strings (or Symbols) | Keys can be any datatype      |
| Keys are not well ordered         | Keys are ordered by insertion |
| Have default keys                 | Do not have default keys      |

---

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

---

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

---

### Promises

- **Producing code** is code that can take some time
- **Consuming code** is code that must wait for the result

A Promise is a JavaScript object that links producing code and consuming code. Hence it contains both the producing code and the call to the consuming code.

**Syntax:**

```Javascript
let examplePromise = new Promise((resolve, reject)=>{
  // producing code -> which may take some time
  resolve(); // when successful
  reject(); // when failed or error
});

// consuming code -> which will wait for the promise to fulfill
examplePromise.then(
  ()=>{
    // for successful execution
  }
  ()=>{
    // for error
  }
);
```

On successful completion of producing code, one of the two callback(resolve, reject) is called. There are two properties of the Promise object: **state** and **result** which are inaccessible and in order to handle the promises we must use the Promise method. Following are the 3 stages of promise:

- Pending: waiting for result
- Fulfilled: Promise results in success
- Reject: Promise result in failure

`Promise.then()` that takes two arguments, a callback for success and another for failure. Both are optional, so you can dd a callback for success or failure only. If we're interested only in errors, then we can use `null` as the first argument.
**Example:**

```Javascript
const loadScript = (src) => {
  return new Promise((resolve,reject)=>{
    let script = document.createElement("script");
    script.scr = scr;
    script.onload = () => resolve(script);
    script.onerror = ()=> reject(new Error(`Script load error for ${scr}`));

    document.head.append(script);
  });

  // Usage:
  let promise = loadScript("https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js");

  promise.then(
    (script)=>{
      alert(`${script.src} is loaded!`);
    }
    (error) =>{
      alert(`Error: ${error.message}`);
    }
  );
}
```

---

### The Symbol Type

The Javascript ES6 introduced a new primitive data type called `Symbol`. Symbols are immutable(can't be changed) and are unique.

**Example:**

```Javascript
// two symbols with the same description
const value1 = Symbol('hello');
const value2 = Symbol('hello');

console.log(value1 === value2); // false
```

Though `value1` and `value2` both contain the same description, they are different.

- For creating symbol you can use `Symbol()` function, also an optional string as its description can be passed
  ```Javascript
  const x = Symbol()
  const x = Symbol("hey");
  console.log(x); // Symbol(hey)
  ```
- To access the description of a symbol, we can use the `.description` operator.
  ```Javascript
  const x = Symbol('hey');
  console.log(x.description); // hey
  ```
- To add symbols as a _key_ in an object we can use the `[]` brackets.
  ```Javascript
  let id = Symbol('id');
  let person = {
    name:"Jack",
    // adding symbol as a key
    [id]: 123 //not "id":123
  }
  console.log(person) // {name:"Jack", Symbol(id): 123}
  ```
- The `for...in` loop doesn't iterate over Symbolic properties.

**Benefits of Using Symbols in Object**

If the same code snippet is used in various programs, then its is better to use `Symbols` in the object key. It is because you can use the same key name i different codes and avoid duplication issues.

**Example:**

```Javascript
let person = {
  name: "Jack"
};
//creating symbol
let id = Symbol("id");
// adding symbol as a key
person[id] = 12;
```

In the above example, if the `person` object is also used by another program, then you wouldn't want to add a property that can be accessed or changed by another program. Hence by using symbol, you create a unique property that you can use.

Now if the other program also needs to use a property named _id_, just add a Symbol named `id` and there won't be duplication issues. For example:

```Javascript
let person ={
  name: 'Jack'
};

let id = Symbol('id');
person[id] = "Another value";
```

In the above program, even if the same name is used to store values, the symbol data type will have a unique value.

---

### Default Parameter Values

ES6 allows function parameters to have default values.

**Example:**

```Javascript
const addFunction = (x,y=10) =>{
  // if values of  y are not passed then default value of 10 will be applied to it
  return x +y;
}
addFunction(5); // will return 15
```


---

### Function Rest Parameter
The rest parameter (...) allows a function to treat an indefinite number of argument as an array:

**Example:**

```Javascript
const totalSum = (...args) =>{
  let sum = 0;
  for(let arg of args){
    sum += arg;
  }
  return sum;
}

let x = totalSum(4,6,1,2,7,5);
```
---

### String.includes()
The `includes()` method returns `true` if a string contains a specified value, otherwise `false`. The `includes()` method is _case sensitive_. 

**Example:**
```Javascript
let text = "The is the sample string";
text.includes("sample") // returns true
```
---

### String.startsWith()


The `startsWith()` method returns `true` if a string begins with a specified value, otherwise `false`. This method is _case-sensitive_.

**Example:**
```Javascript
let text = "This is the sample string";
text.startsWith("This") // returns true
```

---

### String.endsWith()

The `endsWith()` method returns `true` if a string ends with a specified value, otherwise `false`. This method is _case-sensitive_.

**Example:**
```Javascript
let text = "This is the sample string";
text.endsWith("string") // returns true
```
---

### Array.from()

The `Array.from()` method lets you create array from _iterable objects_(object such as `Map` and `Set`) or if the object is not iterable,array-like objects(objects with a `length` property and indexed elements). `Array.from()` never creates a sparse array(an array of data in which many elements have a value of zero)

**Example:**

```Javascript
// array from a string
Array.from("foo"); //["f","o","o"]


// array from a set
const set = new Set(["foo", "bar", "baz", "foo"]);
Array.from(set); // ["foo", "bar", "baz"]

// array from a Map
const map = new Map([
  [1, 2],
  [2, 4],
  [4, 8],
]);
Array.from(map);
// [[1, 2], [2, 4], [4, 8]]
Array.from(mapper.values());
// ['a', 'b'];

Array.from(mapper.keys());
// ['1', '2'];

```
---
### Array.keys()
The Javascript `array.keys()` method is used to return a new array iterator which contains the keys for each index in the given input array. It returns a new array iterator.
**Syntax:**
```Javascript
array.keys()
```
**Example:**
```Javascript
// Taking input as an array A
// containing some elements.
let A = [ 5, 6, 10 ];
  
// array.keys() method is called
let iterator = A.keys();
  
// printing index array using the iterator
for (let key of iterator) {
    console.log(key);
}

// output will be -> 0,1,2
```
---

### Array.find()
The `find()` method returns the value of the first array element that passes a test function. 
- This method will return `undefined` if no elements are found.
- The `find()` method does not execute the function for empty elements.
- The `find()` method does not change the original array.

**Syntax:**
```javascript
array.find(function(currentValue, index, arr),thisValue)
/*
  function() -> required(a function to be run for each array element)
  currentValue -> required (value of current element)
  index -> optional (index of current element)
  arr -> optional (the array of the current element)
  thisValue -> optional and default is undefined
*/
```
**Example:**
```Javascript
// the below example finds the first element that is larger than 18:
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find((value, index) => {
  return value > 18;
})
// output will be 25
```

### Array.findIndex()
The `findIndex() method returns the index of the first array element that passes a test function.
- The `findIndex()` method returns -1 if no match is found.
- The `findIndex()` method doesn't execute the function for empty array elements.
- The `findIndex()` method doesn't change the original array.

**Syntax:**
```Javascript
array.findIndex(function(currentValue, index, arr), thisValue)
/*
  function() -> required(a function to be run for each array element)
  currentValue -> required (value of current element)
  index -> optional (index of current element)
  arr -> optional (the array of the current element)
  thisValue -> optional and default is undefined
*/
```

**Example:**
```Javascript
const ages = [3, 10, 18, 20];

ages.findIndex(checkAge);

function checkAge(age) {
  return age > 18;
}
```

### New Math Methods
ES6 added the following methods to the Math object:
- `Math.trunc()`: returns the integer part of x:
  
    **Example:**
    `Math.trunc(4.9) //returns 4`

- `Math.sign()`: returns if x is negative, null or positive:
  
    **Example:**
    `Math.sign(-4) //returns -1` 

- `Math.cbrt()`: returns the cube root of x:
  
    **Example:**
    `Math.cbrt(64) //returns 4` 

- `Math.log2()`: returns the base 2 logarithm of x:
  
    **Example:**
    `Math.log2(2) //returns 1` 

- `Math.log10()`: returns the base 10 logarithm of x:
  
    **Example:**
    `Math.log10(10) //returns 1` 

---
### New Number Properties
ES6 added the following properties to the Number object:
  - EPSILON
    **Example:**
    `let x = Number.EPSILON; //returns 2.220446049250313e-16`
  - MIN_SAFE_INTEGER
    **Example:**
    `let  x = Number.MIN_SAFE_INTEGER; //returns -9007199254740991
  - MAX_SAFE_INTEGER
    **Example:**
    `let  x = Number.MAX_SAFE_INTEGER; //returns 9007199254740991
  
---
### New Number Methods
ES6 added 2 new methods to the Number Object:
- `Number.isInteger()` that returns `true` if the argument is an integer.
  **Example:**
  ```Javascript
  Number.isInteger(10);        // returns true
  Number.isInteger(10.5);      // returns false
  ```
- `Number.isSafeInteger()` returns `true` if the argument is a safe integer.
  **Example:**
  ```Javascript
  Number.isSafeInteger(10);    // returns true
  Number.isSafeInteger(12345678901234567890);  // returns false
  ```
---

### New Global Methods
ES6 added 2 new global number methods:
- `isFinite()` returns `false` if the argument is `Infinity` or `Nan`. Otherwise it returns `true`:
 **Example:**
 ```Javascript
  isFinite(10/0);       // returns false
  isFinite(10/1);       // returns true
 ```
- `isNaN()` is the global method returns `true` if the argument is `NaN`. Otherwise if returns `false`:
 **Example:**
 `isNaN("Hello"); // returns true`

 ---

 ### Object entries()
 The `entries()` method returns an Array Iterator object with key/value pairs. The `entries()` method doesn't change the original array.
 ```Javascript
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// Expected output:
// "a: somestring"
// "b: 42"
 ```
---
### Javascript Modules
JS modules allow you to break up the code into separate files. This makes it easier to maintain a code-base. Modules are imported from external files with the `import` statement. Modules also rely on `type=module` in the `<script>` tag.
**Example:**
```html
<script type="module">
import message from "./message.js";
</script>
```
#### Export
There are 2 types of exports in module:
- Named Exports:
  We can create the named exports in 2 ways. In-line individually, or all at once at the bottom.
  - In-line individually:
    ```javascript
      export const name = "Jesse";
      export const age = 40;
    ``` 
  - All at once at the bottom:
    ```javascript
      const name = "Jesse";
      const age = 40;
      export {name, age};
    ```
- Default Exports:
  We can only have one default export in a file.
  ```javascript
  const message = () => {
  const name = "Jesse";
  const age = 40;
  return name + ' is ' + age + 'years old.';
  };

  export default message;
  ```
#### Import
We can import modules into a file in 2 ways, based on if they are named export or default exports. Named exports are constructed using curly braces, while default exports are not.
- Import from named exports:
 
  `import { name, age } from "./person.js";`
- Import from default exports
 
  `import message from "./message.js";`

*Modules only work with HTTP(s) protocol. A web-page opened via the file:// protocol cannot use import / export.
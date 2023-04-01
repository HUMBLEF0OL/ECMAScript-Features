## ECMAScript 2015 also known as ES6 was the second major revision to JavaScript.
Following are the new features included in ES6:


- [ECMAScript 2015 also known as ES6 was the second major revision to JavaScript.](#ecmascript-2015-also-known-as-es6-was-the-second-major-revision-to-javascript)
  - [Let keyword](#let-keyword)
  - [Const keyword](#const-keyword)
  - [Arrow Functions](#arrow-functions)
  - [The Spread (...) Operator](#the-spread--operator)



### Let keyword
The `let` keyword allows you to declare a variable with block scope i.e _the variable defined within a block will not be accessible from outside the block_. The variables defined with let can't be redeclare and must be declared before use

```Javascript
var x = 10; // Here x is 10
{
  let x = 2; // Here x is 2
}
// Here x is 10
```


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
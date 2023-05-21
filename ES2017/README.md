## Following are the new features included in ES2017:

- [Following are the new features included in ES2017:](#following-are-the-new-features-included-in-es2017)
  - [Javascript String Padding:](#javascript-string-padding)
- [JavaScript Object Entries:](#javascript-object-entries)
- [JavaScript `Object.values()`:](#javascript-objectvalues)
- [Javascript async/await:](#javascript-asyncawait)


### Javascript String Padding:

ECMAScript 2017 added two string methods to JavaScript: padStart() and padEnd() to support padding at the beginning and at the end of a string.

The _padStart()_ method in JavaScript is used to pad a string with another string until it reaches the given length. The padding is applied from the left end of the string. 

**Syntax:**
_string.padStart(targetLength, padString)_

**Parameters:**
This method accepts two parameters as mentioned above and described below:

- targetLength: It is the length of the final string once the original string has been padded. If the value is less than the original string length, then the original string is returned.
- padString: It is the string that is to be padded with the original string. If this value is too long to be within the targetLength, it is truncated from the end. The default used string is the space character (” “).

**Return Value:** 
It returns the final string that is padded with the given string to the given length. 

**Example:**
```Javascript
// string definition
let string1 = "CODE";

// padding "*" to the start of given string
// until the length of final padded string reaches 10
let paddedString = string1.padStart(10, "*");

console.log(paddedString);

// Output: ******CODE
```

*Similarly the `padEnd()` is used to append string at the end of the given string*

---

## JavaScript Object Entries:
The `Object.entries()` method returns an array of key-value pairs of an object's enumerable properties.

**Syntax:**
The `entries()` method, being a static method, is called using the Object class name. The syntax of the `entries()` method is:

`Object.entries(required_obj)`

**Example:**
```Javascript
const obj = { name: "Adam", age: 20, location: "Nepal" };

// returns properties in key-value format
console.log(Object.entries(obj)); 

// Output:  [ [ 'name', 'Adam' ], [ 'age', 20 ], [ 'location', 'Nepal' ] ]
```
---

## JavaScript `Object.values()`:
The `Object.values()` method returns an array containing the enumerable values of an object.

**Syntax:**
The `values()` method, being a static method, is called using the Object class name. The syntax of the `values() `method is:

**Example:**
```Javascript
// array-like object having integers as key
const obj = { 65: "A", 66: "B", 67: "C" };

// print the enumerable values of obj
console.log(Object.values(obj));

// Output:  [ 'A', 'B', 'C' ]
```

---

## Javascript async/await:
We use the `async` keyword with a function to represent that the function is an asynchronous function. The async function returns a `promise`.

The syntax of async function is:
```Javascript
async function functionName(parameter1, parameter2, ...paramaterN){
    // statements
}
```

**Example:**
```Javascript
// async function example

async function f() {
    console.log('Async function.');
    return Promise.resolve(1);
}

f(); 

// Output: Async function.
```

In the above program, the ``async keyword is used before the function to represent that the function is asynchronous.

Since this function returns a promise, you can use the chaining method `then()` like this:
```Javascript
async function f() {
    console.log('Async function.');
    return Promise.resolve(1);
}

f().then(function(result) {
    console.log(result)
});

// Output: Async function
// 1
```

In the above program, the `f()` function is resolved and the `then()` method gets executed.

**JavaScript await Keyword**
The await` keyword is used inside the async function to wait for the asynchronous operation.

The syntax to use await is:

`let result = await promise;`


The use of `await` pauses the async function until the promise returns a result (resolve or reject) value. For example,

```Javascript
// a promise
let promise = new Promise(function (resolve, reject) {
    setTimeout(function () {
    resolve('Promise resolved')}, 4000); 
});

// async function
async function asyncFunc() {

    // wait until the promise resolves 
    let result = await promise; 

    console.log(result);
    console.log('hello');
}

// calling the async function
asyncFunc();

// Output:
// Promise resolved
// hello
```

In the above program, a `Promise` object is created and it gets resolved after 4000 milliseconds. Here, the `asyncFunc()` function is written using the `async` function.

The `await` keyword waits for the promise to be complete (resolve or reject).
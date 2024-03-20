
## ECMAScript 2018, also known as ES9, introduced several new features and improvements.

Following are the new features included in ES2018:

- [ECMAScript 2018, also known as ES9, introduced several new features and improvements.](#ecmascript-2018-also-known-as-es9-introduced-several-new-features-and-improvements)
  - [Asynchronous Iteration](#asynchronous-iteration)
  - [Rest/Spread Properties](#restspread-properties)
  - [Promise.prototype.finally()](#promiseprototypefinally)
  - [RegExp Improvements](#regexp-improvements)
  - [Object Rest/Spread Properties](#object-restspread-properties)
  - [Shared Memory and Atomics](#shared-memory-and-atomics)
  - [Async Generators](#async-generators)
  - [Object.entries() and Object.values()](#objectentries-and-objectvalues)

---

### Asynchronous Iteration

Allows for asynchronous iteration over objects that implement the async iterable protocol.

Example:

```javascript
async function* fetchUrls(urls) {
  for await (const url of urls) {
    const response = await fetch(url);
    console.log(await response.text());
  }
}
const urls = [url1, url2, url3];
fetchUrls(urls);
```

---

### Rest/Spread Properties

Rest properties collect the remaining properties of an object into a new object, while spread properties spread the properties of an object into another object.

Example:

```javascript
const { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }
```

---

### Promise.prototype.finally()

Adds a `finally` method to the `Promise` prototype, allowing you to run code after a promise is settled (either fulfilled or rejected).

Example:

```javascript
fetchData()
  .then(data => processData(data))
  .catch(error => handleErrors(error))
  .finally(() => console.log('Cleanup'));
```

---

### RegExp Improvements

The `s` (dotAll) flag for regular expressions makes the dot (`.`) in regular expressions match all characters, including newlines.

Example:

```javascript
const regex = /foo.bar/s;
console.log(regex.test('foo\nbar')); // true
```

---

### Object Rest/Spread Properties

Similar to rest/spread properties for arrays, this feature allows you to use the spread syntax with objects.

Example:

```javascript
const person = { name: 'John', age: 30, city: 'New York' };
const { name, ...rest } = person;
console.log(name); // John
console.log(rest); // { age: 30, city: 'New York' }
```

---

### Shared Memory and Atomics

Shared memory and atomic operations allow for more efficient concurrent programming, particularly in web workers.

Example:

```javascript
const sharedArray = new Int32Array(new SharedArrayBuffer(4));
Atomics.store(sharedArray, 0, 42);
console.log(Atomics.load(sharedArray, 0)); // 42
```

---

### Async Generators

Functions can now be both async and a generator, allowing for more flexible asynchronous iteration patterns.

Example:

```javascript
async function* asyncGenerator() {
  yield 1;
  yield 2;
  return 3;
}
const gen = asyncGenerator();
gen.next().then(console.log); // { value: 1, done: false }
```

---

### Object.entries() and Object.values()

These methods were introduced to complement the existing `Object.keys()` method. They allow you to extract the key-value pairs of an object into arrays, making it easier to iterate over objects and work with their values.

Example:

```javascript
const person = { name: 'John', age: 30 };

// Object.entries()
for (const [key, value] of Object.entries(person)) {
  console.log(`${key}: ${value}`);
}
// Output:
// name: John
// age: 30

// Object.values()
for (const value of Object.values(person)) {
  console.log(value);
}
// Output:
// John
// 30
```

---
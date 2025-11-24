
---

# 1. Functions in JavaScript

### What is a function?

A function is a block of code designed to perform a task. It runs only when called.

### Why functions are used

* Reuse code
* Organize logic
* Avoid repeating tasks
* Improve maintainability

---

## A. Function Declaration

A named function defined with the `function` keyword. Fully hoisted.

```js
function greet() {
  console.log("Hello");
}

greet();
```

---

## B. Function Expression

A function stored inside a variable. Not hoisted the same way.

```js
const greet = function() {
  console.log("Hello");
};

greet();
```

---

## C. Arrow Function

Shorter syntax. Does not have its own `this`.

```js
const greet = () => {
  console.log("Hello");
};
```

Short version:

```js
const add = (a, b) => a + b;
```

---

## D. Anonymous Function

A function without a name. Mostly used as a callback.

```js
setTimeout(function() {
  console.log("Done");
}, 1000);
```

---

## E. Parameters and Arguments

Parameters are placeholders, arguments are actual values.

```js
function sum(a, b) {  // a, b → parameters
  return a + b;
}

sum(10, 20);          // 10, 20 → arguments
```

---

## F. Default Parameters

Provide default values if arguments are missing.

```js
function multiply(a = 2, b = 5) {
  return a * b;
}

console.log(multiply());  // 10
```

---

## G. Return Statement

```js
function getName() {
  return "John";
}

console.log(getName());  // John
```

If no return, function returns `undefined`.

---

# 2. Function Binding: call, apply, bind

JavaScript functions have dynamic `this`. Binding helps control what `this` refers to.

---

## A. call()

Calls the function immediately.

```js
function greet() {
  console.log("Hello " + this.name);
}

const user = { name: "John" };

greet.call(user);    // Hello John
```

---

## B. apply()

Same as call, but arguments are passed as an array.

```js
function sum(a, b) {
  return a + b;
}

console.log(sum.apply(null, [5, 10]));  // 15
```

---

## C. bind()

Returns a new function with a fixed `this`.

```js
const user = {
  name: "Alice",
  greet: function() {
    console.log("Hello " + this.name);
  }
};

const greetUser = user.greet.bind(user);
greetUser();   // Hello Alice
```

Used in event handlers and callbacks.

---

# 3. Hoisting with Functions

### Function declarations are hoisted:

```js
sayHello();      // Works

function sayHello() {
  console.log("Hello");
}
```

### Function expressions are not hoisted:

```js
sayHello();      // Error
const sayHello = function() {};
```

### Arrow functions behave the same as expressions.

---

# 4. Closures

A closure happens when an inner function remembers variables from its outer function even after the outer function finishes.

---

### Example:

```js
function makeCounter() {
  let count = 0;

  return function() {
    count++;
    return count;
  };
}

const counter1 = makeCounter();

console.log(counter1());  // 1
console.log(counter1());  // 2
```

The inner function continues to access `count` after `makeCounter()` has finished execution.

### Uses of closures

* Private variables
* Function factories
* Maintaining state
* Module patterns

---

# 5. Higher-Order Functions

A function that:

1. Takes another function as a parameter, or
2. Returns a function

---

### Example: map

```js
const arr = [1, 2, 3];

const doubled = arr.map(function(num) {
  return num * 2;
});

console.log(doubled);  // [2, 4, 6]
```

### Example: a function returning another function

```js
function multiplier(factor) {
  return function(num) {
    return num * factor;
  };
}

const double = multiplier(2);
console.log(double(5));  // 10
```

---

# 6. Iterator

An iterator is an object that allows you to traverse data manually.
It must have a `next()` method.

---

### Example:

```js
const arr = [10, 20, 30];

const iterator = arr[Symbol.iterator]();

console.log(iterator.next()); // { value: 10, done: false }
console.log(iterator.next()); // { value: 20, done: false }
console.log(iterator.next()); // { value: 30, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

Used in:

* for...of
* spread operator
* generators

---

# 7. Generator Functions

Generators create iterators automatically and allow pausing and resuming execution.

---

### Example:

```js
function* generateNumbers() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = generateNumbers();

console.log(gen.next());  // {value: 1, done: false}
console.log(gen.next());  // {value: 2, done: false}
console.log(gen.next());  // {value: 3, done: false}
console.log(gen.next());  // {value: undefined, done: true}
```

### Infinite generator:

```js
function* infinite() {
  let i = 0;
  while (true) {
    yield i++;
  }
}
```

Generators help in async workflows and creating custom iterators.

---

# 8. Events in JavaScript

Events are actions performed by the user or the browser:

* Click
* Scroll
* Key press
* Load/Unload
* Mouse move

---

## Registering event listeners

### A. Inline

```html
<button onclick="hello()">Click</button>
```

---

### B. DOM property

```js
button.onclick = function() {
  console.log("Clicked");
};
```

---

### C. addEventListener (recommended)

```js
button.addEventListener("click", function(event) {
  console.log("Button clicked");
});
```

### Event object:

```js
button.addEventListener("click", function(event) {
  console.log(event.target);  // element clicked
});
```

---

# 9. Event Loop

JavaScript is single-threaded but handles asynchronous tasks using:

* Call Stack
* Web APIs
* Callback Queue (Macrotasks)
* Microtask Queue (Promises)
* Event Loop

---

### Example showing order:

```js
console.log("A");

setTimeout(() => console.log("B"), 0);

Promise.resolve().then(() => console.log("C"));

console.log("D");
```

Execution:

1. A
2. D
3. C (microtask)
4. B (macrotask)

Microtasks always run before macrotasks.

---

# 10. Event Bubbling and Capturing

### Bubbling (default):

Event starts at target element and moves upwards to parents.

Example:
Clicking a button inside a div:

1. button handler runs
2. div handler runs
3. body handler runs

---

### Example:

```js
document.body.addEventListener("click", () => console.log("body"));
document.querySelector("div").addEventListener("click", () => console.log("div"));
document.querySelector("button").addEventListener("click", () => console.log("button"));
```

Click button:
button
div
body

---

### stopPropagation():

```js
button.addEventListener("click", function(e) {
  e.stopPropagation();
});
```

---

### Capturing phase:

Event goes from parent to child.

```js
element.addEventListener("click", handler, true);
```

---



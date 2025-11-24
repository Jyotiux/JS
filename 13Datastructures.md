

---

# 1. Numbers in JavaScript

JavaScript uses **double-precision 64-bit floating point** numbers (IEEE 754).
It stores both integers and decimals in the same format.

### Number basics

```js
let x = 10;
let y = 10.5;
```

### Special numeric values

```js
Infinity
-Infinity
NaN   // Not-a-Number
```

Examples:

```js
console.log(10 / 0);     // Infinity
console.log("abc" * 5);  // NaN
```

### Useful number methods

```js
Number.isInteger(10);           // true
Number.parseInt("50px");        // 50
Number.parseFloat("5.25px");    // 5.25
(10.789).toFixed(2);            // "10.79"
(5.678).toPrecision(2);         // "5.7"
```

### Precision issue example

```js
0.1 + 0.2 === 0.3    // false
```

---

# 2. Strings in JavaScript

Strings represent text. They are **immutable** (cannot be changed directly).

### Declaration

```js
let s1 = "Hello";
let s2 = 'Hello';
let s3 = `Hello ${name}`;  // Template literal
```

### Common string methods

```js
"hello".toUpperCase();         // "HELLO"
"HELLO".toLowerCase();         // "hello"
"JavaScript".includes("Script");  // true
"abcabc".indexOf("b");         // 1
"hello world".replace("world", "JS");
```

### String slicing

```js
"JavaScript".slice(4);     // "Script"
"JavaScript".substring(0, 4); // "Java"
"JavaScript"[0];           // "J"
```

---

# Quiz: Numbers, Strings (sample)

1. Why is `0.1 + 0.2` not exactly equal to 0.3?
2. What will `"5" + 5` and `"5" - 5` output?
3. What is the difference between `slice()` and `substring()`?

---

# 3. Arrays

Arrays hold ordered, indexed data.

### Creating arrays

```js
const arr = [1, 2, 3];
const arr2 = new Array(5, 6, 7);
```

### Accessing elements

```js
arr[0];     // 1
arr.length; // 3
```

### Adding/removing elements

```js
arr.push(4);     // [1,2,3,4]
arr.pop();       // remove last
arr.unshift(0);  // add at start
arr.shift();     // remove from start
```

### Searching

```js
arr.indexOf(2);        // 1
arr.includes(3);       // true
```

### Important array methods

```js
arr.map(x => x * 2);
arr.filter(x => x > 2);
arr.reduce((acc, x) => acc + x, 0);
arr.find(x => x === 2);
arr.sort((a, b) => a - b);
```

### Spread syntax

```js
const newArr = [...arr, 10];
```

---

# 4. Linked List in JavaScript

JavaScript does not have a built-in linked list, but it can be implemented with objects.

### Node structure

```js
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}
```

### Singly linked list

```js
class LinkedList {
  constructor() {
    this.head = null;
  }

  insert(value) {
    const node = new Node(value);
    node.next = this.head;
    this.head = node;
  }
}
```

### Traversal

```js
let temp = list.head;
while (temp) {
  console.log(temp.value);
  temp = temp.next;
}
```

Linked lists are useful where frequent inserts/deletes at the beginning are needed.

---

# Quiz: Arrays, LinkedList (sample)

1. What is the time complexity of array indexing?
2. What is the time complexity of inserting in the middle of an array?
3. Why is a linked list preferred over arrays for insertions?

---

# 5. Map in JavaScript

Map stores key-value pairs and remembers insertion order.

### Example

```js
const map = new Map();

map.set("name", "John");
map.set(1, "Number key");
map.set(true, "Boolean key");

console.log(map.get("name"));
console.log(map.has(1));
```

### Map vs Object

Map allows:

* keys of any type
* ordered iteration
* better performance for large datasets

---

# 6. Stack

A stack works on **LIFO (Last In, First Out)**.

### Implementing stack

```js
class Stack {
  constructor() {
    this.items = [];
  }

  push(val) {
    this.items.push(val);
  }

  pop() {
    return this.items.pop();
  }

  peek() {
    return this.items[this.items.length - 1];
  }
}

const stack = new Stack();
stack.push(10);
stack.push(20);
stack.pop();   // 20
```

Stacks are used in:

* Undo operations
* Backtracking
* Expression evaluation

---

# 7. Queue

A queue works on **FIFO (First In, First Out)**.

### Implementation

```js
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(val) {
    this.items.push(val);
  }

  dequeue() {
    return this.items.shift();
  }
}

const q = new Queue();
q.enqueue(1);
q.enqueue(2);
q.dequeue();    // 1
```

Queues are used in:

* Scheduling
* Printers
* Task processing

---

# Quiz: Stack, Queue (sample)

1. Difference between stack and queue?
2. Which is LIFO? Which is FIFO?
3. What does `peek()` return in a stack?

---

# 8. Sorting Algorithms

JavaScript has built-in sorting:

```js
arr.sort((a, b) => a - b);
```

But learning manual algorithms is important.

### Bubble Sort

```js
function bubbleSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
}
```

### Selection Sort

```js
function selectionSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    let min = i;
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[min]) min = j;
    }
    [arr[i], arr[min]] = [arr[min], arr[i]];
  }
}
```

### Quick Sort

```js
function quickSort(arr) {
  if (arr.length <= 1) return arr;

  const pivot = arr[0];
  const left = [];
  const right = [];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < pivot) left.push(arr[i]);
    else right.push(arr[i]);
  }

  return [...quickSort(left), pivot, ...quickSort(right)];
}
```

---

# 9. JavaScript ES6+ Data Structures

## A. WeakMap

Keys must be objects.
Garbage-collected when no references exist.

```js
const wm = new WeakMap();
let obj = {};

wm.set(obj, "value");
obj = null;  // entry removed automatically
```

Use case: private object data.

---

## B. WeakSet

Only stores objects, no duplicates.
Automatically garbage-collected.

```js
const ws = new WeakSet();
let obj = {};

ws.add(obj);
obj = null;
```

---

## C. Typed Arrays

Used for working with binary data (images, audio, video).

Example:

```js
const buffer = new ArrayBuffer(8);
const view = new Uint8Array(buffer);
view[0] = 255;
```

Typed arrays include:

* Int8Array
* Uint8Array
* Float32Array
  etc.

---

## D. Deque (Double-ended queue)

Insert/remove at both ends.

Implementation:

```js
class Deque {
  constructor() {
    this.items = [];
  }
  pushFront(val) { this.items.unshift(val); }
  pushBack(val)  { this.items.push(val); }
  popFront()     { return this.items.shift(); }
  popBack()      { return this.items.pop(); }
}
```

---

## E. Priority Queue (Heap)

Highest or lowest priority item gets removed first.

Example (min-heap):

```js
class MinHeap {
  constructor() {
    this.data = [];
  }

  insert(val) {
    this.data.push(val);
    this.bubbleUp();
  }

  bubbleUp() {
    let idx = this.data.length - 1;
    while (idx > 0) {
      let parent = Math.floor((idx - 1) / 2);
      if (this.data[idx] >= this.data[parent]) break;
      [this.data[idx], this.data[parent]] = [this.data[parent], this.data[idx]];
      idx = parent;
    }
  }
}
```

Used in:

* Dijkstra’s algorithm
* Task scheduling
* CPU management

---

# Quiz: Data Structures (sample)

1. What is the difference between Array and LinkedList?
2. What is the time complexity of accessing an element in an array?
3. What is a WeakMap used for?
4. How does a priority queue differ from a normal queue?
5. What data structure does JavaScript's `Map` resemble?

---



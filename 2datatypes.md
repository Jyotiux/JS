### **Data Types in JavaScript**

---

## **1. Node.js REPL**
- REPL stands for **Read-Eval-Print Loop**.
- It is an interactive shell to execute JavaScript code in Node.js.
- You can start it by running:
  ```
  node
  ```
- You can execute JavaScript line by line or run scripts.

---

## **2. Variables in JavaScript**
JavaScript provides three ways to declare variables:
| Keyword | Scope | Can be Updated? | Can be Redeclared? | Initialization |
|---------|-------|---------------|----------------|---------------|
| **var** | Function Scope | ✅ Yes | ✅ Yes | `undefined` (default) |
| **let** | Block Scope | ✅ Yes | ❌ No | Not initialized |
| **const** | Block Scope | ❌ No | ❌ No | Must be initialized |

### **Example:**
```js
var x = 5; 
let y = 10;
const z = 15;

x = 6;  // ✅ Allowed
y = 12; // ✅ Allowed
// z = 20; ❌ Not allowed (const cannot be changed)

console.log(x, y, z);
```

---

## **3. Primitive Data Types in JavaScript**
JavaScript has **7 primitive data types**:
1. **null** → Represents an empty or unknown value (`typeof null` is **"object"** due to historical reasons).
2. **number** → Stores integer and floating-point numbers.
3. **string** → Represents text (sequence of characters).
4. **symbol** → Creates unique identifiers.
5. **undefined** → Represents an uninitialized variable.
6. **boolean** → Represents `true` or `false`.
7. **bigint** → Used for very large numbers.

### **Example:**
```js
var a = null;  
var b = 10;  
var c = "Shubham";  
let d = Symbol("id");  
let e = undefined;  
const p = true;  
let bigNumber = 123456789012345678901234567890n;

console.log(a, b, c, d, e, p, bigNumber);
console.log(typeof a, typeof b, typeof c, typeof d, typeof e, typeof p, typeof bigNumber);
```

---

## **4. Objects in JavaScript**
- Objects store **key-value pairs** and provide more details about a single entity.
- Properties can be added dynamically.

### **Example:**
```js
const item = {
    name: "Shubham",
    age: 25
};

// Adding a new property
item.salary = "900k";

console.log(item);
```

---

## **5. Why `null` is of type `object`?**
- In JavaScript, `typeof null` returns `"object"`.
- This is an old bug in JavaScript (since its first version).
- It wasn't fixed because changing it would break existing code.

---

### **Key Takeaways**
Use `let` or `const` instead of `var` to avoid scoping issues.  
`const` ensures variables remain constant.  
Primitive data types store single values, whereas objects store key-value pairs.  
`null` is **not** an object but is mistakenly categorized as one.  

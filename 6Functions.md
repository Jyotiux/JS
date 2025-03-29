### **JavaScript Functions**  

---

## **1️ Function Declaration (Normal Function)**
- **A function is a block of code that performs a specific task.**
- **Syntax:**  
  ```js
  function functionName(parameters) {
      // Code to execute
  }
  ```
- **Example:**
  ```js
  function nice(name) {
      console.log("Hey " + name + ", you are nice.\n");
      console.log("Hey " + name + ", you are strong.\n");
  }

  var n = "Jyoti";
  nice(n);
  ```
  **🔹 Output:**
  ```
  Hey Jyoti, you are nice.
  Hey Jyoti, you are strong.
  ```

---

## **2️ Function with Parameters and Return Value**
- **Functions can take parameters and return values.**
- **Syntax:**
  ```js
  function functionName(param1, param2) {
      return param1 + param2;
  }
  ```
- **Example:**
  ```js
  function sum(a, b) {
      console.log(a + b);
  }

  sum(3, 5);
  ```
  **🔹 Output:**
  ```
  8
  ```

---

## **3️ Arrow Functions (Modern Syntax)**
- **Introduced in ES6, shorter and cleaner syntax for functions.**
- **Syntax:**
  ```js
  const functionName = (parameters) => {
      // Code to execute
  }
  ```
- **Example:**
  ```js
  const func = (x) => {
      console.log(x);
  }

  func(4);
  ```
  **🔹 Output:**
  ```
  4
  ```

---

## **4️ Function with Return Statement**
- A function can return a value instead of printing it.
- **Example:**
  ```js
  function multiply(a, b) {
      return a * b;
  }

  let result = multiply(4, 5);
  console.log(result);
  ```
  **🔹 Output:**
  ```
  20
  ```

---

## **5️ Anonymous Function (Function Without a Name)**
- **Used when the function doesn’t need a name, like in callbacks.**
- **Example:**
  ```js
  let greet = function(name) {
      return "Hello " + name;
  };

  console.log(greet("Jyoti"));
  ```
  **🔹 Output:**
  ```
  Hello Jyoti
  ```

---

## **6️ Immediately Invoked Function Expression (IIFE)**
- **A function that runs as soon as it is defined.**
- **Example:**
  ```js
  (function() {
      console.log("I am an IIFE!");
  })();
  ```
  **🔹 Output:**
  ```
  I am an IIFE!
  ```

---

### **🔹 Summary Table**
| Function Type | Syntax | Key Feature |
|--------------|--------|-------------|
| **Normal Function** | `function fn(){}` | Traditional function |
| **Function with Parameters** | `function fn(a, b){}` | Takes input values |
| **Arrow Function** | `const fn = (x) => {}` | Shorter syntax |
| **Function with Return** | `return value;` | Returns a value instead of printing |
| **Anonymous Function** | `let fn = function() {};` | No function name |
| **IIFE** | `(function() {})();` | Runs immediately |


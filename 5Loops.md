### ** Loops in JavaScript**  

---

## **1. `for` Loop**
- Used for iterating a fixed number of times.
- Syntax:  
  ```js
  for(initialization; condition; increment/decrement) {
      // Code to execute
  }
  ```
- Example:
  ```js
  let a = 1;
  for(let i = 0; i < 100; i++) {
      console.log(a + i);
  }
  ```
  **🔹 Explanation:**
  - `let i = 0` → Initializes `i` to `0`.
  - `i < 100` → Runs until `i` reaches `99`.
  - `i++` → Increments `i` in each iteration.

---

## **2. `for...in` Loop (Iterating Over Object Properties)**
- Used to iterate over **keys** of an object.
- Syntax:
  ```js
  for (const key in object) {
      // Code to execute
  }
  ```
- Example:
  ```js
  let obj = {
      name: 'John',
      role: 'Programmer',
      company: 'Ajipi'
  };

  for (const key in obj) {
      const element = obj[key];
      console.log(`${key}: ${element}`);
  }
  ```
  **🔹 Output:**
  ```
  name: John
  role: Programmer
  company: Ajipi
  ```

---

## **3. `for...of` Loop (Iterating Over Strings or Arrays)**
- Used for iterating over **values** of an iterable (string, array, etc.).
- Syntax:
  ```js
  for (const item of iterable) {
      // Code to execute
  }
  ```
- Example:
  ```js
  for (const c of "Harry") {
      console.log(c);
  }
  ```
  **🔹 Output:**
  ```
  H
  a
  r
  r
  y
  ```

---

## **4. `while` Loop**
- Executes as long as a condition is **true**.
- Syntax:
  ```js
  while (condition) {
      // Code to execute
  }
  ```
- Example:
  ```js
  let i = 0;
  while (i < 5) {
      console.log(i);
      i++; // Increment to avoid infinite loop
  }
  ```
  **🔹 Output:**
  ```
  0
  1
  2
  3
  4
  ```

---

## **5. `do...while` Loop**
- Runs the **code at least once**, even if the condition is false.
- Syntax:
  ```js
  do {
      // Code to execute
  } while (condition);
  ```
- Example:
  ```js
  let j = 0;
  do {
      console.log(j);
      j++;
  } while (j < 5);
  ```
  **🔹 Output:**
  ```
  0
  1
  2
  3
  4
  ```

---

### **🔹 Summary**
| Loop Type | Use Case | Runs at Least Once? |
|-----------|---------|---------------------|
| `for` | Known number of iterations | ❌ No |
| `for...in` | Iterates over object keys | ❌ No |
| `for...of` | Iterates over iterable values | ❌ No |
| `while` | Runs while condition is true | ❌ No |
| `do...while` | Runs at least once, then checks condition | ✅ Yes |


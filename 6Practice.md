### ** JavaScript Objects, Loops, and Functions**  

---

## **1️ Working with Objects in JavaScript**
- **An object is a collection of key-value pairs.**
- **Values can be numbers, strings, arrays, or even other objects.**
- **Example:**
  ```js
  let obj = {
      "risha": 23,
      "prisha": 24,
      "trisha": 23
  };

  console.log(obj['prisha']);  // Output: 24
  ```

---

## **2️ Looping Through an Object Using `for...in`**
- **The `for...in` loop is used to iterate over object properties.**
- **Example (Corrected version of your code):**
  ```js
  for (const key in obj) {
      if (key === "prisha") {
          console.log(obj[key]);  // Output: 24
      }
  }
  ```

---

## **3️ Using `while` Loop for Input Validation**
- **The `while` loop keeps running until a condition is met.**
- **Example:**
  ```js
  const num = 28;
  let userInput = prompt("Enter the number: ");
  // works on browser

  while (userInput != num) { 
      console.log("Try again"); 
      userInput = prompt("Enter the number: "); // Ask again
  }

  console.log("Correct value");
  ```
  🔹 **Explanation:**  
  - The loop continues until `userInput` matches `num`.  
  - It keeps asking the user for input until the correct value is entered.  

---

## **4️ Calculating Mean Using a Function**
- **A function can be used to calculate the mean of numbers.**
- **Example:**
  ```js
  function mean(a, b, c, d, e) {
      console.log((a + b + c + d + e) / 5);
  }

  mean(1, 2, 3, 4, 5);  // Output: 3
  ```

---

### **🔹 Wrap up**
| Concept | Description | Example |
|---------|------------|---------|
| **Objects** | Store key-value pairs | `{ "risha": 23 }` |
| **For...in Loop** | Iterates over object properties | `for (const key in obj) {}` |
| **While Loop** | Runs until a condition is met | `while (condition) {}` |
| **Functions** | Reusable block of code | `function mean(a,b){}` |


### **Logical Operators, Switch Case, and Conditions in JavaScript**

---

## **1. Checking if Age is Between 10 and 20 (Logical AND `&`)**
- The `&` operator is a **bitwise AND**, which might not be the intended choice for logical conditions. Instead, we should use `&&` (logical AND).

### **Example:**
```js
let age = 15;
let isok = (age > 10 && age < 20) ? "yes" : "no";
console.log(isok); // Output: "yes"
```
 **Key Takeaway:**  
 Use `&&` for logical AND operations instead of `&`.

---

## **2. Using Switch Case Statements in JavaScript**
- The `switch` statement is useful when checking a variable against multiple possible values.

### **Example:**
```js
switch (age) {
    case 15:
        console.log("Age is 15");
        break;
    case 20:
        console.log("Age is 20");
        break;
    default:
        console.log("Age is neither 15 nor 20");
}
```
 **Key Takeaway:**  
 Always include a `break;` after each case to prevent **fall-through**.  
 Add a `default:` case for handling unexpected values.

---

## **3. Checking if a Number is Divisible by 2 or 3**
- The given expression `(num % 2) || (num % 3)` is incorrect because:
  - `num % 2` or `num % 3` gives `0` (falsy) when divisible and a nonzero (truthy) value otherwise.
  - `||` (logical OR) returns the first truthy value or the last falsy value.

### **Example:**
```js
let num = 6;
let isDivis = (num % 2 === 0 || num % 3 === 0) ? "divisible" : "not divisible";
console.log(isDivis); // Output: "divisible"
```
 **Key Takeaway:**  
 Use `=== 0` to explicitly check divisibility.

---

## **4. Checking if a Number is Divisible by 2 and 3**
- The given expression `(num % 2) & (num % 3)` is incorrect because:
  - `&` is a **bitwise AND**, which does not work for logical comparisons.

### **Example:**
```js
let isDivis = (num % 2 === 0 && num % 3 === 0) ? "divisible" : "not divisible";
console.log(isDivis); // Output: "divisible"
```
 **Key Takeaway:**  
 Use `&&` (logical AND) instead of `&`.

---

## **5. Checking if Someone Can Drive Based on Age**
- Again, using `&` is incorrect here; we need `&&`.

### **Example:**
```js
let canDrive = (age > 18 && age < 75) ? "yes" : "no";
console.log(canDrive); // Output: "no" (since age = 15)
```
 **Key Takeaway:**  
 Use `&&` for logical conditions, not `&`.

---

### **🔹 Wrap up**
 **Use `&&` (Logical AND) instead of `&` in conditions.**  
 **Use `||` (Logical OR) correctly by comparing explicitly with `=== 0`.**  
 **Switch case needs `break;` to avoid fall-through.**  
 **Use `default:` in `switch` for handling unexpected values.**  

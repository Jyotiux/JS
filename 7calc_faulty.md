# **Faulty Calculator in JavaScript**  

## **🔹 Overview**
This JavaScript program simulates a **faulty calculator** that performs incorrect calculations **10% of the time**. It randomly replaces certain arithmetic operations with incorrect ones.

---

```js
function faultyCalculator(a, b, ope) {
    let num = Math.random();
    let faultyOps = { "+": "-", "*": "+", "-": "/", "/": "**" };

    // Introduce a 10% error
    if (num * 100 < 10) {
        ope = faultyOps[ope] || ope;
    }

    return eval(`${a} ${ope} ${b}`);
}

console.log(faultyCalculator(10, 2, "+"));
console.log(faultyCalculator(5, 3, "*"));
console.log(faultyCalculator(8, 4, "-"));
console.log(faultyCalculator(9, 3, "/"));
```


### **1️ Randomizing the Faulty Operations**
- The program uses `Math.random()` to **generate a random number** between 0 and 1.
- If `num * 100 < 10`, the calculator **randomly applies a faulty operation**.

### **2️ Faulty Operations Mapping**
- The faulty operations are stored in an **object (dictionary):**
  ```js
  let faultyOps = { "+": "-", "*": "+", "-": "/", "/": "**" };
  ```
  🔹 **Example of Faulty Mapping:**
  - `+` ➝ `-`
  - `*` ➝ `+`
  - `-` ➝ `/`
  - `/` ➝ `**` (Exponentiation)

### **3️ Performing the Calculation**
- If the faulty condition is met (`num * 100 < 10`), the operation is replaced using:
  ```js
  ope = faultyOps[ope] || ope;
  ```
- The `eval()` function **evaluates the expression dynamically**:
  ```js
  return eval(`${a} ${ope} ${b}`);
  ```

---

## **🔹 Example Runs**
```js
console.log(faultyCalculator(10, 2, "+"));  // Normally 12, but could be 8
console.log(faultyCalculator(5, 3, "*"));   // Normally 15, but could be 8
console.log(faultyCalculator(8, 4, "-"));   // Normally 4, but could be 2
console.log(faultyCalculator(9, 3, "/"));   // Normally 3, but could be 729 (9³)
```

### ** Outputs**
| Expression | Expected Output | Faulty Output |
|------------|---------------|--------------|
| `10 + 2` | `12` | `8` |
| `5 * 3` | `15` | `8` |
| `8 - 4` | `4` | `2` |
| `9 / 3` | `3` | `729` (since `/` turns into `**`) |

---

| Concept | Explanation |
|---------|------------|
| **`Math.random()`** | Generates a **random number** between 0 and 1 |
| **10% error condition** | `num * 100 < 10` |
| **Object for faulty operations** | Stores incorrect operation mappings |
| **Dynamic execution (`eval()`)** | Evaluates the modified expression at runtime |
| Logical OR | Ensures the correct operation if no faulty operation is defined |


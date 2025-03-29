## **JavaScript Strings & Template Literals**

### **1️ Template Literals (` `)**
- Template literals allow **multi-line strings** and **string interpolation**.
- Variables inside the string can be inserted using **`${}`**.

```js
let name = "Jyoti";
console.log(`My name is "${name}"`);
```
**Output:**
```
My name is "Jyoti"
```

---

### **2️ String Methods**
####  **Convert to Uppercase & Lowercase**
```js
let str = "Jyoti";
console.log(str.toUpperCase()); // "JYOTI"
console.log(str.toLowerCase()); // "jyoti"
```

####  **Find Length of a String**
```js
console.log(str.length); // 5
```

####  **Extract Part of a String (Slice)**
```js
console.log(str.slice(0, 3)); // "Jyo"
```
- `slice(start, end)`: Extracts characters **from start index to end index (not included)**.

####  **Replace a Part of the String**
```js
console.log(str.replace("Jyoti", "Joshi")); // "Joshi"
```
- ** Note:** It replaces **only the first occurrence**.

####  **Concatenate Strings**
```js
console.log(str.concat(" Joshi")); // "Jyoti Joshi"
```

####  **Remove Whitespace (Trim)**
```js
let str2 = "  Jyoti  ";
console.log(str2.trim()); // "Jyoti"
```

---

### **3️ Important String Properties**
- **Strings are immutable** → Modifying them creates a new string.
- **Strings are indexed** → You can access characters using index positions.

```js
console.log(str[0]); // "J"
console.log(str[str.length - 1]); // "i"
```

---

Here's the updated table with additional string methods:  

### **Some points**  
| Method | Description | Example | Output |  
|--------|------------|---------|--------|  
| `toUpperCase()` | Converts string to uppercase | `"Jyoti".toUpperCase()` | `"JYOTI"` |  
| `toLowerCase()` | Converts string to lowercase | `"Jyoti".toLowerCase()` | `"jyoti"` |  
| `length` | Returns string length | `"Jyoti".length` | `5` |  
| `slice(start, end)` | Extracts part of the string | `"Jyoti".slice(0,3)` | `"Jyo"` |  
| `substring(start, end)` | Similar to `slice()`, but does not accept negative indexes | `"Jyoti".substring(1,3)` | `"yo"` |  
| `substr(start, length)` | Extracts part of a string, specifying length | `"Jyoti".substr(1,2)` | `"yo"` |  
| `replace("old", "new")` | Replaces part of the string (first occurrence only) | `"Jyoti".replace("Jyoti", "Joshi")` | `"Joshi"` |  
| `replaceAll("old", "new")` | Replaces all occurrences of a substring | `"Jyoti Jyoti".replaceAll("Jyoti", "Joshi")` | `"Joshi Joshi"` |  
| `concat("str")` | Concatenates strings | `"Jyoti".concat(" Joshi")` | `"Jyoti Joshi"` |  
| `trim()` | Removes whitespace from both sides | `"  Jyoti  ".trim()` | `"Jyoti"` |  
| `trimStart()` | Removes whitespace from the start | `"  Jyoti".trimStart()` | `"Jyoti"` |  
| `trimEnd()` | Removes whitespace from the end | `"Jyoti  ".trimEnd()` | `"Jyoti"` |  
| `charAt(index)` | Returns the character at the specified index | `"Jyoti".charAt(2)` | `"o"` |  
| `charCodeAt(index)` | Returns the ASCII/Unicode of the character at the specified index | `"Jyoti".charCodeAt(2)` | `111` (ASCII for 'o') |  
| `split("separator")` | Splits a string into an array based on a separator | `"Jyoti Joshi".split(" ")` | `["Jyoti", "Joshi"]` |  
| `includes("str")` | Checks if a string contains another string | `"Jyoti".includes("yoti")` | `true` |  
| `startsWith("str")` | Checks if a string starts with a given substring | `"Jyoti".startsWith("J")` | `true` |  
| `endsWith("str")` | Checks if a string ends with a given substring | `"Jyoti".endsWith("i")` | `true` |  
| `repeat(n)` | Repeats the string `n` times | `"Hi ".repeat(3)` | `"Hi Hi Hi "` |  




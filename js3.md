### **JavaScript Data Types and Objects**

---

## **1. String Concatenation with Numbers**
- When you add a number to a string using `+`, JavaScript converts the number into a string and performs **concatenation** instead of arithmetic addition.

### **Example:**
```js
var str = "Hello";
str = str + 1;
console.log(str); // Output: "Hello1"
console.log(typeof str); // Output: "string"
```
 **Key Takeaway:** `+` operator with a string converts the number into a string and concatenates.

---

## **2. Using `typeof` Operator**
- The `typeof` operator helps determine the data type of a variable.

### **Example:**
```js
console.log(typeof str); // Output: "string"
```
 **Key Takeaway:** Always use `typeof` to check variable types, especially when handling dynamic values.

---

## **3. Working with `const` Objects**
- `const` only prevents reassignment of the **whole object**, but **individual properties** inside the object can be modified.

### **Example:**
```js
const obj = { name: "John" };
obj.name = 1; // Allowed, modifying property
console.log(obj); // Output: { name: 1 }
```
 **Key Takeaway:** `const` prevents reassignment but allows modification of object properties.

---

## **4. Adding a New Key to an Object**
- New properties can be added to a `const` object.

### **Example:**
```js
obj.roll = 34;
console.log(obj); // Output: { name: 1, roll: 34 }
```
 **Key Takeaway:** You **cannot** reassign a `const` object but can modify and add properties.

---

## **5. Creating a Dictionary (Object)**
- Objects in JavaScript can be used as dictionaries to store key-value pairs.

### **Example:**
```js
var dictionary = {
    "apple": "fruit",
    "car": "vehicle",
    "tree": "plant",
    "house": "building",
    "book": "reading material"
};
console.log(dictionary);
```
 **Key Takeaway:** Objects in JavaScript can serve as dictionaries for key-value mappings.

---

### **🔹 Some more points**
 **String + Number → Converts Number to String (Concatenation).**  
 **`typeof` Operator → Helps Check Data Type.**  
 **`const` Objects → Can Modify Properties But Not Reassign Entire Object.**  
 **Objects Can Be Used as Dictionaries.**  

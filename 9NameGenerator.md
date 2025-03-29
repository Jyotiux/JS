### **Business Name Generator Code**  

// Business name generator by combining list of adjectives,name of shops and word
```js
let adj=['Grand','Artistic','Colourful'];
let names=['Hiccup','Gear','Delight']
let word=['Store','Shop','Market']

let num=Math.floor(Math.random()*adj.length);
let num2=Math.floor(Math.random()*names.length);
let num3=Math.floor(Math.random()*word.length);

let businessName=adj[num]+' '+names[num2]+' '+word[num3];
console.log(businessName);
```

#### **Concepts Used:**
1. **Arrays**:  
   - `adj`, `names`, and `word` are arrays storing lists of adjectives, names, and words.
   
2. **Generating Random Numbers**:  
   - `Math.random()` generates a random decimal between `0` and `1`.
   - Multiplying by `array.length` ensures the number falls within the valid index range.
   - `Math.floor()` rounds it down to get a valid index (`0`, `1`, or `2` in this case).

3. **String Concatenation**:  
   - `adj[num] + ' ' + names[num2] + ' ' + word[num3]` creates a business name by combining a random adjective, name, and word.

---




### **Example Outputs:**
- **"Artistic Gear Market"**  
- **"Grand Delight Store"**  
- **"Colourful Hiccup Shop"**  


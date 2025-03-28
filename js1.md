
1 **JavaScript in Frontend vs Backend:**  
   - **Frontend:** Runs in the browser and manipulates web pages (e.g., DOM manipulation, event handling).  
   - **Backend:** Runs on the server (e.g., using Node.js to handle server-side logic).  

2️ **Executing JavaScript:**  
   - In the browser: JavaScript runs inside `<script>` tags or external JS files linked via `<script src="js1.js"></script>`.  
   - In Node.js: Runs JavaScript in the terminal (`node filename.js`), but it won’t access browser-specific elements like `document`.  

3️ **Basic Browser Interactions:**  
   - `alert("Hello");` → Displays an alert box.  
   - `prompt("Enter your number");` → Asks for user input in a popup.  
   - `console.log("Hello");` → Outputs messages in the console for debugging.  

4️ **DOM Manipulation (Document Object Model):**  
   - `document.title = "Hey I am good";` → Changes the page title dynamically.  
   - `document.body.style.backgroundColor = "yellow";` → Changes the background color.  
   - **(Error in your code: `document.title.body.style.backgroundColor` should be `document.body.style.backgroundColor`)**  


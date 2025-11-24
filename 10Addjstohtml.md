
# Adding JavaScript in HTML — Notes

**1. Inline JavaScript**

* Write JS directly in HTML element attributes like `onclick`, `onmouseover`.
* Example: `<button onclick="alert('Clicked!')">Click Here</button>`
* Not recommended for large projects due to poor maintainability.

**2. Internal JavaScript**

* Use `<script>` tag inside `<head>` or `<body>`.
* Inside `<head>`: script runs before page content loads.
* Inside `<body>`: script runs after DOM elements are available.
* Example:

```html
<script>
function myFun() {
  document.getElementById("demo").innerHTML = "Content changed!";
}
</script>
```

**3. External JavaScript**

* Place JS in a separate `.js` file and link it using `<script src="file.js"></script>`.
* Advantages: faster page load (cached), better readability, reusable, separation of concerns.

**4. Async and Defer**

* `async`: downloads and executes script as soon as available, may block HTML rendering.
* `defer`: delays execution until after HTML parsing, does not block DOM.
* Example:

```html
<script src="script.js" async></script>
<script src="script.js" defer></script>
```

**5. Referencing External JS Files**

* Full URL: `src="https://example.com/script.js"`
* File path: `src="/js/script.js"`
* Same folder: `src="script.js"`

**Tip:**

* Inline: small scripts, quick testing
* Internal: simple projects
* External: scalable and maintainable projects

---

#  DOM — Document Object Model

#### 1. Tree Structure of HTML-Based Websites

HTML documents are structured as a tree — the **DOM Tree**.

* Each tag becomes a **node** in the tree.
* The root is `document`
* Nodes can be: **elements**, **attributes**, or **text**

**Visual Example:**

```html
<html>
  <body>
    <h1>Hello</h1>
    <p>World</p>
  </body>
</html>
```

DOM Tree:

```
document
 └── html
     └── body
         ├── h1 → "Hello"
         └── p → "World"
```

---

#### 2. Traversing the Document

You use **JavaScript** to access and modify nodes via the `document` object.

**Selection Methods:**

```js
document.getElementById("main")
document.getElementsByClassName("item")
document.getElementsByTagName("p")
document.querySelector("h1")
document.querySelectorAll(".btn")
```

**Navigating:**

```js
element.parentElement
element.children
element.firstElementChild
element.nextElementSibling
```

---

#### 3. Separation of Concerns & Best Practices

* **HTML** → structure only
* **CSS** → styling only
* **JavaScript** → behavior only

**Why?**

* Easier to debug
* Clean code
* Reusable components

**Example:**

```html
<!-- HTML -->
<button id="clickMe">Click</button>
```

```css
/* CSS */
#clickMe { color: blue; }
```

```js
// JS
document.getElementById("clickMe").addEventListener("click", function() {
  alert("Clicked");
});
```

Avoid inline JS like:

```html
<button onclick="alert('bad practice')">Click</button>  <!-- NOT RECOMMENDED -->
```

---

#### 4. Manipulating HTML with the DOM

**Changing Content:**

```js
document.querySelector("h1").textContent = "New Title";
```

**Changing Attributes:**

```js
document.querySelector("img").setAttribute("src", "new.jpg");
```

**Changing Styles:**

```js
document.querySelector("h1").style.color = "red";
```

**Adding Classes:**

```js
element.classList.add("highlight");
element.classList.remove("highlight");
element.classList.toggle("dark-mode");
```

**Creating and Appending Elements:**

```js
const newPara = document.createElement("p");
newPara.textContent = "Hello!";
document.body.appendChild(newPara);
```

---

### Summary

| Concept         | Method/Usage                      |
| --------------- | --------------------------------- |
| Access Elements | `getElementById`, `querySelector` |
| Modify Content  | `textContent`, `innerHTML`        |
| Change Style    | `style`, `classList`              |
| Best Practice   | Keep JS/CSS/HTML separate         |
| DOM Structure   | Tree-like, rooted at `document`   |

<footer>TO BE CONT...</footer>

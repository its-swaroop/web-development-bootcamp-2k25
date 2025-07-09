#  JAVASCRIPT + ES6 — Complete Language Fundamentals


#### A. Comparing JavaScript with Markup & Stylesheet Languages

| Language   | Role                  |
| ---------- | --------------------- |
| HTML       | Structure (markup)    |
| CSS        | Presentation (styles) |
| JavaScript | Behavior (scripting)  |

JS is a **scripting language** — used to manipulate HTML/CSS and build interactivity. Unlike markup/styling, it’s logic-based, supports programming constructs, variables, functions, control flow, etc.

---

#### B. JavaScript Overview

* Client-side and server-side scripting
* Runs in browser (via engine like V8 in Chrome)
* Used for DOM manipulation, event handling, animation, API calls, backend (Node.js), etc.

---

#### C. Code Editors and IDEs

* **Editors:** VS Code (recommended), Sublime Text
* **IDEs:** WebStorm, Eclipse (heavyweight)
* VS Code + Prettier + ESLint = Clean JS workflow

---

### SYNTAX & CORE CONCEPTS

#### 1. Variables and Scope

```js
let name = "Ruth";       // block-scoped, reassignable
const PI = 3.14;         // block-scoped, constant
var old = 20;            // function-scoped (avoid)
```

---

#### 2. Data Types

| Type      | Example            |
| --------- | ------------------ |
| String    | `"Hello"`          |
| Number    | `42`, `3.14`       |
| Boolean   | `true`, `false`    |
| Null      | `null`             |
| Undefined | `let x;`           |
| Symbol    | `Symbol("id")`     |
| Object    | `{ key: "value" }` |
| Array     | `[1, 2, 3]`        |

---

#### 3. Operators

* **Arithmetic:** `+ - * / % **`
* **Comparison:** `===`, `!==`, `>`, `<`, `>=`, `<=`
* **Logical:** `&&`, `||`, `!`

---

#### 4. Control Structures

```js
if (x > 0) {
  console.log("Positive");
} else {
  console.log("Not positive");
}
```

**Loops:**

```js
for (let i = 0; i < 5; i++) { }
while (condition) { }
for (let val of array) { }        // array values
for (let key in object) { }       // object keys
```

---

#### 5. Functions

**Declaration:**

```js
function greet(name) {
  return `Hello ${name}`;
}
```

**Expression:**

```js
const greet = function(name) { return `Hello ${name}`; };
```

**Arrow:**

```js
const greet = name => `Hello ${name}`;
```

**Scope & Closures:**

* Functions remember variables from their outer scope

```js
function outer() {
  let x = 10;
  return function inner() { return x; };
}
```

---

#### 6. Higher-Order Functions

* Functions that **take or return other functions**

```js
function operate(fn, x, y) {
  return fn(x, y);
}

const add = (a, b) => a + b;
operate(add, 2, 3); // 5
```

**Array Methods:**

```js
array.map(fn)
array.filter(fn)
array.reduce(fn)
```

---

#### 7. Arrays

```js
const arr = [1, 2, 3];
arr.push(4);             // Add
arr.pop();               // Remove last
arr.shift();             // Remove first
arr.slice(1, 3);         // Returns part
arr.concat([5, 6]);      // Combine
arr.indexOf(2);
arr.lastIndexOf(2);
```

**Spread Syntax:**

```js
const arr2 = [...arr, 10];         // Spread into new array
```

---

#### 8. Object-Oriented JavaScript

**Object Literal:**

```js
const user = { name: "Ruth", age: 25 };
```

**Constructor Function:**

```js
function Person(name) {
  this.name = name;
}
const p1 = new Person("Ruth");
```

**Class Syntax:**

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    return `${this.name} speaks`;
  }
}
class Dog extends Animal {
  speak() {
    return super.speak() + " Woof!";
  }
}
```

---

#### 9. Object/Array Manipulation Methods

```js
Object.keys(user);           // ['name', 'age']
Object.values(user);         // ['Ruth', 25]
Object.assign({}, user);     // Clone object
```

**for...in** for objects, **for...of** for arrays

---

### Summary Table

| Topic                     | Usage                          |
| ------------------------- | ------------------------------ |
| `let`, `const`            | Modern, block-scoped variables |
| `map`, `filter`, `reduce` | Higher-order array ops         |
| `for...in`, `for...of`    | Object keys and array values   |
| Arrow functions           | Short syntax, lexical `this`   |
| Class & `super`           | OOP in JS                      |
| Spread syntax             | Array/object expansion         |

<footer>TO BE CONT...</footer>

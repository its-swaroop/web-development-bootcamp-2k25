# MODULE 6.0: NODE.JS — BACKEND WITH SERVER-SIDE JAVASCRIPT

#### 1. What Is Node.js?

* Runtime environment for executing **JavaScript outside the browser**
* Built on **Chrome's V8 engine**
* Enables JavaScript for **server-side** applications

---

#### 2. Key Components of Back-End with Node.js (MVC-ready)

**MVC = Model-View-Controller Architecture**

| Layer      | Responsibility                               |
| ---------- | -------------------------------------------- |
| Model      | Data layer (DB interaction, logic)           |
| View       | Frontend (optional in REST APIs)             |
| Controller | Request handler / logic between view & model |

In Node.js, **Express.js** is used as the MVC web framework (you’ll cover that in next module).

---

#### 3. Core JavaScript in Backend Context

* Same JS fundamentals: data types, objects, classes, OOP
* More emphasis on **objects as data structures** (for JSON handling, APIs)
* Example class:

```js
class User {
  constructor(name) {
    this.name = name;
  }
  greet() {
    return `Hello, ${this.name}`;
  }
}
```

---

#### 4. Node.js on the Command Line

**Run JS files:**

```bash
node app.js
```

**REPL mode (interactive terminal):**

```bash
node
> 2 + 2
```

**Exit:** `Ctrl + C` twice

---

#### 5. NPM (Node Package Manager)

* Package manager for Node modules
* Comes installed with Node.js

**Common Commands:**

```bash
npm init -y                    # Initialize project
npm install express            # Install package
npm install --save-dev nodemon # Dev dependency
npm uninstall express
```

---

#### 6. JavaScript Build Process

**Goal:** Automate and optimize

* Transpile ES6+ code (via Babel)
* Minify, bundle (via Webpack, Parcel)
* Nodemon to auto-restart on save:

```bash
npm install --save-dev nodemon
```

Update `package.json`:

```json
"scripts": {
  "start": "node app.js",
  "dev": "nodemon app.js"
}
```

---

#### 7. Event Loop & Event Emitters

* **Event loop** handles async operations (non-blocking)
* **Emitter pattern** is core to Node

```js
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('greet', () => {
  console.log('Hello event received!');
});

emitter.emit('greet');
```

---

#### 8. File System Interaction

Using `fs` module:

```js
const fs = require('fs');

fs.writeFileSync('data.txt', 'Hello World');
let data = fs.readFileSync('data.txt', 'utf-8');
console.log(data);
```

**Async versions:**

```js
fs.writeFile('file.txt', 'Hello', err => {});
fs.readFile('file.txt', 'utf-8', (err, data) => {});
```

---

#### 9. Modules in Node.js

* Every JS file is treated as a **module**
* Use `require()` to import
* Use `module.exports` to export

```js
// math.js
function add(a, b) { return a + b; }
module.exports = add;

// app.js
const add = require('./math');
console.log(add(2, 3));
```

---

#### 10. Native Node Drivers

* Built-in modules that don't need installation
* Examples:

  * `fs` (file system)
  * `http` (create servers)
  * `path` (file paths)
  * `os` (system info)
  * `events` (event-driven code)
  * `url`, `crypto`, etc.

---

### Summary

| Topic               | Command or Concept                    |
| ------------------- | ------------------------------------- |
| Run Node            | `node app.js`                         |
| Package Manager     | `npm install`, `npm init`             |
| Event Emitters      | `events` module                       |
| File Handling       | `fs.readFileSync()`, `fs.writeFile()` |
| Module System       | `require()`, `module.exports`         |
| Backend JS Concepts | OOP, classes, methods, JSON, logic    |
| Build Tools         | `nodemon`, `babel`, `webpack`         |

---

<footer>TO BE CONT....</footer>

# MODULE 6.1: EXPRESS.JS — WEB FRAMEWORK FOR NODE

#### 1. Installing and Using Express in Node Apps

Express is a lightweight **web application framework** for Node.js. It simplifies routing, middleware, and server creation.

**Install Express:**

```bash
npm install express
```

**Basic Server Setup:**

```js
const express = require('express');
const app = express();
const port = 3000;

app.listen(port, () => {
  console.log(`Server running on http://localhost:${port}`);
});
```

---

#### 2. Creating Node + Express Servers

**Basic Route Handling:**

```js
app.get('/', (req, res) => {
  res.send('Hello, World');
});
```

**Other HTTP methods:**

```js
app.post('/submit', (req, res) => { ... });
app.put('/update', (req, res) => { ... });
app.delete('/delete/:id', (req, res) => { ... });
```

---

#### 3. RESTful Routing with Express

REST = Representational State Transfer
Routes are structured by **resource + method**

**Example: Resource: `/users`**

| Method | Route        | Action         |
| ------ | ------------ | -------------- |
| GET    | `/users`     | Read all users |
| POST   | `/users`     | Create a user  |
| GET    | `/users/:id` | Read 1 user    |
| PUT    | `/users/:id` | Update user    |
| DELETE | `/users/:id` | Delete user    |

**Route Example:**

```js
app.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ID: ${userId}`);
});
```

---

#### 4. Middleware in Express

**Middleware = Function that runs during the request lifecycle**

**Use Cases:**

* Logging
* Parsing body
* Authentication
* Error handling

**Example:**

```js
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // pass control to next middleware/route
});
```

**Built-in Middleware:**

```js
app.use(express.static('public'));      // serve static files
app.use(express.json());                // parse JSON body
app.use(express.urlencoded({ extended: true })); // parse form data
```

**Third-party Example:**

```bash
npm install morgan
```

```js
const morgan = require('morgan');
app.use(morgan('dev'));
```

---

### Summary

| Feature           | Usage Example                            |
| ----------------- | ---------------------------------------- |
| Server Creation   | `app.listen(port)`                       |
| Routing           | `app.get()`, `app.post()`                |
| RESTful Structure | `/resource`, `/resource/:id`             |
| Middleware Use    | `app.use()`, custom/third-party handlers |

<footer>TO BE CONT....</footer>

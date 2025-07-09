# MODULE 8.1: BUILDING RESTful APIs — Backend Logic for the Web



#### 1. REST Principles — What & Why

**REST = Representational State Transfer**

Guiding principles of REST API design:

| Principle         | Meaning                                          |
| ----------------- | ------------------------------------------------ |
| Stateless         | Each request is independent (no session)         |
| Resource-based    | Focus on **nouns**, not actions (e.g., `/users`) |
| Uniform Interface | Use standard HTTP methods (GET, POST...)         |
| Structured Data   | Use **JSON** for request/response bodies         |

REST is about designing **clean, predictable, scalable** APIs.

---

#### 2. MongoDB GUI — Robo 3T

* **Robo 3T** is a graphical interface for MongoDB
* Helps you view/edit documents, collections, and databases easily

**Usage:**

* Connect using the MongoDB URI (`mongodb://...`)
* Browse `databases → collections → documents`
* Run **queries** using Mongo shell syntax:

```js
db.users.find({ name: "Ruth" });
db.posts.insertOne({ title: "Node REST", userId: 1 });
```

Useful for debugging, testing, and inspecting database changes while building APIs.

---

#### 3. Implementing HTTP Methods with Express + MongoDB

| Method | Action         | Endpoint Example       |
| ------ | -------------- | ---------------------- |
| GET    | Read data      | `/items`, `/items/:id` |
| POST   | Create new     | `/items`               |
| PUT    | Replace entire | `/items/:id`           |
| PATCH  | Update part    | `/items/:id`           |
| DELETE | Remove         | `/items/:id`           |

**Example: Basic Express API with Mongoose**

```js
const express = require('express');
const router = express.Router();
const Item = require('../models/item');

// GET all items
router.get('/', async (req, res) => {
  const items = await Item.find();
  res.json(items);
});

// POST new item
router.post('/', async (req, res) => {
  const newItem = new Item(req.body);
  await newItem.save();
  res.status(201).json(newItem);
});

// PUT replace item
router.put('/:id', async (req, res) => {
  const updated = await Item.findByIdAndUpdate(req.params.id, req.body, { new: true, overwrite: true });
  res.json(updated);
});

// PATCH partial update
router.patch('/:id', async (req, res) => {
  const updated = await Item.findByIdAndUpdate(req.params.id, req.body, { new: true });
  res.json(updated);
});

// DELETE item
router.delete('/:id', async (req, res) => {
  await Item.findByIdAndDelete(req.params.id);
  res.sendStatus(204);
});
```

---

#### 4. Chained Route Handlers in Express

Group routes for the same endpoint:

```js
router.route('/items/:id')
  .get(async (req, res) => { /* Read */ })
  .put(async (req, res) => { /* Replace */ })
  .patch(async (req, res) => { /* Update */ })
  .delete(async (req, res) => { /* Delete */ });
```

Cleaner, DRY (Don’t Repeat Yourself), and RESTful.

---

### Summary

| Concept         | Key Tool / Practice                         |
| --------------- | ------------------------------------------- |
| REST Principles | Stateless, resource-based, JSON             |
| MongoDB GUI     | Robo 3T for visual query & document editing |
| CRUD Methods    | `GET`, `POST`, `PUT`, `PATCH`, `DELETE`     |
| API Logic       | Express routers + Mongoose queries          |
| Route Chaining  | `.route().get().post().put()` syntax        |

<footer>TO BE CONT...</footer>

# MODULE 7.0: DATABASES — DATA MODELING & RELATIONSHIPS


#### 1. Relational Databases

* **Store data in tables (rows + columns)**
* Use **SQL (Structured Query Language)** for operations
* Example systems: PostgreSQL, MySQL, SQLite

**Table Example:**

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT,
  email TEXT UNIQUE
);
```

**Key Concepts:**

* **Primary Key** – Unique ID for each row
* **Foreign Key** – Links to another table’s primary key
* **Normalization** – Structuring tables to reduce redundancy

---

#### 2. Data Relationships

| Type         | Description                                  | Example                          |
| ------------ | -------------------------------------------- | -------------------------------- |
| One-to-One   | One record matches one in another table      | User & Profile                   |
| One-to-Many  | One record linked to many in another table   | Author → Posts                   |
| Many-to-Many | Many records relate to many (via join table) | Students ↔ Courses (Enrollments) |

---

#### 3. Designing a Data Model

**Steps:**

1. Identify **entities** (User, Post, Comment)
2. Define **attributes** (name, content, createdAt)
3. Define **relationships**
4. Choose keys: primary, foreign

**Example (Blog App):**

* `users`: id, name
* `posts`: id, title, user\_id
* `comments`: id, body, post\_id, user\_id

---

#### 4. Entity Relationship Modelling (ERM)

A visual diagram showing:

* Tables as **entities**
* Columns as **attributes**
* Arrows for **relationships**

**Helps:**

* Clarify schema before writing SQL
* Prevent design flaws

Tools: dbdiagram.io, Lucidchart

---

#### 5. Object-Relational Mapping (ORM)

* ORMs let you **interact with databases using objects**, not raw SQL
* You define models/classes, and ORM converts them into SQL queries

**Popular ORM for Node:**

* **Sequelize** (for PostgreSQL, MySQL, SQLite)

**Example (Sequelize):**

```js
const User = sequelize.define('User', {
  name: Sequelize.STRING,
  email: Sequelize.STRING
});

const Post = sequelize.define('Post', {
  title: Sequelize.STRING
});

User.hasMany(Post);
Post.belongsTo(User);
```

---

#### 6. Alternative Databases (NoSQL)

| DB Type  | Structure         | Use Case                          |
| -------- | ----------------- | --------------------------------- |
| MongoDB  | Document (JSON)   | Flexible schema, fast prototyping |
| Redis    | Key-value store   | Caching, session storage          |
| Firebase | Realtime database | Mobile/web apps with real-time UX |

Use NoSQL when:

* Schema is dynamic
* High write volume
* Data is deeply nested or denormalized

---

### Summary

| Topic          | Summary                                  |
| -------------- | ---------------------------------------- |
| Relational DBs | Tables, rows, SQL                        |
| Relationships  | 1:1, 1\:M, M\:M                          |
| Data Modeling  | Entities, attributes, keys               |
| ER Modelling   | Visualize structure & flow               |
| ORM            | Classes → SQL (via Sequelize)            |
| NoSQL          | Flexible, document-based (e.g., MongoDB) |

<footer>TO BE CONT...</footer>

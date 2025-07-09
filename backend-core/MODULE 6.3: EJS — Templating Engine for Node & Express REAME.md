# MODULE 6.3: EJS — Templating Engine for Node & Express

#### 1. What Is EJS?

* **EJS = Embedded JavaScript**
* Server-side **templating engine** that lets you write HTML + JS together
* Used to render **dynamic content** in web pages
* Compatible with Express

---

#### 2. Setting Up EJS with Express

**Install:**

```bash
npm install ejs
```

**Setup in `app.js`:**

```js
app.set('view engine', 'ejs');
app.set('views', 'views'); // optional, default is `/views`
```

**Folder structure:**

```
project/
├── views/
│   └── home.ejs
└── app.js
```

---

#### 3. Templating with EJS

EJS templates look like HTML, with embedded JS:

```ejs
<h1>Welcome <%= userName %></h1>
```

**Output tags:**

* `<%= %>` → Escaped output (safe HTML)
* `<%- %>` → Unescaped output (renders raw HTML)
* `<% %>` → Run JS code (loops, conditionals)

---

#### 4. Running JS Code in Templates

```ejs
<ul>
  <% for(let i = 0; i < items.length; i++) { %>
    <li><%= items[i] %></li>
  <% } %>
</ul>

<% if (loggedIn) { %>
  <p>Welcome back!</p>
<% } else { %>
  <p>Please log in.</p>
<% } %>
```

---

#### 5. Passing Data from Server to Template

**In Express route:**

```js
app.get('/', (req, res) => {
  res.render('home', { userName: "Ruth", loggedIn: true });
});
```

**In EJS:**

```ejs
<h2>Hello <%= userName %></h2>
```

You can pass:

* Strings
* Arrays
* Objects
* Booleans

---

#### 6. Layouts and Partials in EJS

Use **partials** for reusable sections (like headers, footers).

**Create partials:**

```
views/partials/header.ejs
views/partials/footer.ejs
```

**Include in main template:**

```ejs
<%- include('partials/header') %>

<h1>Page Content</h1>

<%- include('partials/footer') %>
```

No need to pass variables again if included from the same route.

---

### Summary

| Feature         | Purpose                                |
| --------------- | -------------------------------------- |
| `<%= %>`        | Output escaped data (safe)             |
| `<% %>`         | Run JS (logic/loops)                   |
| `res.render()`  | Render template with data from backend |
| Partials        | Reuse headers, navbars, footers        |
| Views Directory | Holds all `.ejs` files                 |

<footer>TO BE CONT...</footer>

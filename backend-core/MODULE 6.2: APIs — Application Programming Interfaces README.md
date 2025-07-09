# MODULE 6.2: APIs — Application Programming Interfaces

#### 1. What Is an API?

* API = **Application Programming Interface**
* In web dev, it allows apps to **communicate over the internet** using HTTP
* APIs expose **endpoints** that accept and return data (usually in JSON)

**Example:**

```
GET https://api.weather.com/today?city=Pune
```

→ Response:

```json
{ "city": "Pune", "temp": 29 }
```

---

#### 2. HTTP in Depth

| Method | Purpose             |
| ------ | ------------------- |
| GET    | Retrieve data       |
| POST   | Send new data       |
| PUT    | Update data         |
| PATCH  | Modify part of data |
| DELETE | Remove data         |

**Status Codes:**

* 200 OK
* 201 Created
* 400 Bad Request
* 401 Unauthorized
* 404 Not Found
* 500 Internal Server Error

**Headers:**

* `Content-Type: application/json`
* `Authorization: Bearer <token>`

---

#### 3. Calling APIs (Client Side)

**Using `fetch` (browser):**

```js
fetch("https://api.example.com/data")
  .then(res => res.json())
  .then(data => console.log(data));
```

**Using `axios` (Node/React):**

```js
import axios from 'axios';

axios.get("https://api.example.com/data")
  .then(response => console.log(response.data));
```

---

#### 4. Reading API Documentation

Look for:

* **Base URL**
* **Endpoint paths**
* **Required parameters** (query, path, headers, body)
* **Authentication method**
* **Response format**

**Example from OpenWeatherMap:**

```http
GET /data/2.5/weather?q=London&appid=YOUR_API_KEY
```

---

#### 5. Basic API Authentication

| Method           | Description                             |
| ---------------- | --------------------------------------- |
| API Key          | Append to URL or headers                |
| Bearer Token     | `Authorization: Bearer <token>`         |
| Basic Auth       | `Authorization: Basic <base64 user:pw>` |
| OAuth (Advanced) | Used in secure app-user flows           |

---

#### 6. Server-to-Server Communication

**Backend fetching data from another API:**

```js
const axios = require('axios');

app.get('/weather', async (req, res) => {
  const result = await axios.get('https://api.weather.com/today');
  res.json(result.data);
});
```

Used in:

* Microservices
* Proxy servers
* Serverless functions
* Backend to database/API integrations

---

#### 7. JSON vs XML

| Feature     | JSON                    | XML                       |
| ----------- | ----------------------- | ------------------------- |
| Format      | `{ "key": "value" }`    | `<key>value</key>`        |
| Readability | Human-friendly, concise | Verbose                   |
| Use Today   | 99% of modern APIs      | Legacy/Enterprise systems |
| MIME Type   | `application/json`      | `application/xml`         |

**Use JSON unless specifically required to use XML.**

---

### Summary

| Concept         | Key Point                            |
| --------------- | ------------------------------------ |
| What is API     | Interface to access data or services |
| HTTP            | GET/POST/PUT/DELETE + status codes   |
| Fetch API/axios | JS methods to call APIs              |
| Auth            | API key, token, basic auth           |
| JSON > XML      | JSON is the standard format today    |
| Server-server   | Use `axios`, `fetch`, or `https`     |

<footer> TO BE CONT...</footer>

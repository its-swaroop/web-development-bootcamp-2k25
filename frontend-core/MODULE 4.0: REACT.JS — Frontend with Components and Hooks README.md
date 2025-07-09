#  MODULE 4.0: REACT.JS — Frontend with Components and Hooks

#### 1. Introduction to React

* A **JavaScript library** for building user interfaces
* Component-based, declarative, and efficient
* Built and maintained by Facebook
* Ideal for SPAs (Single Page Applications)

---

#### 2. React Components

**Types:**

* **Functional Components** (modern, preferred)
* **Class Components** (legacy, less common now)

**Example (Functional):**

```js
function Greeting() {
  return <h1>Hello, React</h1>;
}
```

**Usage:**

```js
<Greeting />
```

**When to use Components:**

* Reusable UI parts (buttons, cards, navbars, etc.)
* Modularize large UIs

---

#### 3. JSX Syntax

* JSX is **JavaScript + HTML-like syntax**
* Compiled by Babel into `React.createElement()` calls
* Must return a **single parent element**

```js
const element = <h1>Hello, world!</h1>;
```

**JSX Rules:**

* Wrap multiple elements inside a parent tag
* Use `className` instead of `class`
* Use `{}` for JS expressions

```js
const name = "Ruth";
<h1>Hello, {name}</h1>
```

---

#### 4. Props (Properties)

* Props allow **data to flow** from parent to child
* Passed as attributes to a component

**Example:**

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
<Welcome name="Ruth" />
```

**Props are read-only** in child components.

---

#### 5. React DOM

* React DOM efficiently updates the real DOM using a **virtual DOM**
* Only changed parts are re-rendered
* Makes React fast and dynamic

**Rendering:**

```js
ReactDOM.render(<App />, document.getElementById('root'));
```

---

#### 6. State Management

* State holds **dynamic data** for components

**Using useState Hook (functional component):**

```js
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
    </div>
  );
}
```

* State changes cause re-rendering

---

#### 7. React Hooks

**Common Hooks:**

* `useState()` — to hold local state
* `useEffect()` — to run side effects (similar to lifecycle methods)

```js
useEffect(() => {
  console.log("Component mounted or updated");
}, [dependency]);
```

* Hooks can **only be used in functional components**
* Must be **called at the top level**

---

#### 8. Conditional Rendering

Render different components or elements based on condition:

**Using if/else:**

```js
{isLoggedIn ? <Logout /> : <Login />}
```

**Using &&:**

```js
{messages.length > 0 && <Notification />}
```

---

#### 9. Class vs Functional Components

| Feature            | Class Component                 | Functional Component |
| ------------------ | ------------------------------- | -------------------- |
| Syntax             | `extends React.Component`       | Plain function       |
| State              | `this.state`, `this.setState()` | `useState()`         |
| Lifecycle methods  | `componentDidMount()`, etc.     | `useEffect()`        |
| Verbose            | More                            | Less                 |
| Preferred in 2024+ | No                              | Yes (with Hooks)     |

---

### Summary

| Topic               | Example or Use                   |
| ------------------- | -------------------------------- |
| JSX                 | HTML-like syntax in JS files     |
| Component           | Reusable UI block                |
| Props               | Data passed from parent to child |
| State               | Internal component data          |
| useState, useEffect | Hooks for state and side effects |
| Conditional render  | `if`, `? :`, `&&`                |
| Functional > Class  | Modern React approach            |

<footer>TO BE CONT...</footer>

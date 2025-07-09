#  MODULE 2: CSS (Cascading Style Sheets)

#### Key Concepts:

* 3 Ways to Apply CSS:
  * Inline: `<h1 style="color: red;">Hello</h1>`
  * Internal: `<style>` inside `<head>`
  * External: `style.css` linked via `<link rel="stylesheet">`

* Selectors:

  * Element: `h1 { color: blue; }`
  * Class: `.title { font-size: 2rem; }`
  * ID: `#main-header { text-align: center; }`
  * Group: `h1, p { margin: 0; }`
  * Descendant: `div p {}`

* Box Model:
  `Content → Padding → Border → Margin`

* Units:

  * Absolute: `px`, `cm`
  * Relative: `%`, `em`, `rem`, `vh`, `vw`

* Positioning:

  * `static` (default), `relative`, `absolute`, `fixed`, `sticky`

* Flexbox (Angela’s favorite layout tool):

  ```css
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  ```

####  Styling Example:

```css
/* styles.css */
body {
  background-color: #f0f0f0;
  font-family: Arial, sans-serif;
}

h1 {
  color: navy;
  text-align: center;
}

.container {
  display: flex;
  justify-content: space-around;
  padding: 20px;
}
```

####  Important Notes:

* Always separate content (HTML) from presentation (CSS)
* Use `rem`/`em` over `px` for responsive scaling
* Use classes for reusable styling; avoid overusing IDs for styling

<footer>TO BE CONT....</footer>

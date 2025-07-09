# MODULE 2.2: CSS GRID — Two-Dimensional Layout System

#### Key Concepts:

**Grid** allows you to design web layouts in rows and columns. Unlike Flexbox (1D), Grid is 2D.

#### 1. Creating a Grid Container

```css
.container {
  display: grid;
}
```

#### 2. Defining Rows and Columns

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px; /* 3 columns */
  grid-template-rows: 100px 100px;          /* 2 rows */
}
```

You can also use `fr` units (fraction of available space):

```css
grid-template-columns: 1fr 2fr 1fr;
```

#### 3. Grid Gap

```css
grid-gap: 10px;          /* shorthand */
row-gap: 10px;
column-gap: 20px;
```

#### 4. Placing Items

```css
.item1 {
  grid-column: 1 / 3;    /* spans from col 1 to 3 */
  grid-row: 1 / 2;       /* stays in row 1 */
}
```

You can also use:

```css
grid-column: span 2;
grid-row: span 1;
```

#### 5. Implicit vs Explicit Grid

* Explicit grid: Defined with `grid-template-*`
* Implicit grid: Created automatically when items overflow the defined grid

#### 6. Grid Auto Placement

Let the browser place items automatically:

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}
```

Useful for responsive layouts.


### Sample Code

```html
<div class="grid-container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 10px;
}

.item {
  background-color: steelblue;
  color: white;
  padding: 20px;
  text-align: center;
}
```

<footer>TO BE CONT...</footer>

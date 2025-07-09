#  MODULE 2.1: CSS FLEXBOX — The Modern Layout Hero

####  Core Concept:

**Flexbox** = One-dimensional layout system (arranges items in a row or column). Parent becomes a **flex container**, children become **flex items**.


###  Step-by-Step Basics:

#### 1. **Activate Flexbox**

```css
.container {
  display: flex;
}
```

#### 2. **Direction of Flow**

```css
flex-direction: row;        /* default → horizontal */
flex-direction: column;     /* vertical */
```

#### 3. **Main Axis vs Cross Axis**

* `flex-direction: row` → main = horizontal, cross = vertical
* `flex-direction: column` → main = vertical, cross = horizontal


### ✳ Most Used Properties:

####  On Container:

| Property          | What it Does                        |
| ----------------- | ----------------------------------- |
| `display: flex`   | Turns element into a flex container |
| `flex-direction`  | Row / column layout                 |
| `justify-content` | Aligns items on main axis           |
| `align-items`     | Aligns items on cross axis          |
| `flex-wrap`       | Allows wrapping (default = no wrap) |

**Examples:**

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;  /* left - space - right */
  align-items: center;             /* vertical center */
  flex-wrap: wrap;
}
```

####  On Items:

| Property      | What it Does                                |
| ------------- | ------------------------------------------- |
| `flex-grow`   | How much the item should grow (share space) |
| `flex-shrink` | How much to shrink when needed              |
| `flex-basis`  | Initial size before grow/shrink             |
| `flex`        | Shorthand for grow, shrink, basis           |
| `align-self`  | Override align-items for single item        |


###  Sample Code Challenge:

```html
<div class="container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
</div>
```

```css
.container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 200px;
}

.box {
  width: 100px;
  height: 100px;
  background-color: coral;
  text-align: center;
  line-height: 100px;
  color: white;
  font-weight: bold;
}
```

 **Tip:** Use [Flexbox Froggy](https://flexboxfroggy.com/) to master this fast.

<footer>TO BE CONTN....</footer>

# MODULE 2.3: BOOTSTRAP — CSS Framework for Fast, Responsive Design

#### 1. Native CSS vs Bootstrap

| Native CSS                          | Bootstrap (Framework)                       |
| ----------------------------------- | ------------------------------------------- |
| Manual styling                      | Pre-defined, styled classes                 |
| Full control, but time-consuming    | Rapid prototyping                           |
| Write custom media queries          | Built-in responsiveness (`.col-md-*`, etc.) |
| Must create components from scratch | Ready-to-use components (cards, navbars)    |

**Conclusion:** Use CSS when you need custom behavior. Use Bootstrap to move fast with a professional look.


#### 2. Installing Bootstrap in a Project

**Option A: CDN (Quick & Easy)**

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
```

**Option B: Download and Host Locally**

Download from [getbootstrap.com](https://getbootstrap.com) → include `bootstrap.min.css` and `bootstrap.bundle.min.js` in your project folder.


#### 3. The Bootstrap 12-Column Grid System

* Rows contain columns.
* Columns add up to **12 per row**.
* Grid is responsive using breakpoints: `col-sm-`, `col-md-`, `col-lg-`, `col-xl-`.

**Example:**

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Half Width</div>
    <div class="col-md-6">Half Width</div>
  </div>
</div>
```


#### 4. Bootstrap Components (Core)

**Buttons:**

```html
<button class="btn btn-primary">Click Me</button>
```

**Cards:**

```html
<div class="card" style="width: 18rem;">
  <img src="image.jpg" class="card-img-top">
  <div class="card-body">
    <h5 class="card-title">Card Title</h5>
    <p class="card-text">Some text.</p>
    <a href="#" class="btn btn-success">Go</a>
  </div>
</div>
```

**Navbar:**

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Brand</a>
</nav>
```

**Carousel:**

```html
<div id="demoCarousel" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="img1.jpg" class="d-block w-100">
    </div>
    <div class="carousel-item">
      <img src="img2.jpg" class="d-block w-100">
    </div>
  </div>
</div>
```


#### 5. Bootstrap Icons

Use official CDN:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css">
```

Use like:

```html
<i class="bi bi-alarm"></i>
```


#### 6. Snippets and Templates

* **Official**: [https://getbootstrap.com/docs](https://getbootstrap.com/docs)
* **Third-party**: Start Bootstrap, BootstrapMade, Bootsnipp
* Use for navbars, pricing tables, login pages, etc.


#### Final Thoughts:

* Bootstrap = speed + consistency
* Combine with custom CSS when you need personalization
* Ideal for job prep: most service-level jobs expect quick prototyping skills

<footer>TO BE CONT...</footer>

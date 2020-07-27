# Bootstrap 4

Bootstrap 4 (stable release) was released in January 2018

## Bootstrap 3 vs. 4

Many of the major changes from Bootstrap 3 to Bootstrap 4 can be found [here](https://getbootstrap.com/docs/4.5/migration/)

Some of the highlights include:

- **Flexbox is now enabled by default**
  - Flexbox is a system for positioning and moving around elements when laying out your webpage and makes things much easier and less messy than previous use of floats
- Switched from `px` to `rem` (root `em`s)
  - `rem`s are basically a relative unit that allows you to scale the size of things on the web page based off the global font size. Note that the global font size has now changed from 14px to 16px
- There is now a fifth tier/size for the grid system, (previously `xs`: extra small; `sm`: small; `md`: medium; `lg`: large), now there is an extra large that corresponds to the previous large, and `xs` is for smaller devices <`576px`
- There are now dozens of new [utility classes](https://getbootstrap.com/docs/4.5/utilities/)
-

### Grid System

- Moved to Flexbox
- Updated grid class names and a new grid tier

### Components

- New (all encompassing) component called cards, **which replaces panels, thumbnails and wells**
- Glyphicons are no longer included

## Getting Started with Bootstrap 4

- Bootstrap 4 requires the following to work:
  - For CSS components
    - `bootstrap.css`
  - For Javascript components
    - `jquery` 
    - `popper.js`
    - `bootstrap.js`

This can be added via the following CDN links:

```html
<!-- CSS -->
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">

<!-- JS -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
```

## Bootstrap 4 Colours and Backgrounds

- Bootstrap 4 has added/updated the following colours that can be used for text, buttons, etc.:
- `text-primary`
- `text-secondary` (new)
- `text-info`
- `text-danger`
- `text-white` (new)
- `text-light` (new)

As well as some background colours:

- `bg-light`
- `bg-dark`
- etc

## Typography

The following changes have been made to typography in the update from Bootstrap 3 to Bootstrap 4:

### Page Headings

- Moved all `.text-` utilites to the following Sass file - `_utilities.scss`
  - This only relates to the source code
- Dropped the `.page-header` class as its styles can be applied via utilities
  - Instead of `<div class="page-header">`, which would have `padding-bottom`, `margin` and `border-bottom`, there are now utilities that add border, margin and padding
- Display headings -- *"larger, more opinionated heading styles"*
- E.g.:

    ```html
    <h1 class="display-1 text-info">Display 1</h1>
    <h1 class="display-2">Display 2</h1>
    <h1 class="display-3">Display 3</h1>
    <h1 class="display-4">Display 4</h1>
    ```

### Blockquotes

- Blockquotes have been redesigned such that styles have been moved from the `<blockquote>` element to a single class, `.blockquote`.
- `.blockquote-reverse` has also been removed
- In Bootstrap 3, blockquotes were used with the `<blockquote>` element, and if a citation was used, a `<footer>` element
- In Bootstrap 4, `<blockquote>` elements now can have a `.blockquote` class, `<footer>` elements have a `.blockquote-footer` class and `.blockquote-reverse` has a `.blockquote text-right` class
- For example:

```html
<!-- Blockquotes -->
<!-- .blockquote class -->
<blockquote class="blockquote">
    <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
</blockquote>

<!-- .blockquote-footer class -->
<blockquote class="blockquote">
    <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <footer class="blockquote-footer">Written by my cat <cite title="Blue Steele">Blue Steele</cite></footer>
</blockquote>

<!-- .blockquote text-right class -->
<blockquote class="blockquote text-right">
    <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <footer class="blockquote-footer">Written by my cat <cite title="Blue Steele">Blue Steele</cite></footer>
</blockquote>
```

### `px` vs `rem`

> Bootstrap 4 switches from `px` to rm` as the primary CSS unit, though pixels are still used for media queries and grid behaviour as device viewports are not affected by type size

- `rem` stands for "root `em`s" and takes the font size of the root (typically 16px) and multiplies by the number of `rem`s
- If the root font size changes, this means all elements defined in `rem`s will change accordingly
- The root font size is determined by the following CSS:

    ```css
    element.style {
        font-size: 16px
    }
    ```

- This makes pages more responsive when changing page sizes

## New Bootstrap Spacing Utilities

- On the docs:

> Added dozens of utility classes for common CSS property-value pairs and margin/padding spacing shortcuts

### Borders utility

https://getbootstrap.com/docs/4.5/utilities/borders/

#### Additive Borders

- There are new classes for borders and selectively keeping only parts of the border including:

    ```html
    <span class="border"></span>
    <span class="border-top"></span>
    <span class="border-right"></span>
    <span class="border-bottom"></span>
    <span class="border-left"></span>
    ```

#### Subtractive Borders

- It is also possible to subtract borders using the following HTML (note: these require an existing border to subtract *from*):

    ```html
    <span class="border-0"></span>
    <span class="border-top-0"></span>
    <span class="border-right-0"></span>
    <span class="border-bottom-0"></span>
    <span class="border-left-0"></span>
    ```

#### Border colours

- And new border colours have been added inline with the colours we have seen previously

    ```html
    <span class="border border-primary"></span>
    <span class="border border-secondary"></span>
    <span class="border border-success"></span>
    <span class="border border-danger"></span>
    <span class="border border-warning"></span>
    <span class="border border-info"></span>
    <span class="border border-light"></span>
    <span class="border border-dark"></span>
    <span class="border border-white"></span>
    ```

#### Border-radius

- We can also change the border radius and shape using the following (note: it is harder to change the thickness of the border)

    ```html
    <img src="..." alt="..." class="rounded">
    <img src="..." alt="..." class="rounded-top">
    <img src="..." alt="..." class="rounded-right">
    <img src="..." alt="..." class="rounded-bottom">
    <img src="..." alt="..." class="rounded-left">
    <img src="..." alt="..." class="rounded-circle">
    <img src="..." alt="..." class="rounded-0">
    ```

### Spacing

https://getbootstrap.com/docs/4.5/utilities/spacing/

Spacing now has the following properties

- `m` - for classes that set `margin`
- `p` - for classes that set `padding`

#### `padding`

We can set *where* we want the `padding` applied:

- `t` - for classes that set `margin-top` or `padding-top`
- `b` - for classes that set `margin-bottom` or `padding-bottom`
- `l` - for classes that set `margin-left` or `padding-left`
- `r` - for classes that set `margin-right` or `padding-right`
- `x` - for classes that set `*-left` or `*-right`
- `y` - for classes that set `*-top` or `*-bottom`
- blank - for classes that set a `margin` or `padding` on all 4 sides

We can also set the `size` to one of:

- `0` - for classes that eliminate teh `margin` or `padding` by setting it to `0`
- `1` - (by default) for classes that set the `margin` or `padding` to `$spacer * .25`
- `2` - (by default) for classes that set the `margin` or `padding` to `$spacer * .5`
- `3` - (by default) for classes that set the `margin` or `padding` to `$spacer`
- `4` - (by default) for classes that set the `margin` or `padding` to `$spacer * 1.5`
- `5` - (by default) for classes that set the `margin` or `padding` to `$spacer * 3`

## Responsive Breakpoints

Bootstrap 4 introduces a new screen size `xs` (extra small), below is an overview of the [new sizes](https://getbootstrap.com/docs/4.5/layout/overview/) in Bootstrap 4:

| | Extra small <576px | Small ≥576px | Medium ≥768px | Large ≥992px | Extra large ≥1200px |
|-|--------------------|--------------|---------------|--------------|---------------------|
| Screen type | Phone - portrait | Phone - landscape | Tablet | Small desktop/laptop | Large desktop |
| .container | 100% |  540px | 720px | 960px | 1140px |
|.container-sm | 100% | 540px |  720px | 960px | 1140px |
|.container-md | 100% | 100% | 720px | 960px | 1140px |
|.container-lg | 100% | 100% | 100% | 960px | 1140px |
|.container-xl | 100% | 100% | 100% |  100% |  1140px |
|.container-fluid | 100% |  100% | 100% | 100% | 100% |

Bootstrap 4 also allows us to selectively add margin and padding, based on screen size. For example, if you want more spacing on a large screen size and no spacing on a small screen size.

To add margin and padding we've been using the following format `{property}{sides}-{size}`, however if we want to change this for different screen sizes we can use: `{property}{sides}-{breakpoint}-{size}` for `sm`, `md`, `lg` and `xl`.

If we're just using the `{property}{sides}-{size}` format, we have the following HTML:

```html
<button class="btn btn-info p-0">P0</button>
<button class="btn btn-info p-1">P1</button>
<button class="btn btn-info p-2">P2</button>
<button class="btn btn-info p-3">P3</button>
<button class="btn btn-info p-4">P4</button>
<button class="btn btn-info p-5">P5</button>
```

However, if we want this to change for different screen sizes we can use:

```html
<button class="btn btn-warning p-sm-5 p-md-0 p-lg-5 p-xl-0">BUTTON</button>
<button class="btn btn-danger p-0 p-sm-2 p-md-3 p-lg-4 p-xl-5">BUTTON</button>
<button class="btn btn-success p-0 pl-sm-5 pt-md-5 pr-lg-5 pb-xl-5">BUTTON</button>
```

Where:

- `sm` corresponds to `padding` and `margin` for **small** screens
- `md` corresponds to `padding` and `margin` for **medium** screens
- `lg` corresponds to `padding` and `margin` for **large** screens
- `xl` corresponds to `padding` and `margin` for **extra large** screens

Note that if we want to set an option for `xs` (extra small) screens, we can set a default option of `p-0` or `m-0`, which will set the `padding`/`margin` to 0 by default.

## Boostrap 4 Navbars

In Bootstrap 3 we were unable to choose at which breakpoint to expand/collapse the navbar. In Bootstrap 4, we can now add classes which will decide at which breakpoint to expand the navbar.

See the [docs](https://getbootstrap.com/docs/4.5/components/navbar/) for more information.

### Navbar Bootstrap 4 docs summary

From the docs:

> - The navbar has been entirely rewritten in flexbox with improved support for alignment, responsiveness, and customisation
> - Responsive navbar behaviours are now applied to the `.navbar` class via the **required** `.navbar-expand-{breakpoint}` where you choose where to collapse the navbar
> - `.navbar-default` is now `.navbar-light`, though `.navbar-dark` remains the same. **One of these is required on each navbar**. However these no longer set `background-color`s; instead they essentially only affect `color`.
>   - Note that `.navbar-light` and `.navbar-dark` affect **text colour**, to change the navbar background a `.bg-{color}` class is needed

## New Display Utility

- The new display utilities in Bootstrap 4 replace the `.hidden-{size}-*` and `.visible-{size}-*` classes.
- It now has features such as `.d-inline` or `.d-block` which can control whether an element is an inline element or a block element, for example:

  ```html
  <h1 class="border border-danger d-inline">HELLO</h1>
  <h1 class="border border-success d-block">HELLO</h1>
  ```

- Sets inline and block borders accordingly
- In addition, it is also possible to selectively set for certain breakpoint sizes, which elements will appear, for example:

  ```html
  <!-- Hides <h1> on xl only -->
  <h1 class="d-xl-none">HIDE ME ON XL</h1>

  <!-- Always hidden except for on lg, 
  i.e. default is hidden up to large, and hidden for xl -->
  <h1 class="d-none d-lg-block d-xl-none">ALWAYS HIDDEN EXCEPT LG</h1>
  ```

- Another example of where this would be likely to be used in the wild might be a `jumbotron` where a large amount of text is hidden on `xs`/`sm` screens due to it taking up too much space:

  ```html
  <div class="container">
    <div class="jumbotron">
        <h1 class="display-4">Hello, world!</h1>
        <p class="lead d-none d-md-block">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quis odio debitis voluptatem possimus corrupti labore alias! Ad ipsa, veniam in quo a aperiam obcaecati quae. Blanditiis delectus, corrupti optio voluptatem eum deserunt officiis vitae. Similique amet facere voluptas velit maxime neque, quisquam exercitationem aliquam vitae inventore cumque ad nihil sit expedita fugiat at, quos quae. Aperiam obcaecati aut magni veritatis!</p>
        <hr class="my-4">
        <p>It uses utility classes for typography and spacing to space content out within the larger container.</p>
        <a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a>
    </div>
  </div>
  ```

- This ensures that the large lorem ipsum text block is hidden for `xs` and `sm` screen sizes

## Bootstrap 4: Flexbox and Layout

The [Bootstrap 4 migration docs](https://getbootstrap.com/docs/4.5/migration/) mentions Flexbox many times. Although technically Flexbox exists outside of Bootstrap (4), it is strongly interlinked with the use of Bootstrap.

Flexbox and the flex utilities can be very powerful. For example, a border can be set on it's own without Bootstrap, but we can use the Bootstrap border utility to make things easier.

Flexbox includes many CSS properties that can move and position elements inside of a container inside of a page, which can all be done without Bootstrap. However, Bootstrap 4 comes with lots of utilities relating to flexbox, which can be found [here](https://getbootstrap.com/docs/4.5/utilities/flex/).

Flexbox can be described as a model for positioning content inside of a box. With Flexbox the main-axis of our content is from left to right. Then there is also the cross-axis, which is from top to bottom.

### `.justify-content-*`

One way we can use Flexbox, is by defining *where* we want our elements inside, for example a border, illustrated below:

```html
<!-- style added for illustration purposes only -->
<div class="border border-dark d-flex" style="height: 200px">
  <button class="btn btn-info btn-lg">LARGE</button>
  <button class="btn btn-warning">SMALL</button>
</div>
```

The `.justify-content-*` class determines where on the main axis (left to right), elements should be positioned. By default when Flexbox is used (`.d-flex` class), `.justify-content-start` is used as default.

If we change this to `.justify-content-end`:

```html
<div class="border border-dark d-flex justify-content-end" style="height: 200px">
  ...
</div>
```

And we inspect the `<div>` element using a border, we can see the following CSS:

```css
.justify-content-end {
  justify-content: flex-end!important;
}
```

We can use the following variations for our desired use-case:

```html
<div class="d-flex justify-content-start">...</div>
<div class="d-flex justify-content-end">...</div>
<div class="d-flex justify-content-center">...</div>
<div class="d-flex justify-content-between">...</div>
<div class="d-flex justify-content-around">...</div>
```

### `.align-items-*`

If we want to use Flexbox to position elements on the cross-axis (top to bottom), then we can use the `.align-items-*` class. Some examples are included below:

```html
<div class="d-flex align-items-start">...</div>
<div class="d-flex align-items-end">...</div>
<div class="d-flex align-items-center">...</div>
<div class="d-flex align-items-baseline">...</div>
<div class="d-flex align-items-stretch">...</div>
```

Note that both `.justify-content-*` and `.align-items-*` are responsive and can be set for different breakpoints using `.justify-content-{size}-*` and `align-items-{size}-*` for sizes: `sm`, `md`, `lg`, `xl`.

## Flexbox Utilities Pt. 2

We previously discussed how Flexbox has two axes: the main axis (left to right) and the cross axis (top to bottom). We can change the direction of these using:

- `.flex-row`: sets horizontal direction
- `.flex-row-reverse`: starts horizontal direction from the opposite side
- `.flex-column`: sets vertical direction
- `.flex-column-reverse`: starts vertical direction from the opposite side

### Other Flexbox Utilities

- `.align-self`: If we want to individually align one of the items
- `.flex-fill`: to force sibling elements into equal widths while taking up all available horizontal space
- `.flex-grow-*` to toggle a flex item's ability to grow to fill available space
- etc

### Using Flexbox responsively

We can use Flex responsively, for example if we wanted to have buttons that would stack on `xs` breakpoints (smaller screens) we could do something like the following:

```html
<div class="d-flex flex-column flex-md-row justify-content-between">
  <button class="btn btn-dark btn-lg">Link 1</button>
  <button class="btn btn-dark btn-lg">Link 2</button>
  <button class="btn btn-dark btn-lg">Link 3</button>
  <button class="btn btn-dark btn-lg">Link 4</button>
  <button class="btn btn-dark btn-lg">Link 5</button>
  <button class="btn btn-dark btn-lg">Link 6</button>
</div>
```

Where we have set the `<div>` element to be a `.flex-column` as default (i.e. for `xs` screens), and then as `.flex-md-row` for sizes `md` and up (to `xl`).

## Navs and Flexbox

Why should you care about Flexbox? One example is Navs, which are now built with Flexbox behind the scenes, which means we can move elements around using the Flexbox utilities.

From the [docs](https://getbootstrap.com/docs/4.5/components/navs/): 

> ### Navs
>
> - Rewrote component with flexbox
> - Dropped nearly all `>` selectors like `.nav > li > a`, we use separate classes for `.nav`s, `.nav-item`s and `.nav-link`s. This makes you HTML more flexible while bringing along increased extensibility

- By default, navs use flexbox. This means the `.d-flex` class does not need to be used
- Navs can be created with a `<nav>` element (with `<a>` anchor tags) or as a `<ul>` element with `<li>` elements. For both cases there is a `.nav` class to designate these as `nav`s
- Below are some examples:

```html
<!-- Unordered list with list elements -->
<ul class="nav border border-primary justify-content-around">
  <li class="nav-item">
      <a class="nav-link active" href="#">Active</a>
  </li>
  <li class="nav-item">
      <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
      <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
      <a class="nav-link disabled" href="#">Disabled</a>
  </li>
</ul>

<!-- Simpler nav: <nav> element with anchor tags -->
<!-- Also set as a `flex-column` for xs screens -->
<nav class="nav flex-column flex-sm-row justify-content-center align-items-center">
  <a class="nav-link active" href="#">Active</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" href="#">Disabled</a>
</nav>
```

- There are also different configurations for the UI of the Navs such as:
  - Tabs: `.nav-tabs`
  - Pills: `.nav-pills`
  - etc..

## Bootstrap Grid System

One of the major changes from Bootstrap 3 to Bootstrap 4, is the addition of the new breakpoint `xs`. This is somewhat confusing as `xs` already existed in Bootstrap 3, but for `<768px`. Now it is for `<576px`. Below is a table showing the changes:

| Size Range (`px`) | Size/Device | Bootstrap 3 | Bootstrap 4 |
|-------------------|-------------|-------------|-------------|
| `<576px`          | Extra small devices | n/a | `xs` |
| `>=576px`/ `<768px` | Small devices | `xs` | `sm` |
| `>=768px`         | Medium devices | `sm` | `md` |
| `>=992px`         | Large devices | `md` | `lg`|
| `>=1200px`        | Extra large devices | `lg` | `xl` |

Also to note, as previously mentioned, whereas for margin, padding , utility classes, etc., we can specify `sm`, `md`, `lg`, `xl`, to control for `xs` we have to set a default for `xs` and any specific behaviours for `sm`/`md`/`lg`/`xl` accordingly.

In the Bootstrap > Layout > Grid [docs](https://getbootstrap.com/docs/4.5/layout/grid/), there are many examples and the display flex grid. The `.d-flex` class is also set automatically, but there are some things we **have** to do:

- We have to make a container such as `<div class="container">...</div>` (note it can also be a `.fluid` container also)
- It must also contain `<div>` elements `.row` class, of which each has `<div>` elements with `.col-*` class
- For example:

  ```html
  <div class="container">
    <div class="row">
      <div class="col-sm">
        One of three columns
      </div>
      <div class="col-sm">
        One of three columns
      </div>
      <div class="col-sm">
        One of three columns
      </div>
    </div>  
  </div>
  ```

#### Recap

- All breakpoints have changed
- We don't reference `xs` anymore
- We apply everything for `sm` and above, or `md` and above, etc

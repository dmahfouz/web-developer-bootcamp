# Bootstap

## Unit Objectives

1. Define Bootstap and explain why we use it
2. Include bootstrap locally and by using a CDN
3. Use common Bootstrap components like navs and buttons
4. Build a layout using the Bootstrap grid system

## Unit Projects

1. Project: Portfolio site (using Bootstrap)
2. Project: Startup Landing Page

## What is Bootstrap

### What is Bootstrap?

> *Bootstrap is the most popular HTML, CSS and JS framework for developing responsive, mobile first projects on the web*

### Why we're using it

1. Bootstrap is very popular
2. Enables developers to build good looking websites pretty quickly

### Using Bootstrap

#### CSS

- The Bootstrap site(**\***) https://getbootstrap.com/docs/3.3/ (also built with Bootstrap) "gives you a lot for free", meaning that it is possible to go through the docs and find many website components such as buttons, nice looking forms, etc

\* We're using Bootstrap 3 vs. Bootstrap 4 b/c some companies still use Bootstrap 3

- When we click on CSS tab, we can find these components, along with related code and configurations
- Because of this Bootstrap can be considered as a "box of lego pieces" for building websites

#### Components

- Components contain soem of the bigger peices of bootstrap that we can use which includes things like `navbars`. This is one of the more popular aspects of Bootstrap, as many websites use this

### Bootstrap Expo

- expo.getbootstrap.com showcases multiple projects that use bootstrap
- Note that although Bootstrap provides many resources for adding components to your website, you do not *need* to use it as-is, although in some cases this is also *not* a bad thing
- Most professional websites that use Bootstrap, although they may be using Bootstrap add their own elements of style and uniqueness such that everything isn't directly copied

## Adding Bootstrap to a Project

### Method 1: Downloading Bootstrap

- Go to https://getbootstrap.com/docs/3.3/getting-started/#download and click "Download Bootstrap"
- This downloads a zipped folder containing the Bootstrap distribution
- When unzipped, there are `css`, `js` and `fonts` folders
- In the `css` folder, there are:
  - `./css/bootstrap-theme.css`
  - `./css/bootstrap.css`
- As well as minified versions of these fields (same file but shrunk down):
  - `./css/bootstrap-theme.min.css`
  - `./css/bootstrap-min.css`
- And maps files (...)
- In the main `bootstrap.css` file, almost every single line of CSS is a class declaration
- Note that the minified `bootstrap.min.css` file will load up the page slightly quicker than the `bootstrap.css` file
- We can then use these classes inside our application, e.g. if we want a button with white text and a red background, we can to apply `.btn-danger`
- Once Bootstrap is downloaded, we can add different components (such as `bootstrap.css`) to our project directory and using a `<link>` element to reference the Bootstrap CSS file
- An alternative to downloading Bootstrap, is to use the Bootstrap CDN link provided on the Bootstrap download page:

    ```html
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
    ```

- This is simply a hosted version of the minified `bootstrap.min.css` file and saves having to download the entire Bootstrap distribution

## Forms and Inputs

- **Note**: the Bootstrap docs are designed to be used as a reference only, it *does not* need to be memorised

### Jumbotron

- Bootstrap docs (getbootstrap.com/components/#jumbotron) define a Jumbotron as:

    > A lightweight, flexible component that can optionally extend the entire viewport to showcase key content on your site

- Given by the following html:

    ```html
    <div class="jumbotron"> My jumbotron text here</div>
    ```

- To give a jumbotron nicer spacing and margin (so it effectively doesn't take up the whole page), put in a `<div>` with the `container` class:

    ```html
    <div class="container">
        <div class="jumbotron"> My jumbotron text here</div>
    </div>
    ```

### Forms

- There are two main important classes to remember with Forms:
  - `form-control`
    - This makes the inputs "bootstrap-ified", i.e. much better looking
  - `form-group`
    - Whatever is put inside a `form-group` has nicer spacing
  - `form-inline`
    - A form wrapped in the `form-inline` class makes the entire form inline


## Nav Bars

- `nav-bar`s are one of the most important and widely used components in Bootstrap
- We can see an example of a Bootstrap `nav-bar` on Bootstrap's [documentation page](getbootstrap.com)
- When we resize the page, we can see that the nav bar is responsive to the page size and when we get to tablet or mobile sized pages, we get a hamburger icon

## The Grid System

Note: If your screen size is too small then the columns in the grid will stack vertically instead of sitting side-by-side. To correct this issue you can change the `col-lg-6`  classes to `col-md-6` instead.

- The Bootstrap Grid system acts as a skeleton for an entire application. It is a really easy way to add structure and layout to our application
- The Bootstrap documentation for the [Grid System](https://getbootstrap.com/docs/3.3/css/#grid) gives the following definition:

  > Bootstrap includes a responsive, mobile first fluid grid system that appropriately **scales up to 12 columns** as the device or viewport size increases. It includes predefined classes for easy layout options, as well as powerful mixins for generating more semantic layouts.

- Any webpage using the Bootstrap Grid system, will use any of those twelve columns accordingly. For example the Bootstrap documentation page has (roughly) 10 columns worth of content, and a right pane that likely includes 2 columns
- If we wanted to use the Grid system for 12 x 1 column `div` elements on one row and 3 x 4 `div` elements on another row, we could do the following:

  ```html
  <div class="container">
    <div class="row">
      <!-- 1 x 12 x 1 cols -->
      <div class="col-lg-1 pink">COL LG 1</div> <!-- 1st column -->
      <div class="col-lg-1 pink">COL LG 1</div> <!-- 2nd column -->
      ...                                       <!-- ...th column -->
      <div class="col-lg-1 pink">COL LG 1</div> <!-- 12th column -->
    </div>
    <div class="row">
      <!-- 1 x 3 x 4 cols -->
      <div class="col-lg-4 pink">COL LG 4</div>
      <div class="col-lg-4 pink">COL LG 4</div>
      <div class="col-lg-4 pink">COL LG 4</div>
    </div>
  </div>
  ```

- When using the Bootstrap grid system, there are 4 device sizes to take into account, as given in the table from the [Bootstrap docs](https://getbootstrap.com/docs/3.3/css/#grid-options)
- As the screen is resized, Bootstrap will adjust the grid based on the following sizes:
  | Device size | Device Type | Grid behaviour | Class prefix |
  |-------------|-------------|----------------|--------------|
  | **Extra small devices** | Phones (<768px) | Horizontal at all times| `.col-xs-` |
  | **Small devices** | Tablets (>=768px) | Collapsed to start, horizontal above breakpoints | `.col-sm-` |
  | **Medium devices** | Desktop/laptop screen (>=992px) | Collapsed to start, horizontal above breakpoints | `.col-md-` |
  | **Large devices** | Desktops (>=1200px) | Collapsed to start, horizontal above breakpoints | `.col-lg-` |

- This allows a custom grid system to be created that responds as intended for device screen size, for example:

  ```html
  <div class="row">
    <div class="col-md-3 col-sm-6">TOUR DATE!</div>
    <div class="col-md-3 col-sm-6">TOUR DATE!</div>
    <div class="col-md-3 col-sm-6">TOUR DATE!</div>
    <div class="col-md-3 col-sm-6">TOUR DATE!</div>
  </div>
  ```

  - Has a grid system that will start at 1 x 4 x 3 column-`div`s at large and medium sized screen sizes, and then will become 2 x 2 x 6 column-`div`s at small screen sizes and finally 6 x 1 x 6 column-`div`s
    - Note that the large device size `.col-lg-` doesn't need to be explicitly defined as Bootstrap is clever enough to know that it should be the same format the the medium device `.col-md-3`

- If we want to nest grid (rows) in a single column we can do this by adding another row-`div` (`<div class="row">`) and add nested columns within that row:

  ```html
  <div class="row">
    <div class="col-md-3 col-sm-6 pink">
      <div class="row">
        <div class="col-lg-6 orange">FIRST HALF</div>
        <div class="col-lg-6 orange">OTHER HALF</div>
      </div>
    </div>
    <div class="col-md-3 col-sm-6 pink">TOUR DATE!</div>
    <div class="col-md-3 col-sm-6 pink">TOUR DATE!</div>
    <div class="col-md-3 col-sm-6 pink">
      <div class="row">
        <div class="col-lg-2 orange"></div>
        <div class="col-lg-2 orange"></div>
        <div class="col-lg-2 orange"></div>
        <div class="col-lg-2 orange"></div>
        <div class="col-lg-2 orange"></div>
        <div class="col-lg-2 orange"></div>
      </div>
    </div>
  ```

## Bootstrap Image Gallery

[Note: HTML/CSS can be found in the following [directory](./image-gallery/)]

### Takeaways

- Added a `nav-bar` that is fixed to the top of the page as you scroll down
- Used the `navbar-inverse` class to get a black and white layout, which was then changed to the appropriate colours
- Used the `navbar-fixed-top` class to ensure the navbar stays fixed at the top of the page
- Used a jumbotron and a grid system
- Introduced built-in glyphicons from Bootstrap and FontAwesome (more popular/varied than Bootstrap) to add the the `navbar` and main header
- Introduced the `thumbnail` `div` class that can be put around a image to constrain the image within our grid
- Talked about specificity, how Bootstrap styles had to be overrided to add our own custom styles

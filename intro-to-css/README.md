# Introduction to CSS

## Objectives/Module Summary

- **Objective 1:** Define the "General Rule" of CSS
- **Objective 2:** How to incorporate CSS into HTML files
- **Objective 3:** Select elements by tag name, class and ID
- **Objective 4:** Style elements with basic properties like colour and background
- **Objective 5:** Use Chrome CSS Inspector to debug HTML and CSS
- **Exercise:** CSS Selector Scavenger Hunt

## Intro to CSS

### Objectives

- Define CSS and the role that it plays in WebDev
- View websites before and after CSS has been added
- Understand the "general rule" for CSS syntax

### CSS - Cascading Style Sheets

- Recall, CSS is often consider the "adjectives" or the "skin" of a webpage, whereas HTML is the "nouns"
- We use CSS to describe how things should look, such as make the headings purple, and the font size 50 pixels, or move this down to the bottom, etc.., this refers to the **Style** is CSS
- The **Sheets** in CSS refers to the CSS being a separate file to HTML, they are separate documents that are included in HTML
- To see examples of how powerful CSS can be, check out http://www.csszengarden.com/ and view the different style webpages, all of which have the same HTML, but have been styled in (sometimes radically) different ways

### The General Rule

```css
selector {
    property: value;
    anotherProperty: value;
}
```

- We have a `selector` that selects something, usually html elements
- Then, inside the curly braces we have a key-value format that has a `property: value;`
- Note that we can have one or two or a hundred different `property: value;` key-value pairs inside a `selector`
- Here are some examples:
    ```css
    /*Make all h1's purple and 56px font*/
    h1 {
        color: purple;
        font-size: 56px;
    }

    /*Give all img's a 3px red border*/
    img {
        border-color: red;
        border-width: 3px;
    }
    ```

## Our First Stylesheet

### Where do we write our styles?

- There are two choices to where we should put our CSS
  - **Inline**

    ```html
    <h3 style="color: pink;">blah blah blah </h3>
    <h3 style="color: pink;">knock knock </h3>

    <p style="color: yellow;">blah blah blah </p>
    ```

  - Some notes about the **inline** approach
    - This used to be the only way you would be able to style elements before separate stylesheets and CSS
    - This is **not** the recommended approach, for 2 reasons
    - The first is that this involves writing CSS inside of a HTML element, such as:

        ```html
        <li style="color: purple;">Playing guitar</li>
        ```

    - This has the problem that the CSS code needs to be duplicated/repeated for each element, which can clutter HTML very quickly and become a lot of work/error prone. It also means if we need to change the CSS definitions, we have to replace all instances, which again has the same issue of being cumbersome and error-prone
    - The second is related to the ***separation of concerns***; we want our styles to be self contained in it's own file, so we have one file *just* for HTML and another *just* for CSS
  - **Style tag**
    - CSS can also be embedded into a HTML using the `<style>` element and defining all CSS stylings there, for example:

    ```html
    <html>
        <head>
            <title>About Me</title>
            <style type="text/css">
                /* selector {
                    property: value;
                } */
                h1 {
                    color: purple;
                }
                li {
                    color: orange;
                }
                h1 {
                    color:blue;
                }
            </style>
        </head>
        <body>
            <h1>...</h1>
            <h4>My Hobbies:</h4>
            <ul>
                <li>Cooking</li>
                <li>Music</li>
                <li>Origami</li>
            </ul>
        </body>
    </html>
    ```

  - Note that if there are conflicting styles, such as two different `<h1>` element selectors for colour, we find that the last defined element selector is chosen, i.e.:

    ```css
    h1 {
        color: blue;
    }
    ```

  - The problem with the **Style Tag** is that it is *still* inside the HTML, and we want to separate our HTML and CSS although functionally it may look the same way
  - What we want to do is use a `<link>` tag

### `<link>` tags

- Recap: **inline** and **style tag** implementations of CSS nested in HTML are a **\*bad idea\***
- A `<link>` tag allows us to write our CSS in a totally separate file and then connect it to our HTML using a `<link>` tag in the `<head>`
- This will go get the contents of the CSS file and style the HTML accordingly
- If we have a CSS file called `app.css` we would link it in our HTML using the following:
    ```html
    <link rel="stylesheet" type="text/css" href="app.css">
    ```
- This will then apply the required stylings defined in `app.css` to the HTML
- In summary the `<link>` tag is just a reference to another file
- One final note: we want to put the `<link>` tag in the `<head>`, this is the point of `<head>`, it's where you put the stuff that isn't actually on the page such as elements, but things that have to do with those elements such as fonts, stylesheets and javascript files

## Colours in CSS

- In this section, we will explore different ways of describing and representing colours in CSS
- Most of the default colours are rarely used, because most designers and web developers have a very specific colour palette - this could be following a brand's colour or a design that someone has created
- There are around 147 built-in colours in CSS
- CSS provides a few different colours systems that can be used:
  - **Hexadecimal:**
    - '#' + string of 6 hexadecimal numbers from (0-F), for example:
        ```css
        /* Change all h1s to black */
        h1 {
            color: #000000;
        }
        /* Change all h2s to purple */
        h2 {
            color: #4B0082;
        }
        /* Change all h3s to pink */
        h3 {
            color: #FF1493;
        }
        ```
    - The starting '#' in a hexadecimal colour code is called an **octothorpe**
    - The first two numbers of the 6 digit hexadecimal code used to represent numbers correspond to how much red is in the colour, the next two correspond to how much green, and the last two how much blue is in the colour
  - **RGB**
    - 3 Channels: Red, Green and Blue. Each ranges from 0-255
    - Follows the format: `rgb(<red intensity>, <blue intensity>, <green intensity>)`
    - Example CSS:
        ```css
        h1 {
            color: rgb(0, 255, 0);
        }

        h2 {
            color: rgb(100, 0, 100);
        }

        h3 {
            color: rgb(11, 99, 150);
        }
        ```
  - **RGBA**
    - Just like RGB, but with an alpha (transparency) channel. Ranges from 0.0-1.0
    - Syntax:
        ```css
        /* full opaqueness (zero transparency) */
        h1 {
            color: rgba(11, 99, 150, 1);
        }
        /* slightly more transparent (0.6 opaqueness) */
        h2 {
            color: rgba(11, 99, 150, .6);
        }
        /* even more transparent (0.2 opaqueness) */
        h3 {
            color: rgba(11, 99, 150, .2);
        }
        ```

- Summary:
  - Built-in colours - e.g. `red`, `blue`, `..`, etc - rarely used
  - Hexadecimal colours - e.g. `#0FA24C`
  - RGB - `rgb(r, g, b)` - similar to hexadecimal
  - RGB - `rgba(r, g, b, a)` - similar to `rgb()`, but includes a channel for alpha which represents transparency

## Background and Border

### Colour and background

- Use `color` to set text colour and `background` for background colour
- Code example:
  - CSS:

    ```css
    body {
        background: #95a5a6;
    }

    div {
        background: #3498db;
    }

    P {
        color: #ecf0f1;
    }
    ```

  - HTML:

    ```html
    <div>
        <p>Hello</p>
        <p>Goodbye</p>
    </div>
    ```

### Background Image

- The background property can also be set to a background image
- CSS example:

    ```css
    body {
        background: url(http://3dprint.com/wp-content/uploads/2014/11/-Rainbow_Ocean__by_Thelmal.jpg);
    }

    div {
        background: rgba(0,0,0,.7);
    }

    P {
        color: #ecf0f1
    }
    ```

- When setting the background using an image URL, if the image is not big enough to fit the page, the border will tile horizontally and/or vertically
- To prevent URL backgrounds from tiling we can use the `background-repeat: no-repeat;` option which will prevent the background image from having a repeated tiling style effect
- If we want the background image to cover the page, we can use the `background-size: cover;` property-value option, which will stretch the image to cover the screen

    ```css
    body {
        background: url(https://www.some-website.com/image.jpg);
        background-repeat: no-repeat;
        background-size: cover;
    }
    ```

### CSS Borders

- If we want to add a border to any of our HTML elements, we can use the following CSS:

    ```css
    h1 {
        color: rgba(24, 156, 90, 0.616);
        border-width: 5px;
        border-style: solid; */
        border: 1px dashed rgb(200, 100, 50)
    }
    ```

- Borders defined in CSS typically have three parts:
  - Width (size of border line in pixels)
  - Colour (colour of border)
  - Border-style (`solid`, `dashed`, etc)

- We can write all three parts of the CSS border definitions using the following syntax:

    ```css
    h1 {
        color: rgba(24, 156, 90, 0.616);
        border: 1px dashed rgb(200, 100, 50)
    }
    ```

## CSS Selectors

- In this section, we're going to focus on three CSS selectors:
  - Element
  - ID
  - Class

- Note that there are way more options for selecting elements, which will be covered later

### The Basics: Element, ID and Class

#### Element Selector

- Select all instances of a given element, e.g. `div`, `h1`
- HTML:

    ```html
    <div>
        <p>You say yes</p>
        <p>I say no</p>
    </div>

    <div>
        <p>You say goodbye</p>
        <p>I say hello</p>
    </div>
    ```

- CSS:

    ```css
    div {
        background: purple;
    }

    p {
        color: yellow;
    }
    ```

- The example above sets all `div`s to have a purple background and all paragraph elements `<p>` to be yellow

#### ID Selector

- If we want to single out only one `<li>` or one `<h1>` element, we could use the ID selector
- The ID selector selects an element with a given ID. Only one per page!

    ```html
    <div>
        <p>You say yes</p>
        <p>I say no</p>
    </div>

    <div>
        <p>You say goodbye</p>
        <p id="special">I say hello</p>
    </div>
    ```

- CSS:

    ```css
    div {
        background: purple;
    }

    #special {
        color: yellow;
    }
    ```

- The CSS above selects the last `<li>` element to be yellow by adding a hook which is called an `id`
- `id`s are added as an attribute to any element such as `id="value"`
- The CSS `id` selector references the id `"special"` using an octathorpe (hash symbol) as it would with an element such that:

    ```css
    #id {
        property: value
    }
    ```

- Note: id values (i.e. `="special"`) _can only be used **once**_. If the same id is used more than once, that will produce invalid HTML
- We can however, have multiple Ids on a page as long as they don't appear more than once
- Note that it is also possible to have an element selector and an id selector at the same time, for example, if we wanted all `<li>`s to have a red border, but the last `<li>` to have a yellow background this could be done with the following:

    ```css
    li {
    border: 2px solid red;
    }

    #special {
        background: yellow;
    }
    ```

#### Class selector

- Sometimes, we want to have multiple elements that look similar
- A `class` attribute works similarly to a `id` element, except that it can be used for any number of elements on a page
- The class selector selects all elements with a given class

- HTML:

    ```html
    <div>
        <p class="highlight">You say yes</p>
        <p>I say no</p>
    </div>

    <div>
        <p class="highlight">You say goodbye</p>
        <p id>I say hello</p>
    </div>
    ```

- CSS:

    ```css
    div {
        background: purple;
    }

    .highlight {
        color: yellow;
    }
    ```

- In the above code, we apply the class `highlight` to the 1st and 3rd paragraph and reference this class with a dot: `.highlight { ... }`

#### Some final notes

- In our `todos.css`, we can add a strike-through (to checked items) using the `text-decoration` property
- We can also add the `checked` attribute to our checkbox, to ensure the checkboxes are checked by default:  `<input type="checkbox" checked>`

## Introduction to Chrome Inspector

- In chrome, source code can be view by right-clicking and selecting 'View Source'
- There is another feature that can be used by right-clicking and selecting 'Inspect' or 'Inspect Element', this will open the Chrome Inspector
- In the 'Elements' tab of the Chrome Inspector, it is possible to view the HTML code for that webpage, and by hovering over each HTML element the Chrome Inspector will show you where that element corresponds to on the page and the space it takes up
- It is also possible to view the CSS elements for a particular HTML element and looking in the 'Styles' pane to the right. This wil show all the CSS references to the element, where it be the element, class, id, or other
- These CSS elements can be unchecked and checked and even modified to interactively show changes in the webpage
- In the top left-hand corner of the Chrome Inspector, there is a magnifying glass or cursor icon, that when clicked allows you to select any part of the page and the Chrome Inspector will show you the corresponding HTML code
- All of these features are useful for debugging such as looking at what space elements are taking up, how they look, what HTML is contributing to which parts of the page
- The features of Chrome Inspector are useful for also understanding how other webpages work, for example if you're curious or want to mimic a style

## More Advanced Selectors

- Recap: CSS selectors covered so far:
  - Element selector
  - Id selector
  - Class selector
- Reference: https://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048
- Note that these do not need to be memorised from the article, these will be naturally memorised over time by using the more common css selectors

## Inheritance, Specificity and the Cascade

- If we set a property on a parent, it can also affect a child element (via *inheritance*). For example:

    ```css
    ul {
        color: purple;
    }
    ```

- Will set all `<li>` elements (that are children of the `<ul>` elements) to be the colour purple
- *Specificity* in CSS is that we can have multiple styles target the same element or tag, for example:

    ```css
    body {
        color: red;
    }
    p {
        color: green;
    }
    ```

- Will first target the `<p>` paragraph element a red (inherited from body) but then will target the element as green, as the last styling more specifically targets the `<p>` tag
- Whichever style is more specific/closest to the style, will determine ("win") which styling to use

### Specificity calculator

- Some basic rules:
  - Element selectors such as tag names (e.g. `<p>`, `<h2>`) are not very specific
    - Specificity score = 0-9
  - Class selectors (e.g. `.highlight`) are more specific
    - Specificity score = 10-99
  - Id selectors (e.g. `#special`) are even more specific
    - specificity score = 100-999

### Summary:

- **Type selectors** are not very specific, e.g.:

    ```css
    /* least specific */
    li {
        /* ... */
    }
    /* more specific */
    li a {
        /* ... */
    }
    /* even more specific */
    li + a {
        /* ... */
    }
    ```

- **Class, Attribute and Psuedo-Class Selectors** are more specific (magnitude x10 bigger), e.g.:

    ```css
    .hello {
        /* ... */
    }

    input[type="text"] {
        /* ... */
    }
    ```

- **ID Selector** are most specific, e.g.:

    ```css
    #special {
        /* ... */
    }
    ```

### References

- [MDN article on Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [Specificity calculator](https://specificity.keegan.st/)
- [W3 guide on Specificity](https://www.w3.org/TR/selectors-3/#specificity)

## Selectors Practice Exercise

### Notes/corrections

- Lecture should say *"Make all inputs (except the checkboxes) have a 3px red border"* **instead of** *"Make all inputs have a 3px red border"*
- Checkboxe elements cannot be styled *directly*, if you're wondering how to style them, you can checkout this [thread](http://stackoverflow.com/questions/4148499/how-to-style-checkbox-using-css)
- Around the 1m40 market, there is a mistake in the CSS colour property used, it should be either a `background` or `background-color` property
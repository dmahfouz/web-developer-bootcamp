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
  - HTML
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
- Output:

<!DOCTYPE html>
<html>
    <head>
	    <style type="text/css">
		    body {
        	    background: url(https://i.pinimg.com/564x/25/d0/7f/25d07fe50870380f45f3aa18c22773dc.jpg);
    	    }
	        div {
	            background: rgba(0,0,0,.7);
	        }
            p {
                color: #ecf0f1
            }
	    </style>
	<title></title>
    </head>
    <body>
	    <div>
		    <p>Hello</p>
		    <p>Goodbye</p>
	    </div>
    </body>
</html>


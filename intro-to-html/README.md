# Section 3: Introduction to HTML

## Unit Objectives

- **Objective 1**: Write properly structured HTML documents
  - Essential tags, code, rules
- **Objective 2**: Write common closing and self-closing tags
  - Different types of tags, common elements
  - Closing tags
  - Self closing tags
- **Objective 3**: Recreate a simple website bnased on a provided photo

## HTML Basics

### Objectives

- Write simple HTML documents
- Understand the difference between closing and self closing tags
- Write tags with attributes
- Use MDN as a reference
- Given an image, write the corresponding HTML

### History of HTML

- Created in 1989/1990
- Allowed publishing and exchanging of scientific and technical documents
- Allowed electronic linking of the documents via hyperlinks

### The General Rule

`<tagName> Some Content </tagName>`

### Introduction to MDN (Mozilla Developer Network)

- MDN (Mozilla Developer Network) can be a great resource for learning HTML, CSS and JavaScript as as well as acting as a reference
- The following [link](https://web.archive.org/web/20151206134313/https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Introduction) is a short introduction to HTML (outdated)
- The following [link](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML) is an up-to-date reference for HTML

### HTML Boilerplate and Comments

- HTML5 boilerplate (required to create a valid document) looks like the following:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title></title>
    </head>
    <body>

    </body>
    </html>
    ```

  - Note that `<!DOCTYPE html>` indicates a HTML5 doctype - this tells the browser that this document is using HTML5
  - The `<html>` element represents the root (top-level element) of an HTML document (also referred to as the *root element*). All other elements must be descentants of this element
    - The **permitted content** of an HTML element is (**_only_**) one `<head>` element and one `<body>` element
  - The `<head>` element provides general information (metadata) about the document, including its title and links to or definitions of scripts and style sheets - e.g. font, CSS, JavaScript files
  - The `<body>` element represents the contents of our document

- To write comments, use the following syntax:

    ```html
    <!-- this is a comment -->
    ```

- The `<title>` tag is also important as this is responsible for the text shown in the tab of your page in a browser, as well as what will be shown in search engines (e.g. google search hits will show the title that you've given) and other pages linked to your site

### Basic Tags

- MDN Element Reference [(link)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
  - Lists all the elements in HTML
  - ~ 100 different types of HTML elements

- Heading elements `<h1>–<h6>` are elements for different types of headings
  - Also known as **block elements** - which means that each heading will get it's own line (note the alternative to **block elements** are **inline elements** like (em-)bold(-en) `<bold>`)

- Note about deprecations of `<b>` bold elements and `<i>` italicised elements
  - Bold elements `<b>` is now deprecated in HTML5 and better, recommended approach is to use the strong `<strong>` instead
  - Similarly, italicised elements `<i>` is also deprecated in HTML5 and the better, recommended approach is to use emphasized `<em>` elements
  - Both the strong `<strong>` and emphasis `<em>` tags mean more than `<b>` and `<i>` and the idea is in HTML5, we want to separate the **styling from the structure**, where `<b>`/`<i>` indicate styling whereas `<strong>`/`<em>` refer to structure

### HTML lists

- Two types of list:
  - Ordered list `<ol>` (1., 2., 3, .., etc)

    ```html
    <ol>
        <li>Red</li>
        <li>Orange</li>
        <li>Yellow</li>
    </ol>
    ```
  
  - Unordered list `<ul>`

    ```html
    <ul>
        <li>Red</li>
        <li>Orange</li>
        <li>Yellow</li>
    </ul>
    ```

- Note that for both ordered `<ol>` and unordered `<ul>` lists, list elements `<li>` are required to display individual elements
- Within ordered/unordered lists, it is possible to nest more lists (can be of different type or otherwise - i.e. nested ordered lists within unordered list or vice versa)
- It is also possible to add other formatting

    ```html
    <h4>My colour list</h4>
    <ol>
        <li>Red</li>
        <li>Orange</li>
        <li>Yellow
            <ul>
                <li>Sunflower</li>
                <li>Banana
                    <ol>
                        <li>Frozen banana</li>
                        <li>Non-Frozen banana</li>
                    </ol>
                </li>
            </ul>
        </li>
    </ol>

    <ul>
        <li><strong>Red</strong></li>
        <li>Orange</li>
        <li>Yellow</li>
    </ul>
    ```

Which looks like
><h4>My colour list</h4>
><ol>
>    <li>Red</li>
>    <li>Orange</li>
>    <li>Yellow
>        <ul>
>            <li>Sunflower</li>
>            <li>Banana
>                <ol>
>                    <li>Frozen banana</li>
>                    <li>Non-Frozen banana</li>
>                </ol>
>            </li>
>        </ul>
>    </li>
></ol>
>
><ul>
>    <li><strong>Red</strong></li>
>    <li>Orange</li>
>    <li>Yellow</li>
></ul>

### Divs and Spans

- Divs `<div>` and spans `<span>` are not that useful without CSS
- But they are useful for grouping content together
- According to MDN, a div `<div>` is a generic container for flow content
- A span `<span>` is also a generic container, but has the key difference in that `<span>` is an inline element, whereas a div `<div>` is a block-level element

### HTML Attributes

#### Attributes

- Attributes are a way to add additional information to HTML elements
- They take the form of a key-value pair:

    ```html
    <tag name="value"></tag>
    ```

  - Where the key is a property, in the above case `name` and the value is a corresponding value, in this case `="value"`
  - Some other examples include:

    ```html
    <img src="corgi.png">

    <p class="selected">woof woof</p>

    <a href="www.google.com">Click me to go to Google</a>

    <link rel="stylesheet" type="text/css" href="style.css">
    ```

#### MDN Attribute Reference

- MDN has a comprehensive attribute reference [link](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
- You do not need to memorise all of these
- It's important to note that not every attribute works on every single element - most attributes work on 2-5 different elements

#### Images

- Note, there is no opening/closing tags as the image `<img>` tag is a **self-closing tag**

```html
<img src="corgi.png>
```

#### Anchor tags - links

- Examples:

  ```html
  <a href="url">Link text</a>

  <a href="www.google.com">Click me to go to Google</a>

  <a href="www.reddit.com">Click me to go to Reddit</a>
  ```

- Important notes for anchor `<a>` tags:
  - Anchor tags have the attribute `href` which specifies a URL/destination that the link it renders navigates to
  - It's important to specify text between opening `<a>` and closing `</a>` anchor tags or no link/text will show
  - When specifying the following anchor tag:

    ```html
    <a href="www.google.com">Click me to go to Google</a>
    ```

    - This **will not** navigate to www.google.com when opening an html file stored locally on your computer in a browser
    - This is because when you open an html file from your computer in a browser, the html is using a **file protocol**, therefore when clicking the link, your browser will think that you want to continue to use the **file protocol** and really will open `file:///Path/to/file.html`
    - To navigate to Google, you need to explicitly specify the **HTTP protocol** by including `http://` at the beginning of the url:

      ```html
      <a href="http://www.google.com">Click me to go to Google</a>
      ```

  - If however, you want to link to other pages that is not on HTTP (i.e. other pages in your website) then you do not need to specify the HTTP protocol signature
  - Also, note the difference between *relative* links and *absolute* links
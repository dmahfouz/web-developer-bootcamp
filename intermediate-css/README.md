# Intermediate CSS

## Unit Objectives

### Objectives

- Objective 1: Manipulate common font and text properties using CSS
- Objective 2: Include external fonts using Google Fonts
- Objective 3: Define and manipulate the four components of the Box Model

### Projects

- Project 1: Simple tic-tac-toe project
- Project 2: Image portfolio site
- Project 3: HTML and CSS blog

## Texts and Fonts

In this lecture we will talk about the following CSS selectors for text and fonts:

- `font-family`
- `font-size`
- `font-weight`
- `line-height`
- `text-align`
- `text-decoration`

### `font-family`

- cssfontstack.com shows different fonts available for Windows and Mac and their relative usages
- There are custom fonts, such as Google Fonts, which are available for both
- We can set the font size for a particular element/tag using the `font-family` selector

### `font-size`

- There are many approaches for using a selector to set font size
- Font size can be specified in pixels `px`
- And font size can also be specified in the unit `em`. MDN states the following

> The size of an `em` value is dynamic. When defining the `font-size` property, an `em` is equal to the font size of the element on which the `em` is used. If you haven't set the font size anywhere on the page, then it is the browser default, which is ofter 16px. So by default 1.0em = 16px, and 2em = 32px.

### `font-weight`

- The weight of a font refers to how bold, or how light the weight of a text is
- We can set the weight using the following:

    ```css
    p {
        font-weight: bold;
    }
    ```

- Some fonts will allow you to use a numeric value, which ranges from 100-800, in intervals of 100, (i.e. 100, 200, 300,...) e.g.:

    ```css
    p {
        font-weight: 100;
    }
    ```

### `line-height`

- `line-height` does as it says, which is to control the height of a given line
- This is equivalent to the idea of spacing, so `line-height: 2;` corresponds to double spacing. Note that this is relative to the size of the font

### `text-align`

- `text-align` controls the alignment of any given bit of text, whether it's to the right, the left or the centre
- `text-align` can be set values `center`, `left`, `right`, `justified`, etc

### `text-decoration`

- Text decoration is used to give text an underline effect, or a strikethrough or overline

## Google fonts

- To use Google Fonts, go to www.fonts.google.com
- We can search for the font we're looking for using the search box, in this case we might want to use the **Raleway** font
- If we click on the font, we're given the option of different weights of the font, including normal or regular weighted fonts (*Regular 400*)
- If we then click **Select this style**, a pop-out menu shows on the right
- If we then click the **Embed** tab, we're given a link that allows us to use the font in our `html` and `css` files
- We can also add other fonts, by selecting **Browse fonts** in the top menu and choosing other fonts we want to use

## Introduction to the Box Model (padding, margin, border and more!)

- One of the most important concepts in CSS is positioning of elements - i.e. how do we lay out a page or move a div to the top right, or make an anchor tag wider or add spacing between images
- All of these concerns are important and are related to something call the **box model**
- The **box model** is central to everything in CSS and is defined by MDN as the following:

    > "In a document, each element is represented as a rectangular box. In CSS, each of these rectangular boxes is described using the standard *box model*. Each box has four edges: the **margin edge**, **border edge**, **padding edge** and the **content edge**

- There are 4 properties or 4 different parts to every box that we can manipulate
- Say we have a paragraph element `<p>`:

| Box model component | Description | Chrome Inspector | CSS |
|---------------------|-------------|------------------|-----|
| **Content** | The text inside the paragraph is the **content**, this is the innermost box | *In chrome inspector this is the blue inner box* | `width: 10px;` / `height: 20%;` |
| **Padding** | The **padding** is around the **content** and inside the **border**, this is the space between the content and the border | *In chrome inspector this is the green box* | `padding: 10px;` , `padding-left: 15px;` |
| **Border** |  The **border** is around the **padding** but inside the **margin**, this is the border around the element **content** and **padding** | *In chrome inspector this is the orange box* | `border: 2px solid blue;` ; `border-top: ...;` |
| **Margin** | The **margin** is around the **border** and represents the space between elements | *In chrome inspector this is the outermost, dark orange box* | `margin: 10px 5px 20px 30px;` , `margin: 9 auto;` |

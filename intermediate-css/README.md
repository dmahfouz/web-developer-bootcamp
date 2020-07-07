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
- We can also browse fonts, by selecting **Browse fonts** in the top menu
- 
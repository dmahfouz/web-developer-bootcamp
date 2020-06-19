# Intermediate HTML

## Objectives

- **Objective 1**: Write valid HTML tables
  - **Exercise**: Pokemon Table Assignment
- **Objective 2**: Write validated HTML Forms using `<form>`, `<input>`, `<select>` and `<label>` tags
  - **Exercise**: Recreate complex form

## HTML Tables

- To specify a table we use the `<table>` element
- Within the `<table>` element, we can specify table rows using `<tr>`
- Within each `<tr>` row element, we can specify the table data cell using `<td>`
- To specify headings for our table, we can add a table row element `<tr>` that includes table header elements `<th>`
- To give more meaning to our HTML table we can specify a table head element `<thead>` containing the HTML code for the table heading, and a table body element `<tbody>` to specify the HTML code containing the body for the HTML
- Finally, without CSS, no borders will be rendered unless we use the border attribute (`<table border="1">`), however this is outdated as of HTML4 and is bad practice (we use CSS instead)
- The following shows code for a HTML table:
    ```html
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
                <th>Breed</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Rusty</td>
                <td>2</td>
                <td>Mutt</td>
            </tr>
            <tr>
                <td>Wyatt</td>
                <td>13</td>
                <td>Golden</td>
            </tr>
        </tbody>
    </table>
    ```
- Which would look like this in our browser:
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
                <th>Breed</th>
            </tr>    
        </thead>
        <tbody>
            <tr>
                <td>Rusty</td>
                <td>2</td>
                <td>Mutt</td>
            </tr>
            <tr>
                <td>Wyatt</td>
                <td>13</td>
                <td>Golden</td>
            </tr>    
        </tbody>
    </table>

### Pokemon Tables Exercise

- Use the Pokemon data in the `pokemondata.txt` file to create a table with the following:
  - Image: image of pokemon
  - Name: name of pokemon
  - Type: pokemon type
  - Evolves into: link to next evolution

- HTML code:

    ```html
    <table border="1">
        <thead>
            <tr>
                 <th>Image</th>
                 <th>Name</th>
                 <th>Type</th>
                 <th>Evolves Into</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><img src="http://img4.wikia.nocookie.net/__cb20140328190757/pokemon/images/thumb/2/21/001Bulbasaur.png/200px-001Bulbasaur.png"></td>
                <td>Bulbasuar</td>
                <td>Grass/Poison</td>
                <td><a href="http://pokemon.wikia.com/wiki/Ivysaur">Ivysaur</a></td>
            </tr>
            <tr>
                <td><img src="http://img4.wikia.nocookie.net/__cb20140724195345/pokemon/images/thumb/7/73/004Charmander.png/200px-004Charmander.png"></td>
                <td>Charmander</td>
                <td>Fire</td>
                <td><a href="http://pokemon.wikia.com/wiki/Charmeleon">Charmeleon</a></td>
            </tr>
            <tr>
                <td><img src="http://img1.wikia.nocookie.net/__cb20140328191525/pokemon/images/thumb/3/39/007Squirtle.png/200px-007Squirtle.png"></td>
                <td>Squirtle</td>
                <td>Water</td>
                <td><a href="http://pokemon.wikia.com/wiki/Wartortle">Wartortle</a></td>
            </tr>            
        </tbody>
    </table>
    ```

- HTML output

    <table border="1">
        <thead>
            <tr>
                <th>Image</th>
                <th>Name</th>
                <th>Type</th>
                <th>Evolves Into</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><img src="./imgs/001Bulbasaur.png"></td>
                <td>Bulbasuar</td>
                <td>Grass/Poison</td>
                <td><a href="http://pokemon.wikia.com/wiki/Ivysaur">Ivysaur</a></td>
            </tr>
            <tr>
                <td><img src="./imgs/004Charmander.png"></td>
                <td>Charmander</td>
                <td>Fire</td>
                <td><a href="http://pokemon.wikia.com/wiki/Charmeleon">Charmeleon</a></td>
            </tr>
            <tr>
                <td><img src="./imgs/007Squirtle.png"></td>
                <td>Squirtle</td>
                <td>Water</td>
                <td><a href="http://pokemon.wikia.com/wiki/Wartortle">Wartortle</a></td>
            </tr>            
        </tbody>
    </table>

### HTML Forms - Getting User Input

#### Objectives
- Use the `<form></form>` tag
- Use the `<input>` tag
- Use the `<label></label>` tag
- Write Simple validations

- Example forms
    - Facebook - login form
    - Twitter - sign up form
    - Google - search box

#### The `<form>` tag

- Example:

    ```html
    <form action="/my-form-submitting-page" method="post">
    <!-- All our inputs will go here -->
    </form>
    ```

- A `<form>` tag consists of:
  - action - the URL to send form data to
  - method - the type of HTTP request

- Note that, until we cover backend JS, our forms won't actually do anything
- Some other things to note about the `<form>` tag
  - The `<form>` tag is just a shell or container for different types of inputs (e.g. email form and password form, or checkboxes, buttons, drop-down menus, colour pickers, etc)
  - There are two important attributes:
    - A form will send a request somewhere, it sends data from the form to a server somewhere
    - The first attribute `action="/my-form-submitting-page"` is going to specify where to send this data (is it going to Google, our sign-up page, etc)
    - The second attribute `method="post"` specifies what type of HTTP request to send. We could send either a `GET` request (`method="get"`) or a `POST` request (`method="post"`)
      - A `GET` request is when we're trying to 'get' data by searching or retrieving it (e.g. Google search)
      - A `POST` request is when we're sending data that we want to be added to a database 'posted' to a server (Sign-up/login on FB/Twitter)

#### The `<input>` tag

- The `<input>` tag is what actually goes inside our forms
- The `<input>` tag creates interactive controls. The "type" attribute determines the type of input
- Examples:

    ```html
    <!-- text input -->
    <input type="text">

    <!-- date input -->
    <input type="date">

    <!-- color input -->
    <input type="color">

    <!-- file input -->
    <input type="file">

    <!-- checkbox input -->
    <input type="checkbox">
    ```

#### A simple form

- Example code:

    ```html
    <h1>Sign In</h1>

    <form action="/sign-in-url" method="post">
        <input type="text">
        <input type="password">
        <button>Login</button>
    </form>
    ```

- This gives the following output

><h1>Sign In</h1>
><form action="/sign-in-url" method="post">
>    <input type="text">
>    <input type="password">
>    <button>Login</button>
></form>

### Playing with input
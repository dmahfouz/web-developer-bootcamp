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
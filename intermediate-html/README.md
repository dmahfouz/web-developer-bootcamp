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

## Pokemon Tables Exercise

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

## HTML Forms - Getting User Input

### Objectives
- Use the `<form></form>` tag
- Use the `<input>` tag
- Use the `<label></label>` tag
- Write Simple validations

- Example forms
    - Facebook - login form
    - Twitter - sign up form
    - Google - search box

### The `<form>` tag

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

### The `<input>` tag

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

### A simple form

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

<h1>Sign In</h1>
<form action="/sign-in-url" method="post">
    <input type="text">
    <input type="password">
    <button>Login</button>
</form>

## Playing with inputs

- We can add inputs using the following syntax: `<input type="text">`
- There are multiple types of inputs that we can create including:
  - Text input: `<input type="text">`
  - Password: `<input type="password">`
  - Radio buttons: `<input type="radio">`
  - Colour picker: `<input type="color>`
  - And many [more](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- We can also add placeholders using the `<placeholder="">` attribute
  - For example we can add a placeholder for username <input type="text" placeholder="username"/>
  - Or we could add a placeholder for password <input type="password" placeholder="password"/>

## The Form Tag

- A form `<form>` is a container for multiple `<input>` tags. Although it is possible for `<input>` tags to exist without a form, if we want to package up multiple `<input>` tags together we would use a `<form>` tag
- A `<form>` has two attributes: `action` and `method`
  - `action`: is where the form sends the data to
  - `method`: what HTTP method do we use (`get`/`post`)
- If we were to set the `action=http://wikipedia.org` and `method="GET"`, the form would send the data entered in `<input>` fields to wikipedia.org
- Note that instead of sending the data to Wikipedia, we would actually normally send it to our own server or back-end
- When we submit the form, the data is sent with the request. We can see this by assigning a `name` attribute to our `<input>` tags:

    ```html
    <form>
        <input name="username" type="text" placeholder="username">
        <input name="password" type="password" placeholder="password">
        <input type="submit">
    </form>
    ```

- If we then enter a username "_Rusty_", and a password "_123_", the data appended to the URL in the form of a query string, i.e.:

    file:///Users/../forms.html<b>?username=Rusty&password=123</b>

- Note that we don't let the user or any user doesn't see the password, 1). because of obvious security risks and 2). because we usually use a `POST` request rather than a `GET` request
- When the data is entered in to a form and the submit button is clicked, the data is taken out of that form and a request is sent somewhere
- If we were to change our html to have `<form action=http://www.wikipedia.org>`:

    ```html
    <form action="http://www.wikipedia.org">
        <input name="username" type="text" placeholder="username">
        <input name="password" type="password" placeholder="password">
        <input type="submit">
    </form>
    ```

    Then when we enter username _"Rusty"_ and password _"test123"_ and click the submit button, we are taken to Wikipedia **and** our data added via a query string to the URL

    https://wikipedia.org/?username=Rusty&password=test123

## Labels

- Labels are exactly what they sound like: they let us add captions to individual elements in our form
- The reason we use labels `<label>` is that rather than just having a paragraph or some plain text, labels are really important for making a site accessible
- If someone is visually impaired or blind and they're trying to access our form or trying to sign up, their screen reader software that they're using is going to look for label tags and it's going to use those labels to know what part of the form corresponds to
-There are two syntaxes we're going to cover:
  - In the first syntax, we nest our `<input>` forms within a `<label>` tag, in the case below we have label tags for username and password, with the label text 'Username:' and 'Password' and their corresponding `<input>` tags

    ```html
    <form action="/sign-in-url" method="post">
        <label>Username: <input type="text"></label>
        <label>Password: <input type="password"></label>
        <button>Login</button>
    ```

  - In the second syntax, instead of nesting our `<input>`s inside of our `<label>`s, we connect them using `for=` and `id=` attributes. As long as these match, screen readers and accessibility software will know that these two items correspond to each other

    ```html
    <form action="/sign-in-url" method="post">
      <label for="username">Username:</label>
      <input id="username" type="text">
      <label for="password">Password:</label>
      <input id="password" type="password">
      <button>Login</button>
    </form>
    ```

## (HTML5) Form validations - simple validations

- Form validations are the ability to enforce rules and structure on different parts of a form (e.g. you cannot leave your email blank, your password must be greater than 10 characters, your email must follow a valid email syntax)
- The 'required' attribute validates that an input is not empty
- There are also type validations. Try changing "type" from "text" to "email"
- Example HTML:

    ```html
    <form action="/sign-in-url" method="post">
        <label for="email">Email:</label>
        <input id="email" type="email" required>
        <label for="password">Password:</label>
        <input id="password" type="password" required>
    </form>
    ```

- Note that validation is fairly limited in HTML only, but there are two mains types of validation that can be done in HTML
    1. Presence validation - this is denoted by the `required` attribute in the `<input>` tags, this enforces forms such as usernames and passwords to be non-empty when the submit button is clicked
    2. Validation of the data type or format of the data - this is denoted by the `type` atribute and enforces for example whether an email looks like an email and has the correct format, i.e. person@mail.com

## Dropdowns and radio buttons

- In this section we are going to talk about 3 addition `<input>` types:
    1. Radio button / checkboxes
    2. Select tag (drop down menus)
    3. Text area - multi-line text input field

### Radio buttons and checkboxes

- The difference between a radio button and checkbox is that a radio button cannot be unclicked/toggled whereas a checkbox can
- A radio button is typically used when there is only one option, e.g. select gender (male/female)
- A checkbox is used when there are multiple options/choices of which not all need to be clicked/toggled
- When creating radio buttons there are a few things we need to consider:

    ```html
    <p>Do you prefer cats or dogs?</p>
    <form>
        <label for="dogs">Dogs: </label>
        <input name="petChoice" id="dogs" type="radio" value="DOGS">

        <label for="cats">Cats:</label>
        <input name="petChoice" id="cats" type="radio" value="CATS">

        <button>Go!</button>
        <!-- ^ equivalent to: <input type="submit"> -->
    </form>
    ```

    1. If we have a question "do you prefer cats or dogs?" and we assign a radio button to the option of cat and dog, to ensure that only one radio button can be clicked, we need to ensure that the `<input>` tag for both the cat and dog radio button have the same attribute value, so that they are linked

    2. If a button is the last element in the form, this will act as the submit action for the form, this is similar to adding a final `<input>` tag with the attribute `type` set to submit

    3. We need to assign a `value` attribute to each `<input>` tag in order for the query string to be populated with something recognisable, i.e. `<input name="petChoice" ... value="DOGS>` and `<input name="petChoice" ... value="CATS">`. What this does is if the "dog" radio button is clicked, then under the name `petChoice` store the value `DOGS` otherwise if the "cat" radio button is clicked, the the value `CATS` under the name `petChoice`
        - This ensures that if the "dog" radio button is clicked the query string will be `file:///Path/to/inputs.html?petChoice=DOGS` and if the "cat" radio button is clicked the query string will be `file:///Path/to/inputs.html?petChoice=CATS`

### Drop-downs using the `<select>` tag

- The `<select>` tag allows us to create nice-drop down menus
- To add options to choose from in the drop down menu we can add the `<option>` tag for each option
- If we have a submit `<button>` or a submit input tag `<input type="submit">`, and we press submit, nothing will be added to the query string for the drop-down menu we have defined
- Therefore to remedy this, we need to add a `name` attribute to the `<select>` tag, i.e.: `<select name="colour">`, as follows:

    ```html
    <form>
        <p>What's your favourite colour</p>
        <select name="colour">
            <option>Red</option>
            <option>Orange</option>
            <option>Yellow</option>
        </select>
        <button>Go!</button>
    </form>	
    ```

- Then, when we select an option and click the go button, we will have a query string for our drop-down that looks like: `../inputs.html?colour=Orange`
- Note that for the `<option>` selected, the browser takes whatever text is inside (in this case 'Orange') and stores that as a value under the `name` attribute `"colour"`
- So we don't always want the value that is sent along in the request to be identical to whatever is displayed in the `<option>` tag
- If we want to send a custom value, we can use the `value` attribute in the `<option>` tag, for example, if we have a drop-down menu for moods and for each mood we have an emoticon, instead of sending the value of the emoticon, we can define custom values in the `value` attribute, as follows:

    ```html
    <p>What's your current mood?</p>
    <select name="mood">
        <option value="happy">:)</option>
        <option value="neutral">:|</option>
        <option value="sad">:(</option>
    </select>
    ```

### Multi-line inputs using `<textarea>` 

- The `<textarea>` tag is another tag like `<select>` and is not an `<input>` with a type
- We can create multi-line forms using the `<textarea>` tag, which  can be useful for when we ask the user to enter a resume or a bio, and there is a multi-line text input form to fill in rather than a single-line form using `<input type="text">`
- We can specify the size of the `<textarea>` form using attributes such `rows` and `cols`, for example:

    ```html
    <textarea rows="10" cols="50"></textarea>
    ```

- Just like the other elements that have been discussed, if we want to send data (from the `<textarea>` form) in the request, then we need to give the `<textarea>` element a `name` attribute, as follows:

    ```html
    <textarea name="paragraph" rows="10" cols="50"></textarea>
    ```

## Forms Exercise

### Creating a Registration Form

- This project will cover topics discussed in the last few videos including
  - `<form>` tags
  - different types of `<input>` tags such as radio buttons and drop-down menus
  - Validations and labels
- You're going to combine these elements to make a registration form for some fake website
- The registration form will include:
  - First name and last name text forms
  - Male/Female radio buttons
  - Email text form
  - Birthday: (month/day/year) dropdowns
  - Check-box for agreeing to terms and conditions
  - A submit button

### Validations

- First name, last name and email cannot be blank
- Email must be a valid email address
- **Bonus**: include validation to ensure password is between 5 and 10 characters (using only HTML5)
- [Solution](formsExercise.html)
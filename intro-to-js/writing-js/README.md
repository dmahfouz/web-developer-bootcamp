# Section 10: Introduction to JavaScript

## Recap

- HTML is often considered as the *nouns* in web development
- CSS is considered as the *adjectives* (stylings for the nouns)
- JavaScript is considered as the *verbs*

## Unit Objectives

- **Objective 1**: Evaluate JS using the developer console
- **Objective 2**: List the 5 JS primitives
- **Objective 3**: Define variables with the *var* keyword
- **Objective 4**: Write code using *`console.log`*, *`alert`*, and *`prompt`*

## The JavaScript Console

In Chrome, we can go to the JavaScript console by either:

- Inspecting the page and hitting the "console" tab
- (On Windows), hit Ctrl+Shift+i for Chrome inspector and navigate to the "console" tab
- Pressing Ctrl+Shift+j to go directly to the JavaScript console

## Primitives

### Objectives

- Introduce the 5 primitive data types
- Work with numbers and numeric operators
- Work with strings and common string methods

### 4 Primitive Datatypes

In JavaScript, there are five low level basic types of data

1. Numbers
2. Strings
3. Booleans
4. `null`
5. `undefined`

```js
// Numbers - note: in js there is no
// distinction between types of numbers
4
9.3
-10

// Strings - text; inside of quotes
"Hello World"
"43"

// Booleans - true or false
true
false

// null and undefined - these are values
null
undefined
```

### Numbers

```js
// Numbers
4
9.3
10

// We can do arithmetic in js
4 + 10      //14
1/5         //0.2

//Modulo - remainder operator
10 % 3      // 1
24 % 2      // 0
15 % 11     // 4
```

### Strings

```js
// Single or double quotes are ok
"hello world"
'hello world'

// Concatenation
"charlie" + "brown"     // "charliebrown"

// Escape characters start with "\"
"Singin \"Do wah diddy, diddy, dum diddy do\" "
"This is a backslash: \\"

// Strings have a `length` property
"hello world".length    // 11

// Access individual characters using [] and an index
"hello"[0]  //"h"
"hello"[4]  //"o"
```

## Primitives Exercise

Solve the following (in js) without using js:

```js
//1.
100 % 3     // 1

//2.
("blah" + "blah")[6]    // "a"

//3.
"hello".length % "hi\\".length  // 2
```

## Variables

This section focusses on Javascript variables and their syntax. Variables are a concept that exists in every programming language and is just a container that has a name and inside of that container we store some data.

Below are some examples of variables defined in Javascript

```js
// Variables are simply containers that store values
// They follow the pattern below
var yourVariableName = yourValue;

// They can store all the values that we've discussed
var name = "Rusty";
var secretNumber = 73;
var isAdorable = true;

// Recall the stored value by calling the variable name
var name = "Rusty";
"hello there " + name   // "hello there Rusty"

var num = 37;
num + 3 + 10    // 50

// We can also update existing variables
var name = "Robert";
name = "Bob";
```

## **`const`**, **`let`** and **`var`**

### Some history

- When JavaScript was created in 1997, variables were defined using **`var`**
- In 2015, **`let`** & **`const`** were introduced

### Browser support

- As of 2018, all the major browsers support **`const`**
- As of 2018, **not** all of the major browsers support **`let`** (such as Opera Mini, Android browser, etc)

### When to use **`var`**, **`const`** and **`let`**

#### **`var`**

- **`var`** is scoped to "current execution context"
  - AKA a variable's enclosing function or the global scope
- Can be reassigned anytime
- Initialising with a value is optional
- Can be redeclared at any point
- Global variables are added to window

For example:

```js
function greet() {
    for (var i = 0; i <3; i++) {
        console.log("Hello!");
    }
    console.log(i);
}
```

### **`let`**

- **Block scoped**
- Does not create property on global window object
- Initialising w/ value is optional
- Can be reassigned
- Cannot be redeclared (in same scope)

### **`const`**

- **Cannot be reassigned** (i.e. **`const`** stands for "constant")
  - Not immutable, but variable reference cannot change
- **Block scoped**
- Must be initialised with a value
- Does not create property on global window object
- Cannot be redeclared (in same scope)

The table below shows the differences between **`var`**, **`let`** & **`const`**:

| Property | **`var`** | **`let`** | **`const`** |
|----------|-------|-------|---------|
| Scoping  | Global / current execution context | Block | Block |
| Reassignable? | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Requires initialising with a value? | :x: | :x: | :heavy_check_mark: |
| Creates property on global window object? | :heavy_check_mark: | :x: | :x: |
| Can be redeclared? | :heavy_check_mark: | :x: | :x: |

### Concluding notes

- *Prefer **`const`** over **`let`***
- *Prefer **`let`** over **`var`***
- *Use **`var`** pretty much never* (you probably don't need it)

## `null` and `undefined`

```js
// The two other primitives are null and undefined

// Variables that are declared but not
// initialised are undefined

// The following variables are undefined:
var name;
var age;

// null is "explicitly empty/nothing"
var currentPlayer = "charlie";
currentPlayer = null;   // game over
```

## Useful Built-in Methods

### **`clear`**

- **`clear()`** is a built-in method, that can be used to clear the Javascript console

### **`alert`**, **`prompt`** & **`console.log`**

- **`alert`** essentially pops up (alerts) a message to the user. When it is used a pop-up will appear with the message contents, e.g.:

    ```js
    alert("This is a pop up!");
    ```

- **`console.log`** prints a message to the javascript console, e.g.:

    ```js
    console.log("Hello from the console!");
    ```

- **`prompt`** is useful for getting input from a user, e.g.:

    ```js
    var userName = prompt("What is your name?");
    ```

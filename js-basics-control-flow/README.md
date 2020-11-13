# Section 11: Javascript Basics: Control Flow

## Unit Objectives

- **Objective 1**: Evaluate complex logical expression
- **Objective 2**: Write 3-part JS conditional statements
- **Objective 3**: Write JS `while` loops and `for` loops
- **Objective 4**: Translate between `while` and `for` loops

## Boolean Logic: True, False and Beyond

- Everything starts with the idea that a statement is either True or False
- Then we can combine those initial statements to create more complex statements that also evaluate to True or False

## Comparison Operators (in Javascript)

*Assuming `x=5`

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| `>` | Greater than | `x > 5` | `false` |
| `>=`| Greater than or equal to | `x >= 5` | `true` |
| `<` | Less than | `x < -50` | `false` |
| `<=`| Less than or equal to | `x <= 100` | `true` |
| `==`| Equal to | `x=="5"` | `true` |
| `!=` | Not equal to | `x != "b"` | `true` |
| `===` | Equal value and type | `x === "5"` | `false` |
| `!==` | Not equal value or equal type | `x !== "5"` | `true` |

### Equality Operators: `==` vs. `===`

`"=="` performs ***type coercion***, while `"==="` does not:

```js
var x = 99;
x == "99" // true
x === "99" // false

var y = null;
y == undefined // true
y === undefined // false

```

As a rule of thumb, always use `===`, it is much safer and much more **specific**

### Some edge cases

```js
true == "1"  // true
0 == false   // true
null == undefined // true
NaN == NaN        // false
```

## Logical Operators: AND, OR, and NOT

| Operator | Name | Example | Result |
|----------|------|---------|--------|
| **`&&`** | AND  | **`x < 10 && x!== 5`** | **`false`** |
| **`||`** | OR   | **`y > 9 || x === 5`** | **`true`**  |
| **`!`**  | NOT  | **`!(x === y)`** | **`true`** |

\* Assuming **`x = 5`** and **`y = 9`**

### Exercise 1

```js
var x = 10;
var y = "a";

y === "b" || x >= 10    // true
```

### Exercise 2

```js
var x = 3;
var y = 8;

!(x == "3" || x === y) && !(y != 8 && x <= y) // false
```

### "Truth-y" and "False-y" Values

- Values that aren't actually *true* or *false*, are still inherently "truth-y" or "false-y" when evaluated in a boolean context

```js
!"Hello World"
!""             // true
!null           // true
!0              // true
!-1             // false
!NaN            // true
```

### Hard and fast rule for "truth-y"/"false-y" values

- "Falsey" values:
  - `false`
  - `0`
  - `""`
  - `null`
  - `undefined`
  - `NaN`
- Everything else is "Truthy"

### Exercise 3

```js
var str = "";   // falsey
var msg = "haha!";  // truthy
var isFunny = "false"; // truthy

!(( str || msg ) && isFunny)   // false
```

## Javascript Conditionals: making decisions with code

### Examples

- **User login**: when a user logs in on a website and types a password in a form, there is code that checks that password that you typed in against the password in the database. If they match the user logs into the site and gets redirected to another page. If they **don't** match, the user gets an error message of some sort. These are the two available paths from the same code

- **Buying something online**: when a user buys something online and types in their credit card information, if the transaction goes through the user gets a confirmation email and sees a success screen, otherwise if there's a problem with the info provided or insufficient funds available, then the user gets an error message

### `if`, `else if`, `else`

#### Bouncer exercise

- If you are younger than 18:
  - You cannot enter the venue
- If you are between 18 and 21:
  - You can enter, but cannot drink
- Otherwise:
  - You can enter and drink

#### Exercises

Add the following logic:

- If age is negative,
  - Print an error message
- If age is (exactly) 21,
  - Print "happy 21st birthday! have a free shot"
- If age is odd,
  - Print "you age is odd!"
- (Bonus) if age is a perfect square,
  - Print "perfect square"

```js
// Get age and convert it to a Number (prompt always returns a String)
var age = Number(prompt("What is your age?"));

// negative age
if(age < 0) {
    console.log("Error, you cannot have a negative age!");
}

// age is a perfect square
if((age**0.5) % 1 == 0) {
    console.log("Perfect square!");
}

// If age is a perfect square
if(age % Math.sqrt(age) === 0) {
  console.log("Your age is a perfect square!");
}

// odd age (all ages > 0)
if((age % 2) !== 0) {
    console.log("Your age is odd!");
}

// age is exactly 21yrs
if (age === 21) {
    console.log("Happy 21st Birthday! Have a free shot!")
}

// less than 18yrs
if(age < 18) {
    console.log("Sorry, you are not old enough to enter the venue");
}

// 18 < age < 21
else if (age < 21) {
    console.log("You can enter, but cannot drink");
}

// age > 21 yrs
else {
    console.log("You can enter and drink");
}
```

## Simple Guessing Game

We want to create a game where we have Javascript code that will prompt a user for a number which it can then check against a pre-defined `secretNumber` and tell the user if they guessed right.

We could use the following code to try this:

```js
// create secretNumber
var secretNumber = 4;

// ask user for guess
var guess = prompt("Guess a number");

// check if guess is right
if (guess === secretNumber) {
    alert("YOU GOT IT RIGHT!");
}
```

**However**, this will fail, because the variable `guess` is stored as a string. We *could* use the double operator `==` to check the number against a string, *or* we could use the code:

  ```js
  if (Number(guess) === secretNumber) {
    alert("YOU GOT IT RIGHT!");
  }
  ```

which will coerce the string `guess` to a number and still allow us to use the triple-equals (`===`) operator.

## Introduction to Loops

### Objectives

- Understand the purpose of loops
- Define "DRY" (**D**on't **R**epeat **Y**ourself) code
- Write simple while loops

### What if I wanted to print the numbers from 1-5?

We could do something like below (already not that ideal):

  ```js
  console.log(1);
  console.log(2);
  console.log(3);
  console.log(4);
  console.log(5);
  ```

What if we wanted to print numbers from 1-10,000? This is where loops come in.

**NB**: Although it would be unlikely in a production application setting to do this, what we might do, for example on something like Facebook where each post can have up to 10,000 comments is to loop through those comments to show them on the page.

### DRY: Don't repeat yourself

- We want to keep our code as DRY as possible. It saves us a lot of time and makes our code cleaner.

### While Loops

- Repeat code **WHILE** a condition is true

  ```js
  while (someCondition) {
    // run some code
  }
  ```

- Very similar to an if statement, except it repeats a given code block instead of just running it once

#### Printing numbers from 1-5 using a `while` loop:

  ```js
  var count = 1;

  while (count < 6) {
    console.log("count is: " + count)
    count++;
  }

  // count is: 1
  // count is: 2
  // count is: 3
  // count is: 4
  // count is: 5
  ```

#### Print each character in a string using a `while` loop:

  ```js
  // string we're looping over
  var str = "hello";

  // first character is at index 0
  var count = 0;

  while (count < str.length) {
    console.log(str[count]);
    count++;
  }

  //"h"
  //"e"
  //"l"
  //"l"
  //"o"

  ```

#### Beware of infinite loops!

- Infinite loops occur when the terminating condition in a loop is never true

```js
var count = 0;

while (count < 10) {
  // loop never exits as `count` does not change
  console.log(count);
}
```

- Although some browsers and IDEs may warn beforehand of bad code or an infinite loop occurring, these still pose the risk of crashing your browser or computer so make sure to avoid these!

### While Loops exercises

#### While Loop Exercise 1

```js
var num = 1;

while (num <= 10) {
  console.log(num);
  num += 2;
}

// Answer: returns ->
// 1
// 3
// 5
// 7
// 9
```

#### While Loop Exercise 2

```js
var num = 1;

while (num <= 20) {
  if (num % 4 === 0) {
    console.log(num);
  }
  num++;
}

// Answer: returns ->
// 4
// 8
// 12
// 16
// 20
```


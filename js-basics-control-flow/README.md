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

### "Truthy" and "Falsey" Values

- Values that aren't actually *true* or *false*, are still inherently "truthy" or "falsey" when evaluated in a boolean context

```js
!"Hello World"
!""             // true
!null           // true
!0              // true
!-1             // false
!NaN            // true
```

### Hard and fast rule for "truthy"/"falsey" values

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


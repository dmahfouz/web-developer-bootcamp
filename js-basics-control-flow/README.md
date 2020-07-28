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


<div align="center">
  <h1>JavaScript</h1>
</div>

[<< Non-Primitive Data Types](../05_nonPrimitiveDataTypes/nonPrimitiveDataTypes.md) | [Conditionals >>](../07_conditionals/conditionals.md)

# Operators

- [Operators](#operators)
  - [Assignment operators](#assignment-operators)
  - [Arithmetic Operators](#arithmetic-operators)
  - [Comparison Operators](#comparison-operators)
  - [Logical Operators](#logical-operators)
  - [Increment Operator](#increment-operator)
  - [Decrement Operator](#decrement-operator)
  - [Ternary Operators](#ternary-operators)
  - [Operator Precedence](#operator-precedence)

### Assignment operators

An equal sign in JavaScript is an assignment operator. It uses to assign a variable.

```js
let firstName = "Asabeneh";
let country = "Finland";
```

Assignment Operators

![Assignment operators](../images/assignment_operators.png)

### Arithmetic Operators

Arithmetic operators are mathematical operators.
| Operator| Name | Purpose |Example|
|:----:|:----:|:---------------------:|:------------:|
|`+`| Addition | Adds two numbers together. | `6 + 9`|
| `-`| Subtraction | Subtracts the right number from the left. | `20 - 15` |
| `*` |Multiplication | Multiplies two numbers together. | `3 * 7`|
| `/` | Division | Divides the left number by the right. | `10 / 5` |
| `%` | Remainder | Returns the remainder left over after you've divided the left number into a number of integer portions equal to the right number. | `8 % 3` |
|`**` | Exponent | Raises a base number to the exponent power, that is, the base number multiplied by itself, exponent times. | `5 ** 2` (returns `25`, which is the same as `5 \* 5`).|

- Addition(+): a + b
- Subtraction(-): a - b
- Multiplication(_): a _ b
- Division(/): a / b
- Modulus(%): a % b
- Exponential(**): a ** b

```js
let numOne = 4;
let numTwo = 3;
let sum = numOne + numTwo;
let diff = numOne - numTwo;
let mult = numOne * numTwo;
let div = numOne / numTwo;
let remainder = numOne % numTwo;
let powerOf = numOne ** numTwo;

console.log(sum, diff, mult, div, remainder, powerOf); // 7,1,12,1.33,1, 64
```

```js
const PI = 3.14;
let radius = 100; // length in meter

//Let us calculate area of a circle
const areaOfCircle = PI * radius * radius;
console.log(areaOfCircle); //  314 m

const gravity = 9.81; // in m/s2
let mass = 72; // in Kilogram

// Let us calculate weight of an object
const weight = mass * gravity;
console.log(weight); // 706.32 N(Newton)

const boilingPoint = 100; // temperature in oC, boiling point of water
const bodyTemp = 37; // body temperature in oC

// Concatenating string with numbers using string interpolation
/*
 The boiling point of water is 100 oC.
 Human body temperature is 37 oC.
 The gravity of earth is 9.81 m/s2.
 */
console.log(
  `The boiling point of water is ${boilingPoint} oC.\nHuman body temperature is ${bodyTemp} oC.\nThe gravity of earth is ${gravity} m / s2.`
);
```

**[⬆ Back to Top](#Operators)**

### Comparison Operators

In programming we compare values, we use comparison operators to compare two values. We check if a value is greater or less or equal to other value.

![Comparison Operators](../images/comparison_operators.png)
**Example: Comparison Operators**

```js
console.log(3 > 2); // true, because 3 is greater than 2
console.log(3 >= 2); // true, because 3 is greater than 2
console.log(3 < 2); // false,  because 3 is greater than 2
console.log(2 < 3); // true, because 2 is less than 3
console.log(2 <= 3); // true, because 2 is less than 3
console.log(3 == 2); // false, because 3 is not equal to 2
console.log(3 != 2); // true, because 3 is not equal to 2
console.log(3 == "3"); // true, compare only value
console.log(3 === "3"); // false, compare both value and data type
console.log(3 !== "3"); // true, compare both value and data type
console.log(3 != 3); // false, compare only value
console.log(3 !== 3); // false, compare both value and data type
console.log(0 == false); // true, equivalent
console.log(0 === false); // false, not exactly the same
console.log(0 == ""); // true, equivalent
console.log(0 == " "); // true, equivalent
console.log(0 === ""); // false, not exactly the same
console.log(1 == true); // true, equivalent
console.log(1 === true); // false, not exactly the same
console.log(undefined == null); // true
console.log(undefined === null); // false
console.log(NaN == NaN); // false, not equal
console.log(NaN === NaN); // false
console.log(typeof NaN); // number

console.log("mango".length == "avocado".length); // false
console.log("mango".length != "avocado".length); // true
console.log("mango".length < "avocado".length); // true
console.log("milk".length == "meat".length); // true
console.log("milk".length != "meat".length); // false
console.log("tomato".length == "potato".length); // true
console.log("python".length > "dragon".length); // false
```

Try to understand the above comparisons with some logic. Remembering without any logic might be difficult.
JavaScript is somehow a wired kind of programming language. JavaScript code run and give you a result but unless you are good at it may not be the desired result.

As rule of thumb, if a value is not true with `==` it will not be equal with `===`. Using `===` is safer than using `==`. The following [link](https://dorey.github.io/JavaScript-Equality-Table/) has an exhaustive list of comparison of data types.

**[⬆ Back to Top](#Operators)**
### Logical Operators

The following symbols are the common logical operators:
`&&(ampersand)` , `||(pipe)` and `!(negation)`.
The `&&` operator gets true only if the two operands are true.
The `||` operator gets true either of the operand is true.
The `!` operator negates true to false and false to true.

```js
// && ampersand operator example

const check = 4 > 3 && 10 > 5; // true && true -> true
const check = 4 > 3 && 10 < 5; // true && false -> false
const check = 4 < 3 && 10 < 5; // false && false -> false

// || pipe or operator, example

const check = 4 > 3 || 10 > 5; // true  || true -> true
const check = 4 > 3 || 10 < 5; // true  || false -> true
const check = 4 < 3 || 10 < 5; // false || false -> false

//! Negation examples

let check = 4 > 3; // true
let check = !(4 > 3); //  false
let isLightOn = true;
let isLightOff = !isLightOn; // false
let isMarried = !false; // true
```
**[⬆ Back to Top](#Operators)**
### Increment Operator

In JavaScript we use the increment operator to increase a value stored in a variable. The increment could be pre or post increment. Let us see each of them:

1. Pre-increment

```js
let count = 0;
console.log(++count); // 1
console.log(count); // 1
```

1. Post-increment

```js
let count = 0;
console.log(count++); // 0
console.log(count); // 1
```

We use most of the time post-increment. At least you should remember how to use post-increment operator.

**[⬆ Back to Top](#Operators)**
### Decrement Operator

In JavaScript we use the decrement operator to decrease a value stored in a variable. The decrement could be pre or post decrement. Let us see each of them:

1. Pre-decrement

```js
let count = 0;
console.log(--count); // -1
console.log(count); // -1
```

2. Post-decrement

```js
let count = 0;
console.log(count--); // 0
console.log(count); // -1
```

**[⬆ Back to Top](#Operators)**
### Ternary Operators

Ternary operator allows to write a condition.
Another way to write conditionals is using ternary operators. Look at the following examples:

```js
let isRaining = true;
isRaining
  ? console.log("You need a rain coat.")
  : console.log("No need for a rain coat.");
isRaining = false;

isRaining
  ? console.log("You need a rain coat.")
  : console.log("No need for a rain coat.");
```

```sh
You need a rain coat.
No need for a rain coat.
```

```js
let number = 5;
number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`);
number = -5;

number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`);
```

```sh
5 is a positive number
-5 is a negative number
```

**[⬆ Back to Top](#Operators)**

### Operator Precedence
Operator precedence determines how operators are parsed concerning each other. Operators with higher precedence become the operands of operators with lower precedence.

```js
console.log(3 + 4 * 5); // 3 + 20
// Expected output: 23

console.log(4 * 3 ** 2); // 4 * 9
// Expected output: 36

let a;
let b;

console.log(a = b = 5);
// Expected output: 5
```
##### Precedence And Associativity
Consider an expression describable by the representation below, where both `OP1`and `OP2` are fill-in-the-blanks for OPerators.

```js
a OP1 b OP2 c
```
The combination above has two possible interpretations:

```js
(a OP1 b) OP2 c
a OP1 (b OP2 c)
```
Which one the language decides to adopt depends on the identity of OP1 and OP2.

If `OP1` and `OP2` have different precedence levels (see the table below), the operator with the higher precedence goes first and associativity does not matter. Observe how multiplication has higher precedence than addition and executed first, even though addition is written first in the code.

```js
console.log(3 + 10 * 2); // 23
console.log(3 + (10 * 2)); // 23, because parentheses here are superfluous
console.log((3 + 10) * 2); // 26, because the parentheses change the order
```

Within operators of the same precedence, the language groups them by associativity. Left-associativity (left-to-right) means that it is interpreted as `(a OP1 b) OP2 c`, while right-associativity (right-to-left) means it is interpreted as `a OP1 (b OP2 c)`. Assignment operators are right-associative, so you can write:

```js
a = b = 5; // same as writing a = (b = 5);
```

with the expected result that `a` and `b` get the value `5`. This is because the assignment operator returns the value that is assigned. First,`b` is set to `5`. Then the a is also set to 5 — the return value of `b = 5`, a.k.a. right operand of the assignment.

As another example, the unique exponentiation operator has right-associativity, whereas other arithmetic operators have left-associativity.

```js
const a = 4 ** 3 ** 2; // Same as 4 ** (3 ** 2); evaluates to 262144
const b = 4 / 3 / 2; // Same as (4 / 3) / 2; evaluates to 0.6666...
```

Operators are first grouped by precedence, and then, for adjacent operators that have the same precedence, by associativity. So, when mixing division and exponentiation, the exponentiation always comes before the division. For example, `2 ** 3 / 3 ** 2` results in `0.8888888888888888` because it is the same as `(2 ** 3) / (3 ** 2)`.

I would like to recommend you to read about operator precedence from this [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

**[⬆ Back to Top](#Operators)**

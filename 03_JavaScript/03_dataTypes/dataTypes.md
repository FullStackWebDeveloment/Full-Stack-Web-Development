<div align="center">
  <h1>JavaScript</h1>
</div>

[<< Variables](../02_variables/variables.md) | [Primitive Data Types>>](../04_primitiveDataTypes/primitiveDataTypes.md)

# Data Types

- [Data Types](#data-types)
  - [Primitive Data Types](#primitive-data-types)
  - [Non-Primitive Data Types](#non-primitive-data-types)
  - [Primitive and Non-primitive Data types means](#Now,-let-us-see-what-exactly-primitive-and-non-primitive-data-types-mean.)

## Data Types

In the previous section, we mentioned a little bit about data types. Data or values have data types. Data types describe the characteristics of data. Data types can be divided into two:

1. Primitive data types
2. Non-primitive data types(Object References)

### Primitive Data Types

Primitive data types in JavaScript include:

1.  Numbers - Integers, floats
2.  Strings - Any data under single quote, double quote or backtick quote
3.  Booleans - true or false value
4.  Null - empty value or no value
5.  Undefined - a declared variable without a value
6.  Symbol - A unique value that can be generated by Symbol constructor
7.  BigInt - type is a numeric primitive in JavaScript that can represent integers with arbitrary magnitude
    | S.No | Type | `typeof` return value |Object wrapper|
    |:----:|:----:|:---------------------:|:------------:|
    | 1 |Null|`"object"`|N/A|
    | 2 |Undefined|`"undefined"`|N/A|
    | 3 |Boolean|`"boolean"`|Boolean|
    | 4 |Number|`"number"`|Number|
    | 5 |BigInt|`"bigint"`|BigInt|
    | 6 |String|`"string"`|String|
    | 7 |Symbol|`"string"`|Symbol|

`Note:The object wrapper classes' reference pages contain more information about the methods and properties available for each type, as well as detailed descriptions for the semantics of the primitive types themselves.`

**[⬆ Back to Top](#Data-Types)**

### Non-Primitive Data Types

Non-primitive data types in JavaScript includes:

1. Objects
2. Arrays

**[⬆ Back to Top](#Data-Types)**
### Now, let us see what exactly primitive and non-primitive data types mean.

_Primitive_ data types are immutable(non-modifiable) data types. Once a primitive data type is created we cannot modify it.

**Example:**

```js
let word = "JavaScript";
```

If we try to modify the string stored in variable _word_, JavaScript should raise an error. Any data type under a single quote, double quote, or backtick quote is a string data type.

```js
word[0] = "Y";
```

This expression does not change the string stored in the variable _word_. So, we can say that strings are not modifiable or in other words immutable.
Primitive data types are compared by its values. Let us compare different data values. See the example below:

```js
let numOne = 3;
let numTwo = 3;

console.log(numOne == numTwo); // true

let js = "JavaScript";
let py = "Python";

console.log(js == py); //false

let lightOn = true;
let lightOff = false;

console.log(lightOn == lightOff); // false
```
**[⬆ Back to Top](#Data-Types)**
### Non-Primitive Data Types

_Non-primitive_ data types are modifiable or mutable. We can modify the value of non-primitive data types after it gets created.
Let us see by creating an array. An array is a list of data values in a square bracket. Arrays can contain the same or different data types. Array values are referenced by their index. In JavaScript array index starts at zero. I.e., the first element of an array is found at index zero, the second element at index one, and the third element at index two, etc.

```js
let nums = [1, 2, 3];
nums[0] = 10;

console.log(nums); // [10, 2, 3]
```

As you can see, an array, which is a non-primitive data type is mutable. Non-primitive data types cannot be compared by value. Even if two non-primitive data types have the same properties and values, they are not strictly equal.

```js
let nums = [1, 2, 3];
let numbers = [1, 2, 3];

console.log(nums == numbers); // false

let userOne = {
  name: "Sathish Sampath",
  role: "developer",
  country: "india",
};

let userTwo = {
  name: "Sathish Sampath",
  role: "developer",
  country: "india",
};

console.log(userOne == userTwo); // false
```

Rule of thumb, we do not compare non-primitive data types. Do not compare arrays, functions, or objects.
Non-primitive values are referred to as reference types, because they are being compared by reference instead of value. Two objects are only strictly equal if they refer to the same underlying object.

```js
let nums = [1, 2, 3];
let numbers = nums;

console.log(nums == numbers); // true

let userOne = {
  name: "Sathish Sampath",
  role: "developer",
  country: "india",
};

let userTwo = userOne;

console.log(userOne == userTwo); // true
```

If you have a hard time understanding the difference between primitive data types and non-primitive data types, you are not the only one. Calm down and just go to the next section and try to come back after some time.

**[⬆ Back to Top](#Data-Types)**

## Checking Data Types and Casting

### Checking Data Types

To check the data type of a certain variable we use the _typeof_ method.

**Example:**

```js
// Different javascript data types
// Let's declare different data types

let firstName = "Sathish"; // string
let lastName = "Sampath"; // string
let country = "India"; // string
let city = "Chennai"; // string
let age = 250; // number, it is not my real age, do not worry about it
let job; // undefined, because a value was not assigned

console.log(typeof "Sathish"); // string
console.log(typeof firstName); // string
console.log(typeof 10); // number
console.log(typeof 3.14); // number
console.log(typeof true); // boolean
console.log(typeof false); // boolean
console.log(typeof NaN); // number
console.log(typeof job); // undefined
console.log(typeof undefined); // undefined
console.log(typeof null); // object
```

### Changing Data Type (Casting)

- Casting: Converting one data type to another data type. We use _parseInt()_, _parseFloat()_, _Number()_, _+ sign_, _str()_
  When we do arithmetic operations string numbers should be first converted to integer or float if not it returns an error.

#### String to Int

We can convert string number to a number. Any number inside a quote is a string number. An example of a string number: '10', '5', etc.
We can convert string to number using the following methods:

- parseInt()
- Number()
- Plus sign(+)

```js
let num = "10";
let numInt = parseInt(num);
console.log(numInt); // 10
```

```js
let num = "10";
let numInt = Number(num);

console.log(numInt); // 10
```

```js
let num = "10";
let numInt = +num;

console.log(numInt); // 10
```

#### String to Float

We can convert string float number to a float number. Any float number inside a quote is a string float number. An example of a string float number: '9.81', '3.14', '1.44', etc.
We can convert string float to number using the following methods:

- parseFloat()
- Number()
- Plus sign(+)

```js
let num = "9.81";
let numFloat = parseFloat(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = Number(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = +num;

console.log(numFloat); // 9.81
```

#### Float to Int

We can convert float numbers to integers.
We use the following method to convert float to int:

- parseInt()

```js
let num = 9.81;
let numInt = parseInt(num);

console.log(numInt); // 9
```

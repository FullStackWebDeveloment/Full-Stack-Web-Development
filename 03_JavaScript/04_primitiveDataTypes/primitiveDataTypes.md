<div align="center">
  <h1>JavaScript</h1>
</div>

[<< Data Types](../03_dataTypes/dataTypes.md)| [Primitive Data Types>>](../04_primitiveDataTypes/primitiveDataTypes.md)

# Primitive Data Types

- [Numbers](#numbers)
    - [Declaring Number Data Types](#declaring-number-data-types)
    - [Math Object](#math-object)
    - [Random Number Generator](#random-number-generator)
- [Strings](#strings)
    - [String Concatenation](#string-concatenation)
    - [Concatenating Using Addition Operator](#concatenating-using-addition-operator)
    - [Long Literal Strings](#long-literal-strings)
    - [Escape Sequences in Strings](#escape-sequences-in-strings)
    - [Template Literals (Template Strings)](#template-literals-template-strings)
    - [String Methods](#string-methods)
- [Booleans](#booleans)
    - [Truthy values](#truthy-values)
    - [Falsy values](#falsy-values)
- [Symbol](#symbol)
- [BigInt](#bigint)
- [Undefined](#undefined)
- [Null](#null)


## Numbers

Numbers are integers and decimal values which can do all the arithmetic operations.
Let's see some examples of Numbers.

### Declaring Number Data Types

```js
let age = 35;
const gravity = 9.81; // we use const for non-changing values, gravitational constant in  m/s2
let mass = 72; // mass in Kilogram
const PI = 3.14; // pi a geometrical constant

// More Examples
const boilingPoint = 100; // temperature in oC, boiling point of water which is a constant
const bodyTemp = 37; // oC average human body temperature, which is a constant

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp);
```

### Math Object

In JavaScript the Math Object provides a lots of methods to work with numbers.

```js
const PI = Math.PI;

console.log(PI); // 3.141592653589793

// Rounding to the closest number
// if above .5 up if less 0.5 down rounding

console.log(Math.round(PI)); // 3 to round values to the nearest number

console.log(Math.round(9.81)); // 10

console.log(Math.floor(PI)); // 3 rounding down

console.log(Math.ceil(PI)); // 4 rounding up

console.log(Math.min(-5, 3, 20, 4, 5, 10)); // -5, returns the minimum value

console.log(Math.max(-5, 3, 20, 4, 5, 10)); // 20, returns the maximum value

const randNum = Math.random(); // creates random number between 0 to 0.999999
console.log(randNum);

// Let us  create random number between 0 to 10

const num = Math.floor(Math.random() * 11); // creates random number between 0 and 10
console.log(num);

//Absolute value
console.log(Math.abs(-10)); // 10

//Square root
console.log(Math.sqrt(100)); // 10

console.log(Math.sqrt(2)); // 1.4142135623730951

// Power
console.log(Math.pow(3, 2)); // 9

console.log(Math.E); // 2.718

// Logarithm
// Returns the natural logarithm with base E of x, Math.log(x)
console.log(Math.log(2)); // 0.6931471805599453
console.log(Math.log(10)); // 2.302585092994046

// Returns the natural logarithm of 2 and 10 respectively
console.log(Math.LN2); // 0.6931471805599453
console.log(Math.LN10); // 2.302585092994046

// Trigonometry
Math.sin(0);
Math.sin(60);

Math.cos(0);
Math.cos(60);
```

#### Random Number Generator

The JavaScript Math Object has a random() method number generator which generates number from 0 to 0.999999999...

```js
let randomNum = Math.random(); // generates 0 to 0.999...
```

Now, let us see how we can use random() method to generate a random number between 0 and 10:

```js
let randomNum = Math.random(); // generates 0 to 0.999
let numBtnZeroAndTen = randomNum * 11;

console.log(numBtnZeroAndTen); // this gives: min 0 and max 10.99

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen);
console.log(randomNumRoundToFloor); // this gives between 0 and 10
```

## Strings

Strings are texts, which are under **_single_** , **_double_**, **_back-tick_** quote. To declare a string, we need a variable name, assignment operator, a value under a single quote, double quote, or backtick quote.
Let's see some examples of strings:

```js
let space = " "; // an empty space string
let firstName = "Sathish";
let lastName = "Sampath";
let country = "India";
let city = "Chennai";
let language = "JavaScript";
let job = "teacher";
let quote = "The saying,'Seeing is Believing' is not correct in 2020.";
let quotWithBackTick = `The saying,'Seeing is Believing' is not correct in 2020.`;
```

### String Concatenation

Connecting two or more strings together is called concatenation.
Using the strings declared in the previous String section:

```js
let fullName = firstName + space + lastName; // concatenation, merging two string together.
console.log(fullName);
```

```sh
Sathish Sampath
```

We can concatenate strings in different ways.

#### Concatenating Using Addition Operator

Concatenating using the addition operator is an old way. This way of concatenating is tedious and error-prone. It is good to know how to concatenate this way, but I strongly suggest to use the ES6 template strings (explained later on).

```js
// Declaring different variables of different data types
let space = " ";
let firstName = "Sathish";
let lastName = "Sampath";
let country = "India";
let city = "Chennai";
let language = "JavaScript";
let job = "teacher";
let age = 250;

let fullName = firstName + space + lastName;
let personInfoOne = fullName + ". I am " + age + ". I live in " + country; // ES5 string addition

console.log(personInfoOne);
```

```sh
Sathish Sampath. I am 250. I live in India
```

#### Long Literal Strings

A string could be a single character or paragraph or a page. If the string length is too big it does not fit in one line. We can use the backslash character (\\) at the end of each line to indicate that the string will continue on the next line.
**Example:**

```js
const paragraph =
  "My name is Sathish Sampath. I live in India, Chennai.\
I am a teacher and I love teaching. I teach HTML, CSS, JavaScript, React, Redux, \
Node.js, Python, Data Analysis and D3.js for anyone who is interested to learn. \
In the end of 2019, I was thinking to expand my teaching and to reach \
to global audience and I started a Python challenge from November 20 - December 19.\
It was one of the most rewarding and inspiring experience.\
Now, we are in 2020. I am enjoying preparing the 30DaysOfJavaScript challenge and \
I hope you are enjoying too.";

console.log(paragraph);
```

#### Escape Sequences in Strings

In JavaScript and other programming languages \ followed by some characters is an escape sequence. Let's see the most common escape characters:

- \n: new line
- \t: Tab, means 8 spaces
- \\\\: Back slash
- \\': Single quote (')
- \\": Double quote (")

```js
console.log(
  "I hope everyone is enjoying the 30 Days Of JavaScript challenge.\nDo you ?"
); // line break
console.log("Days\tTopics\tExercises");
console.log("Day 1\t3\t5");
console.log("Day 2\t3\t5");
console.log("Day 3\t3\t5");
console.log("Day 4\t3\t5");
console.log("This is a backslash  symbol (\\)"); // To write a backslash
console.log('In every programming language it starts with "Hello, World!"');
console.log("In every programming language it starts with 'Hello, World!'");
console.log("The saying 'Seeing is Believing' isn't correct in 2020");
```

Output in console:

```sh
I hope everyone is enjoying the 30 Days Of JavaScript challenge.
Do you ?
Days  Topics  Exercises
Day 1 3 5
Day 2 3 5
Day 3 3 5
Day 4 3 5
This is a backslash  symbol (\)
In every programming language it starts with "Hello, World!"
In every programming language it starts with 'Hello, World!'
The saying 'Seeing is Believing' isn't correct in 2020
```

#### Template Literals (Template Strings)

To create a template strings, we use two back-ticks. We can inject data as expressions inside a template string. To inject data, we enclose the expression with a curly bracket({}) preceded by a $ sign. See the syntax below.

```js
//Syntax
`String literal text``String literal text ${expression}`;
```

**Example: 1**

```js
console.log(`The sum of 2 and 3 is 5`); // statically writing the data
let a = 2;
let b = 3;
console.log(`The sum of ${a} and ${b} is ${a + b}`); // injecting the data dynamically
```

**Example:2**

```js
let firstName = "Sathish";
let lastName = "Sampath";
let country = "India";
let city = "Chennai";
let language = "JavaScript";
let job = "teacher";
let age = 250;
let fullName = firstName + " " + lastName;

let personInfoTwo = `I am ${fullName}. I am ${age}. I live in ${country}.`; //ES6 - String interpolation method
let personInfoThree = `I am ${fullName}. I live in ${city}, ${country}. I am a ${job}. I teach ${language}.`;
console.log(personInfoTwo);
console.log(personInfoThree);
```

```sh
I am Sathish Sampath. I am 250. I live in India.
I am Sathish Sampath. I live in Chennai, India. I am a teacher. I teach JavaScript.
```

Using a string template or string interpolation method, we can add expressions, which could be a value, or some operations (comparison, arithmetic operations, ternary operation).

```js
let a = 2;
let b = 3;
console.log(`${a} is greater than ${b}: ${a > b}`);
```

```sh
2 is greater than 3: false
```

### String Methods

Everything in JavaScript is an object. A string is a primitive data type that means we can not modify it once it is created. The string object has many string methods. There are different string methods that can help us to work with strings.

1. _length_: The string _length_ method returns the number of characters in a string included empty space.

**Example:**

```js
let js = "JavaScript";
console.log(js.length); // 10
let firstName = "Sathish";
console.log(firstName.length); // 8
```

2. _Accessing characters in a string_: We can access each character in a string using its index. In programming, counting starts from 0. The first index of the string is zero, and the last index is the length of the string minus one.

![Accessing sting by index](../images/string_indexes.png)

Let us access different characters in 'JavaScript' string.

```js
let string = "JavaScript";
let firstLetter = string[0];

console.log(firstLetter); // J

let secondLetter = string[1]; // a
let thirdLetter = string[2];
let lastLetter = string[9];

console.log(lastLetter); // t

let lastIndex = string.length - 1;

console.log(lastIndex); // 9
console.log(string[lastIndex]); // t
```

3. _toUpperCase()_: this method changes the string to uppercase letters.

```js
let string = "JavaScript";

console.log(string.toUpperCase()); // JAVASCRIPT

let firstName = "Sathish";

console.log(firstName.toUpperCase()); // SATHISH

let country = "India";

console.log(country.toUpperCase()); // INDIA
```

4. _toLowerCase()_: this method changes the string to lowercase letters.

```js
let string = "JavasCript";

console.log(string.toLowerCase()); // javascript

let firstName = "Sathish";

console.log(firstName.toLowerCase()); // sathish

let country = "India";

console.log(country.toLowerCase()); // india
```

5. _substr()_: It takes two arguments, the starting index and number of characters to slice.

```js
let string = "JavaScript";
console.log(string.substr(4, 6)); // Script

let country = "India";
console.log(country.substr(3, 4)); // ia
```

6. _substring()_: It takes two arguments, the starting index and the stopping index but it doesn't include the character at the stopping index.

```js
let string = "JavaScript";

console.log(string.substring(0, 4)); // Java
console.log(string.substring(4, 10)); // Script
console.log(string.substring(4)); // Script
```

7. _split()_: The split method splits a string at a specified place.

```js
let string = "FullStack Web Development";

console.log(string.split()); // Changes to an array -> ["FullStack Web Development"]
console.log(string.split(" ")); // Split to an array at space -> ["FullStack", "Web","Development"]

let firstName = "Sathish";

console.log(firstName.split()); // Change to an array - > ["Sathish"]
console.log(firstName.split("")); // Split to an array at each letter ->   ['S', 'a', 't',  'h', 'i', 's','h',"h"]

let countries = "India, Sweden, Norway, Denmark, and Iceland";

console.log(countries.split(",")); // split to any array at comma -> ["India", " Sweden", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(", ")); //  ["India", "Sweden", "Norway", "Denmark", "and Iceland"]
```

8. _trim()_: Removes trailing space in the beginning or the end of a string.

```js
let string = "   FullStack Web Development   ";

console.log(string);
console.log(string.trim(" "));

let firstName = " Sathish ";

console.log(firstName);
console.log(firstName.trim()); // still removes spaces at the beginning and the end of the string
```

```sh
   FullStack Web Development
FullStack Web Development
  Sathish
Sathish
```

9. _includes()_: It takes a substring argument and it checks if substring argument exists in the string. _includes()_ returns a boolean. If a substring exist in a string, it returns true, otherwise it returns false.

```js
let string = "FullStack Web Development";

console.log(string.includes("Web")); // true
console.log(string.includes("web")); // false - it is case sensitive!
console.log(string.includes("Development")); // true
console.log(string.includes("development")); // false

let country = "India";

console.log(country.includes("in")); // false
console.log(country.includes("In")); // true
console.log(country.includes("dia")); // true
console.log(country.includes("Dia")); // false
```

10. _replace()_: takes as a parameter the old substring and a new substring.

```js
string.replace(oldsubstring, newsubstring);
```

```js
let string = "Sathish Sampath";
console.log(string.replace("Sathish", "Sampath")); // Sathish Sampath

let country = "Finland";
console.log(country.replace("Fin", "Noman")); // Nomanland
```

11. _charAt()_: Takes index and it returns the value at that index

```js
string.charAt(index);
```

```js
let string = "FullStack Web Development";
console.log(string.charAt(0)); // F

let lastIndex = string.length - 1;
console.log(string.charAt(lastIndex)); // t
```

12. _charCodeAt()_: Takes index and it returns char code (ASCII number) of the value at that index

```js
string.charCodeAt(index);
```

```js
let string = "FullStack Web Development";
console.log(string.charCodeAt(3)); // l ASCII number is 68

let lastIndex = string.length - 1;
console.log(string.charCodeAt(lastIndex)); // t ASCII is 116
```

13. _indexOf()_: Takes a substring and if the substring exists in a string it returns the first position of the substring if does not exist it returns -1

```js
string.indexOf(substring);
```

```js
let string = "FullStack Web Development";

console.log(string.indexOf("l")); // 2
console.log(string.indexOf("Web")); // 10
console.log(string.indexOf("development")); // -1
```

14. _lastIndexOf()_: Takes a substring and if the substring exists in a string it returns the last position of the substring if it does not exist it returns -1

```js
//syntax
string.lastIndexOf(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";

console.log(string.lastIndexOf("love")); // 67
console.log(string.lastIndexOf("you")); // 63
console.log(string.lastIndexOf("JavaScript")); // 38
```

15. _concat()_: it takes many substrings and joins them.

```js
string.concat(substring, substring, substring);
```

```js
let string = "30";
console.log(string.concat("FullStack", "Web", "Development")); // FullStackWebDevelopment

let country = "In";
console.log(country.concat("dia")); // India
```

16. _startsWith_: it takes a substring as an argument and it checks if the string starts with that specified substring. It returns a boolean(true or false).

```js
//syntax
string.startsWith(substring);
```

```js
let string = "Love is the best to in this world";

console.log(string.startsWith("Love")); // true
console.log(string.startsWith("love")); // false
console.log(string.startsWith("world")); // false

let country = "India";

console.log(country.startsWith("In")); // true
console.log(country.startsWith("in")); // false
console.log(country.startsWith("dia")); //  false
```

17. _endsWith_: it takes a substring as an argument and it checks if the string ends with that specified substring. It returns a boolean(true or false).

```js
string.endsWith(substring);
```

```js
let string = "Love is the most powerful feeling in the world";

console.log(string.endsWith("world")); // true
console.log(string.endsWith("love")); // false
console.log(string.endsWith("in the world")); // true

let country = "India";

console.log(country.endsWith("land")); // true
console.log(country.endsWith("fin")); // false
console.log(country.endsWith("Fin")); //  false
```

18. _search_: it takes a substring as an argument and it returns the index of the first match. The search value can be a string or a regular expression pattern.

```js
string.search(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";
console.log(string.search("love")); // 2
console.log(string.search(/javascript/gi)); // 7
```

19. _match_: it takes a substring or regular expression pattern as an argument and it returns an array if there is match if not it returns null. Let us see how a regular expression pattern looks like. It starts with / sign and ends with / sign.

```js
let string = "love";
let patternOne = /love/; // with out any flag
let patternTwo = /love/gi; // g-means to search in the whole text, i - case insensitive
```

Match syntax

```js
// syntax
string.match(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";
console.log(string.match("love"));
```

```sh
["love", index: 2, input: "I love JavaScript. If you do not love JavaScript what else can you love.", groups: undefined]
```

```js
let pattern = /love/gi;
console.log(string.match(pattern)); // ["love", "love", "love"]
```

Let us extract numbers from text using a regular expression. This is not the regular expression section, do not panic! We will cover regular expressions later on.

```js
let txt =
  "In 2022, I was learned Full Stack Development. Now, in 2023 I am super exited to start more challenges like this challenge";
let regEx = /\d+/;

// d with escape character means d not a normal d instead acts a digit
// + means one or more digit numbers,
// if there is g after that it means global, search everywhere.

console.log(txt.match(regEx)); // ["2", "0", "2", "2","2", "0", "2", "3"]
console.log(txt.match(/\d+/g)); // ["2022", "2023"]
```

20. _repeat()_: it takes a number as argument and it returns the repeated version of the string.

```js
string.repeat(n);
```

```js
let string = "love";
console.log(string.repeat(10)); // lovelovelovelovelovelovelovelovelovelove
```

## Booleans

A boolean data type represents one of the two values:_true_ or _false_. Boolean value is either true or false. The use of these data types will be clear when you start the comparison operator. Any comparisons return a boolean value which is either true or false.

**Example: Boolean Values**

```js
let isLightOn = true;
let isRaining = false;
let isHungry = false;
let isMarried = true;
let truValue = 4 > 3; // true
let falseValue = 4 < 3; // false
```

We agreed that boolean values are either true or false.

### Truthy values

- All numbers(positive and negative) are truthy except zero
- All strings are truthy except an empty string ('')
- The boolean true

### Falsy values

- 0
- 0n
- null
- undefined
- NaN
- the boolean false
- '', "", ``, empty string

It is good to remember those truthy values and falsy values. In later section, we will use them with conditions to make decisions.

## Symbol

A Symbol is a unique and immutable primitive value and may be used as the key of an Object property (see below). In some programming languages, Symbols are called "atoms". The purpose of symbols is to create unique property keys that are guaranteed not to clash with keys from other code.

To create a new primitive Symbol, you write Symbol() with an optional string as its description:

```js
// Creating a new symbol with the description "mySymbol"
const mySymbol = Symbol("mySymbol");

// Using the symbol as an object key
const myObj = {
  [mySymbol]: "This is the value for mySymbol key"
};

console.log(myObj[mySymbol]); // Output: "This is the value for mySymbol key"

```
In this example, we create a new symbol named mySymbol and use it as a key in the myObj object. We can access the value associated with the mySymbol key using bracket notation ```myObj[mySymbol]```. Since symbols are unique, we can be sure that no other property in myObj accidentally shares the same key.

## BigInt

The BigInt type is a numeric primitive in JavaScript that can represent integers with arbitrary magnitude. With BigInts, you can safely store and operate on large integers even beyond the safe integer limit (Number.MAX_SAFE_INTEGER) for Numbers.

A BigInt is created by appending n to the end of an integer or by calling the BigInt() function.

```js

console.log(`Range  ${Number.MIN_SAFE_INTEGER} to ${Number.MAX_SAFE_INTEGER}`)//

// BigInt
const x = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
x + 1n === x + 2n; // false because 9007199254740992n and 9007199254740993n are unequal

// Number
Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2; // true because both are 9007199254740992

```
You can use most operators to work with BigInts, including ```+, *, -, **,``` and```` % — ``` the only forbidden one is ```>>>```. A BigInt is not strictly equal to a Number with the same mathematical value, but it is loosely so.

## Undefined

If we declare a variable and if we do not assign a value, the value will be undefined. In addition to this, if a function is not returning the value, it will be undefined.

```js
let firstName;
console.log(firstName); //not defined, because it is not assigned to a value yet
```

## Null

```js
let empty = null;
console.log(empty); // -> null , means no value
```

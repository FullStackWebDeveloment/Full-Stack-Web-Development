<div align="center">
  <h1>JavaScript</h1>
</div>

[<<Primitive Data Types](../04_primitiveDataTypes/primitiveDataTypes.md)| [Operators>>](../06_operators/operators.md)

# Non-Primitive Data Types

- [📔 Object](#-object)
  - [Creating an empty object](#creating-an-empty-object)
  - [Creating an objecting with values](#creating-an-objecting-with-values)
  - [Getting values from an object](#getting-values-from-an-object)
  - [Creating object methods](#creating-object-methods)
  - [Setting new key for an object](#setting-new-key-for-an-object)
  - [Object Methods](#object-methods)
    - [Getting object keys using Object.keys()](#getting-object-keys-using-objectkeys)
    - [Getting object values using Object.values()](#getting-object-values-using-objectvalues)
    - [Getting object keys and values using Object.entries()](#getting-object-keys-and-values-using-objectentries)
    - [Checking properties using hasOwnProperty()](#checking-properties-using-hasownproperty)
- [Arrays](#arrays)
  - [How to create an empty array](#how-to-create-an-empty-array)
  - [How to create an array with values](#how-to-create-an-array-with-values)
  - [Creating an array using split](#creating-an-array-using-split)
  - [Accessing array items using index](#accessing-array-items-using-index)
  - [Modifying array element](#modifying-array-element)
  - [Methods to manipulate array](#methods-to-manipulate-array)
    - [Array Constructor](#array-constructor)
    - [Creating static values with fill](#creating-static-values-with-fill)
    - [Concatenating array using concat](#concatenating-array-using-concat)
    - [Getting array length](#getting-array-length)
    - [Getting index an element in arr array](#getting-index-an-element-in-arr-array)
    - [Getting last index of an element in array](#getting-last-index-of-an-element-in-array)
    - [Checking array](#checking-array)
    - [Converting array to string](#converting-array-to-string)
    - [Joining array elements](#joining-array-elements)
    - [Slice array elements](#slice-array-elements)
    - [Splice method in array](#splice-method-in-array)
    - [Adding item to an array using push](#adding-item-to-an-array-using-push)
    - [Removing the end element using pop](#removing-the-end-element-using-pop)
    - [Removing an element from the beginning](#removing-an-element-from-the-beginning)
    - [Add an element from the beginning](#add-an-element-from-the-beginning)
    - [Reversing array order](#reversing-array-order)
    - [Sorting elements in array](#sorting-elements-in-array)
  - [Array of arrays](#array-of-arrays)

# Object

Everything can be an object and objects do have properties and properties have values, so an object is a key value pair. The order of the key is not reserved, or there is no order.
To create an object literal, we use two curly brackets.

### Creating an empty object

An empty object

```js
const person = {};
```

### Creating an objecting with values

Now, the person object has firstName, lastName, age, location, skills and isMarried properties. The value of properties or keys could be a string, number, boolean, an object, null, undefined or a function.

Let us see some examples of object. Each key has a value in the object.

```js
const rectangle = {
  length: 20,
  width: 20,
};
console.log(rectangle); // {length: 20, width: 20}

const person = {
  firstName: "Sathish",
  lastName: "Sampath",
  age: 25,
  country: "India",
  city: "Chennai",
  skills: ["HTML", "CSS", "JavaScript", "React", "Node", "MongoDB", "Python"],
  isMarried: false,
};
console.log(person);
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Getting values from an object

We can access values of object using two methods:

- using . followed by key name if the key-name is a one word
- using square bracket and a quote

```js
const person = {
  firstName: 'Sathish',
  lastName: 'Sampath',
  age: 25,
  country: 'India',
  city: 'Chennai',
  skills: [
    'HTML',
    'CSS',
    'JavaScript',
    'React',
    'Node',
    'MongoDB',
    'Python',
  ],
  isMarried: false
  getFullName: function() {
    return `${this.firstName}${this.lastName}`
  },
  'phone number': '+3584545454545'
}

// accessing values using .
console.log(person.firstName)
console.log(person.lastName)
console.log(person.age)
console.log(person.location) // undefined

// value can be accessed using square bracket and key name
console.log(person['firstName'])
console.log(person['lastName'])
console.log(person['age'])
console.log(person['age'])
console.log(person['location']) // undefined

// for instance to access the phone number we only use the square bracket method
console.log(person['phone number'])
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Creating object methods

Now, the person object has getFullName properties. The getFullName is function inside the person object and we call it an object method. The _this_ key word refers to the object itself. We can use the word _this_ to access the values of different properties of the object. We can not use an arrow function as object method because the word this refers to the window inside an arrow function instead of the object itself. Example of object:

```js
const person = {
  firstName: "Sathish",
  lastName: "Sampath",
  age: 25,
  country: "India",
  city: "Chennai",
  skills: ["HTML", "CSS", "JavaScript", "React", "Node", "MongoDB", "Python"],
  isMarried: false,
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(person.getFullName());
// Asabeneh Yetayeh
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Setting new key for an object

An object is a mutable data structure and we can modify the content of an object after it gets created.

Setting a new keys in an object

```js
const person = {
  firstName: "Sathish",
  lastName: "Sampath",
  age: 25,
  country: "India",
  city: "Chennai",
  skills: ["HTML", "CSS", "JavaScript", "React", "Node", "MongoDB", "Python"],
  isMarried: false,
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};
person.nationality = "Indian";
person.country = "India";
person.title = "Developer";
person.skills.push("Django");
person.skills.push("SasS");
person.isMarried = true;

person.getPersonInfo = function () {
  let skillsWithoutLastSkill = this.skills
    .splice(0, this.skills.length - 1)
    .join(", ");
  let lastSkill = this.skills.splice(this.skills.length - 1)[0];

  let skills = `${skillsWithoutLastSkill}, and ${lastSkill}`;
  let fullName = this.getFullName();
  let statement = `${fullName} is a ${this.title}.\nHe lives in ${this.country}.\nHe teaches ${skills}.`;
  return statement;
};
console.log(person);
console.log(person.getPersonInfo());
```

```sh
Sathish Sampath is a Developer.
He lives in India.
He knows HTML, CSS, JavaScript, React, Node, MongoDB, Python, Django, and SasS.
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Object Methods

There are different methods to manipulate an object. Let us see some of the available methods.

_Object.assign_: To copy an object without modifying the original object

```js
const person = {
  firstName: "Sathish",
  age: 25,
  country: "India",
  city: "Chennai",
  skills: ["HTML", "CSS", "JS"],
  title: "Developer",
  address: {
    street: "East street",
    pin: 600028,
    state: "Tamilnadu",
  },
  getPersonInfo: function () {
    return `I am ${this.firstName} and I live in ${this.city}, ${this.country}. I am ${this.age}.`;
  },
};

//Object methods: Object.assign, Object.keys, Object.values, Object.entries
//hasOwnProperty

const copyPerson = Object.assign({}, person);
console.log(copyPerson);
```

#### Getting object keys using Object.keys()

_Object.keys_: To get the keys or properties of an object as an array

```js
const keys = Object.keys(copyPerson);
console.log(keys); //['firstName', 'age', 'country','city', 'skills','title', 'address', 'getPersonInfo']
const address = Object.keys(copyPerson.address);
console.log(address); //['street', 'pin', 'state']
```

#### Getting object values using Object.values()

_Object.values_:To get values of an object as an array

```js
const values = Object.values(copyPerson);
console.log(values);
```

#### Getting object keys and values using Object.entries()

_Object.entries_:To get the keys and values in an array

```js
const entries = Object.entries(copyPerson);
console.log(entries);
```

#### Checking properties using hasOwnProperty()

_hasOwnProperty_: To check if a specific key or property exist in an object

```js
console.log(copyPerson.hasOwnProperty("name")); // it's returns false
console.log(copyPerson.hasOwnProperty("skiills")); //it's returns true because it had key as skills
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

# Arrays

In contrast to variables, an array can store _multiple values_. Each value in an array has an _index_, and each index has _a reference in a memory address_. Each value can be accessed by using their _indexes_. The index of an array starts from _zero_, and the index of the last element is less by one from the length of the array.

An array is a collection of different data types which are ordered and changeable(modifiable). An array allows storing duplicate elements and different data types. An array can be empty, or it may have different data type values.

### How to create an empty array

In JavaScript, we can create an array in different ways. Let us see different ways to create an array.
It is very common to use _const_ instead of _let_ to declare an array variable. If you ar using const it means you do not use that variable name again.

- Using Array constructor

```js
// syntax
const arr = Array();
// or
// let arr = new Array()
console.log(arr); // []
```

- Using square brackets([])

```js
// syntax
// This the most recommended way to create an empty list
const arr = [];
console.log(arr);
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### How to create an array with values

Array with initial values. We use _length_ property to find the length of an array.

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]; // array of numbers
const fruits = ["banana", "orange", "mango", "lemon"]; // array of strings, fruits
const vegetables = ["Tomato", "Potato", "Cabbage", "Onion", "Carrot"]; // array of strings, vegetables
const animalProducts = ["milk", "meat", "butter", "yoghurt"]; // array of strings, products
const webTechs = ["HTML", "CSS", "JS", "React", "Redux", "Node", "MongDB"]; // array of web technologies
const countries = ["Finland", "Denmark", "Sweden", "Norway", "Iceland"]; // array of strings, countries

// Print the array and its length

console.log("Numbers:", numbers);
console.log("Number of numbers:", numbers.length);

console.log("Fruits:", fruits);
console.log("Number of fruits:", fruits.length);

console.log("Vegetables:", vegetables);
console.log("Number of vegetables:", vegetables.length);

console.log("Animal products:", animalProducts);
console.log("Number of animal products:", animalProducts.length);

console.log("Web technologies:", webTechs);
console.log("Number of web technologies:", webTechs.length);

console.log("Countries:", countries);
console.log("Number of countries:", countries.length);
```

```sh
Numbers: [0, 3.14, 9.81, 37, 98.6, 100]
Number of numbers: 6
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Array can have items of different data types

```js
const arr = [
  "Sathish",
  250,
  true,
  { country: "India", city: "Chennai" },
  { skills: ["HTML", "CSS", "JS", "React", "Python"] },
]; // arr containing different data types
console.log(arr);
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Creating an array using split

As we have seen in the earlier section, we can split a string at different positions, and we can change to an array. Let us see the examples below.

```js
let js = "JavaScript";
const charsInJavaScript = js.split("");

console.log(charsInJavaScript); // ["J", "a", "v", "a", "S", "c", "r", "i", "p", "t"]

let companiesString = "Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon";
const companies = companiesString.split(",");

console.log(companies); // ["Facebook", " Google", " Microsoft", " Apple", " IBM", " Oracle", " Amazon"]
let txt =
  "I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.";
const words = txt.split(" ");

console.log(words);
// the text has special characters think how you can just get only the words
// ["I", "love", "teaching", "and", "empowering", "people.", "I", "teach", "HTML,", "CSS,", "JS,", "React,", "Python"]
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Accessing array items using index

We access each element in an array using their index. An array index starts from 0. The picture below clearly shows the index of each element in the array.

![arr index](../images/array_index.png)

```js
const fruits = ["banana", "orange", "mango", "lemon"];
let firstFruit = fruits[0]; // we are accessing the first item using its index

console.log(firstFruit); // banana

secondFruit = fruits[1];
console.log(secondFruit); // orange

let lastFruit = fruits[3];
console.log(lastFruit); // lemon
// Last index can be calculated as follows

let lastIndex = fruits.length - 1;
lastFruit = fruits[lastIndex];

console.log(lastFruit); // lemon
```

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]; // set of numbers

console.log(numbers.length); // => to know the size of the array, which is 6
console.log(numbers); // -> [0, 3.14, 9.81, 37, 98.6, 100]
console.log(numbers[0]); //  -> 0
console.log(numbers[5]); //  -> 100

let lastIndex = numbers.length - 1;
console.log(numbers[lastIndex]); // -> 100
```

```js
const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs); // all the array items
console.log(webTechs.length); // => to know the size of the array, which is 7
console.log(webTechs[0]); //  -> HTML
console.log(webTechs[6]); //  -> MongoDB

let lastIndex = webTechs.length - 1;
console.log(webTechs[lastIndex]); // -> MongoDB
```

```js
const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "India",
  "Japan",
  "Kenya",
]; // List of countries

console.log(countries); // -> all countries in array
console.log(countries[0]); //  -> Albania
console.log(countries[10]); //  -> Kenya

let lastIndex = countries.length - 1;
console.log(countries[lastIndex]); //  -> Kenya
```

```js
const shoppingCart = [
  "Milk",
  "Mango",
  "Tomato",
  "Potato",
  "Avocado",
  "Meat",
  "Eggs",
  "Sugar",
]; // List of food products

console.log(shoppingCart); // -> all shoppingCart in array
console.log(shoppingCart[0]); //  -> Milk
console.log(shoppingCart[7]); //  -> Sugar

let lastIndex = shoppingCart.length - 1;
console.log(shoppingCart[lastIndex]); //  -> Sugar
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Modifying array element

An array is mutable(modifiable). Once an array is created, we can modify the contents of the array elements.

```js
const numbers = [1, 2, 3, 4, 5];
numbers[0] = 10; // changing 1 at index 0 to 10
numbers[1] = 20; // changing  2 at index 1 to 20

console.log(numbers); // [10, 20, 3, 4, 5]

const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "India",
  "Japan",
  "Kenya",
];

countries[0] = "Afghanistan"; // Replacing Albania by Afghanistan
let lastIndex = countries.length - 1;
countries[lastIndex] = "Korea"; // Replacing Kenya by Korea

console.log(countries);
```

```sh
["Afghanistan", "Bolivia", "Canada", "Denmark", "Ethiopia", "Finland", "Germany", "Hungary", "India", "Japan", "Korea"]
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

### Methods to manipulate array

There are different methods to manipulate an array. These are some of the available methods to deal with arrays:_Array, length, concat, indexOf, slice, splice, join, toString, includes, lastIndexOf, isArray, fill, push, pop, shift, unshift_

#### Array Constructor

Array:To create an array.

```js
const arr = Array(); // creates an an empty array
console.log(arr);

const eightEmptyValues = Array(8); // it creates eight empty values
console.log(eightEmptyValues); // [empty x 8]
```

#### Creating static values with fill

fill: Fill all the array elements with a static value

```js
const arr = Array(); // creates an an empty array
console.log(arr);

const eightXvalues = Array(8).fill("X"); // it creates eight element values filled with 'X'
console.log(eightXvalues); // ['X', 'X','X','X','X','X','X','X']

const eight0values = Array(8).fill(0); // it creates eight element values filled with '0'
console.log(eight0values); // [0, 0, 0, 0, 0, 0, 0, 0]

const four4values = Array(4).fill(4); // it creates 4 element values filled with '4'
console.log(four4values); // [4, 4, 4, 4]
```

#### Concatenating array using concat

concat:To concatenate two arrays.

```js
const firstList = [1, 2, 3];
const secondList = [4, 5, 6];
const thirdList = firstList.concat(secondList);

console.log(thirdList); // [1, 2, 3, 4, 5, 6]
```

```js
const fruits = ["banana", "orange", "mango", "lemon"]; // array of fruits
const vegetables = ["Tomato", "Potato", "Cabbage", "Onion", "Carrot"]; // array of vegetables
const fruitsAndVegetables = fruits.concat(vegetables); // concatenate the two arrays

console.log(fruitsAndVegetables);
```

```sh
["banana", "orange", "mango", "lemon", "Tomato", "Potato", "Cabbage", "Onion", "Carrot"]
```

#### Getting array length

Length:To know the size of the array

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.length); // -> 5 is the size of the array
```

#### Getting index an element in arr array

indexOf:To check if an item exist in an array. If it exists it returns the index else it returns -1.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.indexOf(5)); // -> 4
console.log(numbers.indexOf(0)); // -> -1
console.log(numbers.indexOf(1)); // -> 0
console.log(numbers.indexOf(6)); // -> -1
```

Check an element if it exist in an array.

- Check items in a list

```js
// let us check if a banana exist in the array

const fruits = ["banana", "orange", "mango", "lemon"];
let index = fruits.indexOf("banana"); // 0

if (index === -1) {
  console.log("This fruit does not exist in the array");
} else {
  console.log("This fruit does exist in the array");
}
// This fruit does exist in the array

// we can use also ternary here
index === -1
  ? console.log("This fruit does not exist in the array")
  : console.log("This fruit does exist in the array");

// let us check if an avocado exist in the array
let indexOfAvocado = fruits.indexOf("avocado"); // -1, if the element not found index is -1
if (indexOfAvocado === -1) {
  console.log("This fruit does not exist in the array");
} else {
  console.log("This fruit does exist in the array");
}
// This fruit does not exist in the array
```

#### Getting last index of an element in array

lastIndexOf: It gives the position of the last item in the array. If it exist, it returns the index else it returns -1.

```js
const numbers = [1, 2, 3, 4, 5, 3, 1, 2];

console.log(numbers.lastIndexOf(2)); // 7
console.log(numbers.lastIndexOf(0)); // -1
console.log(numbers.lastIndexOf(1)); //  6
console.log(numbers.lastIndexOf(4)); //  3
console.log(numbers.lastIndexOf(6)); // -1
```

includes:To check if an item exist in an array. If it exist it returns the true else it returns false.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.includes(5)); // true
console.log(numbers.includes(0)); // false
console.log(numbers.includes(1)); // true
console.log(numbers.includes(6)); // false

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs.includes("Node")); // true
console.log(webTechs.includes("C")); // false
```

#### Checking array

Array.isArray:To check if the data type is an array

```js
const numbers = [1, 2, 3, 4, 5];
console.log(Array.isArray(numbers)); // true

const number = 100;
console.log(Array.isArray(number)); // false
```

#### Converting array to string

toString:Converts array to string

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.toString()); // 1,2,3,4,5

const names = ["Sathish", "Guha", "Sasikumar", "Bharathi"];
console.log(names.toString()); // Sathish,Guha,Sasikumar,Bharathi
```

#### Joining array elements

join: It is used to join the elements of the array, the argument we passed in the join method will be joined in the array and return as a string. By default, it joins with a comma, but we can pass different string parameter which can be joined between the items.

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.join()); // 1,2,3,4,5

const names = ["Sathish", "Guha", "Sasikumar", "Bharathi"];

console.log(names.join()); // Sathish,Guha,Sasikumar,Bharathi
console.log(names.join("")); //SathishGuhaSasikumarBharathi
console.log(names.join(" ")); //Sathish Guha Sasikumar Bharathi
console.log(names.join(", ")); //Sathish, Guha, Sasikumar, Bharathi
console.log(names.join(" # ")); //Sathish # Guha # Sasikumar # Bharathi

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs.join()); // "HTML,CSS,JavaScript,React,Redux,Node,MongoDB"
console.log(webTechs.join(" # ")); // "HTML # CSS # JavaScript # React # Redux # Node # MongoDB"
```

#### Slice array elements

Slice: To cut out a multiple items in range. It takes two parameters:starting and ending position. It doesn't include the ending position.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.slice()); // -> it copies all  item
console.log(numbers.slice(0)); // -> it copies all  item
console.log(numbers.slice(0, numbers.length)); // it copies all  item
console.log(numbers.slice(1, 4)); // -> [2,3,4] // it doesn't include the ending position
```

#### Splice method in array

Splice: It takes three parameters:Starting position, number of times to be removed and number of items to be added.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.splice();
console.log(numbers); // -> remove all items
```

```js
const numbers = [1, 2, 3, 4, 5];
numbers.splice(0, 1);
console.log(numbers); // remove the first item
```

```js
const numbers = [1, 2, 3, 4, 5, 6];
numbers.splice(3, 3, 7, 8, 9);
console.log(numbers.splice(3, 3, 7, 8, 9)); // -> [1, 2, 3, 7, 8, 9] //it removes three item and replace three items
```

#### Adding item to an array using push

Push: adding item in the end. To add item to the end of an existing array we use the push method.

```js
// syntax
const arr = ["item1", "item2", "item3"];
arr.push("new item");
console.log(arr);
// ['item1', 'item2','item3','new item']
```

```js
const numbers = [1, 2, 3, 4, 5];
numbers.push(6);
console.log(numbers); // -> [1,2,3,4,5,6]

numbers.pop(); // -> remove one item from the end
console.log(numbers); // -> [1,2,3,4,5]
```

```js
let fruits = ["banana", "orange", "mango", "lemon"];
fruits.push("apple");
console.log(fruits); // ['banana', 'orange', 'mango', 'lemon', 'apple']

fruits.push("lime");
console.log(fruits); // ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
```

#### Removing the end element using pop

pop: Removing item in the end.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.pop(); // -> remove one item from the end
console.log(numbers); // -> [1,2,3,4]
```

#### Removing an element from the beginning

shift: Removing one array element in the beginning of the array.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.shift(); // -> remove one item from the beginning
console.log(numbers); // -> [2,3,4,5]
```

#### Add an element from the beginning

unshift: Adding array element in the beginning of the array.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.unshift(0); // -> add one item from the beginning
console.log(numbers); // -> [0,1,2,3,4,5]
```

#### Reversing array order

reverse: reverse the order of an array.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.reverse(); // -> reverse array order
console.log(numbers); // [5, 4, 3, 2, 1]

numbers.reverse();
console.log(numbers); // [1, 2, 3, 4, 5]
```

#### Sorting elements in array

sort: arrange array elements in ascending order. Sort takes a call back function, we will see how we use sort with a call back function in the coming sections.

```js
const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

webTechs.sort();
console.log(webTechs); // ["CSS", "HTML", "JavaScript", "MongoDB", "Node", "React", "Redux"]

webTechs.reverse(); // after sorting we can reverse it
console.log(webTechs); // ["Redux", "React", "Node", "MongoDB", "JavaScript", "HTML", "CSS"]
```

### Array of arrays

Array can store different data types including an array itself. Let us create an array of arrays

```js
const firstNums = [1, 2, 3];
const secondNums = [1, 4, 9];

const arrayOfArray = [
  [1, 2, 3],
  [1, 2, 3],
];
console.log(arrayOfArray[0]); // [1, 2, 3]

const frontEnd = ["HTML", "CSS", "JS", "React", "Redux"];
const backEnd = ["Node", "Express", "MongoDB"];
const fullStack = [frontEnd, backEnd];
console.log(fullStack); // [["HTML", "CSS", "JS", "React", "Redux"], ["Node", "Express", "MongoDB"]]
console.log(fullStack.length); // 2
console.log(fullStack[0]); // ["HTML", "CSS", "JS", "React", "Redux"]
console.log(fullStack[1]); // ["Node", "Express", "MongoDB"]
```

**[⬆ Back to Top](#Non-Primitive-Data-Types)**

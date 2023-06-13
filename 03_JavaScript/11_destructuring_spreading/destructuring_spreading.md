<div align="center">
  <h1>JavaScript</h1>
</div>

[<< Functions](../09_functions/functions.md) | [Destructuring Spreading >>](../11_destructuring_spreading/destructuring_spreading.md)

# Destructuring and Spread

- [Destructing Arrays](#destructing-arrays)
- [Destructuring during iteration](#destructuring-during-iteration)
- [Destructuring Object](#destructuring-object)
- [Renaming during structuring](#renaming-during-structuring)
- [Object parameter without destructuring](#object-parameter-without-destructuring)
- [Object parameter with destructuring](#object-parameter-with-destructuring)
- [Destructuring object during iteration](#destructuring-object-during-iteration)
- [Spread or Rest Operator](#spread-or-rest-operator)
- [Spread operator to get the rest of array elements](#spread-operator-to-get-the-rest-of-array-elements)
- [Spread operator to copy array](#spread-operator-to-copy-array)
- [Spread operator to copy object](#spread-operator-to-copy-object)
  - [Spread operator with arrow function](#spread-operator-with-arrow-function)

Destructuring is a way to unpack arrays, and objects and assigning to a distinct variable.

### Destructing Arrays

```js
const numbers = [1, 2, 3];
let [numOne, numTwo, numThree] = numbers;

console.log(numOne, numTwo, numThree);
```

```sh
  1 2 3
```

```js
const names = ["Sathish", "GuhaIyishvarya", "Sasikumar", "Kotti"];
let [firstPerson, secondPerson, thirdPerson, fourthPerson] = names;

console.log(firstPerson, secondPerson, thirdPerson, fourthPerson);
```

```sh
Sathish GuhaIyishvarya Sasikumar Kotti
```

```js
const scientificConstants = [2.72, 3.14, 9.81, 37, 100];
let [e, pi, gravity, bodyTemp, boilingTemp] = scientificConstants;

console.log(e, pi, gravity, bodyTemp, boilingTemp);
```

```sh
2.72 3.14 9.81 37 100
```

```js
const fullStack = [
  ["HTML", "CSS", "JS", "React"],
  ["Node", "Express", "MongoDB"],
];
const [frontEnd, backEnd] = fullStack;

console.log(frontEnd);
console.log(backEnd);
```

```sh
["HTML", "CSS", "JS", "React"]
["Node", "Express", "MongoDB"]
```

If we like to skip on of the values in the array we use additional comma. The comma helps to omit the value at that specific index

```js
const numbers = [1, 2, 3];
let [numOne, , numThree] = numbers; //2 is omitted

console.log(numOne, numThree);
```

```sh
1 3
```

```js
const names = ["Sathish", "GuhaIyishvarya", "Sasikumar", "Kotti"];
let [, secondPerson, , fourthPerson] = names; // first and third person is omitted

console.log(secondPerson, fourthPerson);
```

```sh
GuhaIyishvarya John
```

We can use default value in case the value of array for that index is undefined:

```js
const names = [undefined, "Brook", "David"];
let [
  firstPerson = "Sathish",
  secondPerson,
  thirdPerson,
  fourthPerson = "Kotti",
] = names;

console.log(firstPerson, secondPerson, thirdPerson, fourthPerson);
```

```sh
Sathish GuhaIyishvarya Sasikumar Kotti
```

We can not assign variable to all the elements in the array. We can destructure few of the first and we can get the remaining as array using spread operator(...).

```js
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let [num1, num2, num3, ...rest] = nums;

console.log(num1, num2, num3);
console.log(rest);
```

```sh
1 2 3
[4, 5, 6, 7, 8, 9, 10]
```

### Destructuring during iteration

```js
const countries = [
  ["Finland", "Helsinki"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];

for (const [country, city] of countries) {
  console.log(country, city);
}
```

```sh
Finland Helsinki
Sweden Stockholm
Norway Oslo
```

```js
const fullStack = [
  ["HTML", "CSS", "JS", "React"],
  ["Node", "Express", "MongoDB"],
];

for (const [first, second, third] of fullStack) {
  console.log(first, second, third);
}
```

```sh
HTML CSS JS
Node Express MongoDB
```

### Destructuring Object

When we destructure the name of the variable we use to destructure should be exactly the same as the key or property of the object. See the example below.

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200,
};
let { width, height, area, perimeter } = rectangle;

console.log(width, height, area, perimeter);
```

```sh
20 10 200 undefined
```

### Renaming during structuring

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200,
};
let { width: w, height: h, area: a, perimeter: p } = rectangle;

console.log(w, h, a, p);
```

```sh
20 10 200 undefined
```

If the key is not found in the object the variable will be assigned to undefined. Sometimes the key might not be in the object, in that case we can give a default value during declaration. See the example.

```js
const rectangle = {
  width: 20,
  height: 10,
  area: 200,
};
let { width, height, area, perimeter = 60 } = rectangle;

console.log(width, height, area, perimeter); //20 10 200 60
//Let us modify the object:width to 30 and perimeter to 80
```

```js
const rectangle = {
  width: 30,
  height: 10,
  area: 200,
  perimeter: 80,
};
let { width, height, area, perimeter = 60 } = rectangle;
console.log(width, height, area, perimeter); //30 10 200 80
```

Destructuring keys as a function parameters. Let us create a function which takes a rectangle object and it returns a perimeter of a rectangle.

### Object parameter without destructuring

```js
// Without destructuring
const rect = {
  width: 20,
  height: 10,
};
const calculatePerimeter = (rectangle) => {
  return 2 * (rectangle.width + rectangle.height);
};

console.log(calculatePerimeter(rect)); // 60
//with destructuring
```

```js
//Another Example
const person = {
  firstName: "Sathish",
  lastName: "Sampath",
  age: 25,
  country: "India",
  job: "Instructor and Developer",
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Redux",
    "Node",
    "MongoDB",
    "Python",
    "D3.js",
  ],
  languages: ["Tamil", "English","Hindi"],
};
// Let us create a function which give information about the person object without destructuring

const getPersonInfo = (obj) => {
  const skills = obj.skills;
  const formattedSkills = skills.slice(0, -1).join(", ");
  const languages = obj.languages;
  const formattedLanguages = languages.slice(0, -1).join(", ");

  personInfo = `${obj.firstName} ${obj.lastName} lives in ${
    obj.country
  }. He is  ${obj.age} years old. He is an ${
    obj.job
  }. He teaches ${formattedSkills} and ${
    skills[skills.length - 1]
  }. He speaks ${formattedLanguages} and a little bit of ${languages[2]}.`;

  return personInfo;
};

console.log(getPersonInfo(person));
```

### Object parameter with destructuring

```js
const calculatePerimeter = ({ width, height }) => {
  return 2 * (width + height);
};

console.log(calculatePerimeter(rect)); // 60
```

```js
// Let us create a function which give information about the person object with destructuring
const getPersonInfo = ({
  firstName,
  lastName,
  age,
  country,
  job,
  skills,
  languages,
}) => {
  const formattedSkills = skills.slice(0, -1).join(", ");
  const formattedLanguages = languages.slice(0, -1).join(", ");

  personInfo = `${firstName} ${lastName} lives in ${country}. He is ${age} years old. He is an ${job}. He teaches ${formattedSkills} and ${
    skills[skills.length - 1]
  }. He speaks ${formattedLanguages} and a little bit of ${languages[2]}.`;

  return personInfo;
};
console.log(getPersonInfo(person));
/*
Sathish Sampath lives in India. He is  25 years old. He is an Instructor and Developer. He teaches HTML, CSS, JavaScript, React, Redux, Node, MongoDB, Python and D3.js. He speaks Tamil, English and a little bit of Hindi
*/
```

### Destructuring object during iteration

```js
const todoList = [
  {
    task: "Prepare JS Test",
    time: "4/1/2020 8:30",
    completed: true,
  },
  {
    task: "Give JS Test",
    time: "4/1/2020 10:00",
    completed: false,
  },
  {
    task: "Assess Test Result",
    time: "4/1/2020 1:00",
    completed: false,
  },
];

for (const { task, time, completed } of todoList) {
  console.log(task, time, completed);
}
```

```sh
Prepare JS Test 4/1/2020 8:30 true
Give JS Test 4/1/2020 10:00 false
Assess Test Result 4/1/2020 1:00 false
```

### Spread or Rest Operator

When we destructure an array we use the spread operator(...) to get the rest elements as array. In addition to that we use spread operator to spread array elements to another array.

### Spread operator to get the rest of array elements

```js
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
let [num1, num2, num3, ...rest] = nums
​
console.log(num1, num2, num3)
console.log(rest)
```

```sh
1 2 3
[4, 5, 6, 7, 8, 9, 10]
```

```js
const countries = [
  "Germany",
  "France",
  "Belgium",
  "Finland",
  "Sweden",
  "Norway",
  "Denmark",
  "Iceland",
];

let [gem, fra, , ...nordicCountries] = countries;

console.log(gem);
console.log(fra);
console.log(nordicCountries);
```

```sh
Germany
France
["Finland", "Sweden", "Norway", "Denmark", "Iceland"]
```

### Spread operator to copy array

```js
const evens = [0, 2, 4, 6, 8, 10];
const evenNumbers = [...evens];

const odds = [1, 3, 5, 7, 9];
const oddNumbers = [...odds];

const wholeNumbers = [...evens, ...odds];

console.log(evenNumbers);
console.log(oddNumbers);
console.log(wholeNumbers);
```

```sh
[0, 2, 4, 6, 8, 10]
[1, 3, 5, 7, 9]
[0, 2, 4, 6, 8, 10, 1, 3, 5, 7, 9]
```

```js
const frontEnd = ["HTML", "CSS", "JS", "React"];
const backEnd = ["Node", "Express", "MongoDB"];
const fullStack = [...frontEnd, ...backEnd];

console.log(fullStack);
```

```sh
["HTML", "CSS", "JS", "React", "Node", "Express", "MongoDB"]
```

### Spread operator to copy object

We can copy an object using a spread operator

```js
const user = {
  name: "Sathish",
  title: "Programmer",
  country: "India",
  city: "Chennai",
};

const copiedUser = { ...user };
console.log(copiedUser);
```

```sh
{name: "Sathish", title: "Programmer", country: "India", city: "Chennai"}
```

Modifying or changing the object while copying

```js
const user = {
  name: "Sathish",
  title: "Programmer",
  country: "India",
  city: "Chennai",
};

const copiedUser = { ...user, title: "instructor" };
console.log(copiedUser);
```

```sh
{name: "Sathish", title: "instructor", country: "India", city: "Chennai"}
```

#### Spread operator with arrow function

Whenever we like to write an arrow function which takes unlimited number of arguments we use a spread operator. If we use a spread operator as a parameter, the argument passed when we invoke a function will change to an array.

```js
const sumAllNums = (...args) => {
  console.log(args);
};

sumAllNums(1, 2, 3, 4, 5);
```

```sh
[1, 2, 3, 4, 5]

```

```js
const sumAllNums = (...args) => {
  let sum = 0;
  for (const num of args) {
    sum += num;
  }
  return sum;
};

console.log(sumAllNums(1, 2, 3, 4, 5));
```

```sh
15

```


[Next >> Destructuring Spreading >>](../11_destructuring_spreading/destructuring_spreading.md)



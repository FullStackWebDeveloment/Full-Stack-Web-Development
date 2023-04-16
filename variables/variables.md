<div align="center">
  <h1>JavaScript</h1>
</div>

[<< Day 1](../readMe.md) | [Day 3 >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)

# Variables

### Storing the information you need — Variables

- [What is a variable?](#What-is-a-variable?)
- [Non-Primitive Data Types](#non-primitive-data-types)

## What is a variable?

A variable is a container for a value, like a number we might use in a sum, or a string that we might use as part of a sentence.

## Declaring a variable

To use a variable, you've first got to create it — more accurately, we call this declaring the variable. To do this, we type the keyword `let` followed by the name you want to call your variable:

**Example:**

```js
let firstName; // first name of a person
let lastName; // last name of a person
let country; // country
```

Here we're creating two variables called `firstName`,`lastName` and `country`.They currently have no value; they are empty containers. When you enter the variable names, you should get a value of undefined returned.

**Note:**
`In JavaScript, all code instructions should end with a semicolon (;) — your code may work correctly for single lines, but probably won't when you are writing multiple lines of code together. Try to get into the habit of including it.`

## Initializing a variable

Once you've declared a variable, you can initialize it with a value. You do this by typing the variable name, followed by an equals sign `(=)`, followed by the value you want to give it

**Example:**

```js
let firstName = "Sathish"; // first name of a person
let lastName = "Sampath"; // last name of a person
let country = "India"; // country
```

## You can declare and initialize a variable at the same time, like this:

```js
let firstName = "Guha iyivariya"; // first name of a person
let lastName = "Kotti"; // last name of a person
let country = "India"; // country
```

## An aside on variable naming rules

You can call a variable pretty much anything you like, but there are limitations. Generally, you should stick to just using Latin characters (0-9, a-z, A-Z) and the underscore character.

- You shouldn't use other characters because they may cause errors or be hard to understand for an international audience.
- Don't use underscores at the start of variable names — this is used in certain JavaScript constructs to mean specific things, so may get confusing.
- Don't use numbers at the start of variables. This isn't allowed and causes an error.
- A safe convention to stick to is so-called "lower camel case", where you stick together multiple words, using lower case for the whole first word and then capitalize subsequent words. We've been using this for our variable names in the article so far.
- Make variable names intuitive, so they describe the data they contain. Don't just use single letters/numbers, or big long phrases.
- Variables are case sensitive — so `myage` is a different variable from `myAge`.
  One last point: you also need to avoid using JavaScript reserved words as your variable names — by this, we mean the words that make up the actual syntax of JavaScript! So, you can't use words like `var`, `function`, `let`, and for as variable names. Browsers recognize them as different code items, and so you'll get errors.

## Reserved words

- break
- case
- catch
- class
- const
- continue
- debugger
- default
- delete
- do
- else
- export
- extends
- false
- finally
- for
- function
- if
- import
- in
- instanceof
- new
- null
- return
- super
- switch
- this
- throw
- true
- try
- typeof
- var
- void
- while
- with
  The following are only reserved when they are found in strict mode code:
- `let` (also reserved in `const`, `let`, and `class` declarations)
- `static`
- `yield` (also reserved in generator function bodies)
  The following are only reserved when they are found in module code or async function bodies:

`await`

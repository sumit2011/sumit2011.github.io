# Java Script

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. Introduction:
Js is powerful, flexible and fast programming lang. it is used in web development. It
provide the dynamic behavior to the website.

## Fundamental of Js 
Js is powerful, flexible and fast programming lang. it is used in web development. It
provide the dynamic behavior to the website.

### Console
It is a keyword refer to an object. There are methods built into `console` object one of them is `.log()` method. When we write `console.log()` it will print the wriiten information in paranthesis to the console.

### Comment
As we write JavaScript, we can write comments in our code that the computer will
ignore as our program runs. These comments exist just for human readers.
1. **Single line comment:**
    A single-line comment will comment out a single line and is denoted with
    two forward slashes `//` preceding it.
    ```javascript
    // Prints 5 to the console
    console.log(5);
    ```

2. **Multi-line comment**
    A multi-line comment will comment out multiple lines and is denoted
    with /* to begin the comment, and */ to end the comment.
    ```javascript
    /*
    This is all commented
    console.log(10);
    None of this is going to run!
    console.log(99);
    */
    ```

### Data types
In js there are 8 fundamental data types
1. **Number :** any numerical value including decimal numbers.

    Ex: 4,8,80,60.65
2. **Bigint:** Any number, greater than 2 53 -1 or less than -(2 53 -1), with n appended to
the number: 1234567890123456n.
3. **String:** a group of characters (letters, numbers,spaces,symbols etc) surrounded
by single quotes or double quotes.
4. **Boolean:** It has only two possible value true and false without quotes.
5. **Null:** it represent the absence of a value and it is represented by null keyword.

6. **Undefined:** it is denoted by keyword ‘undefined’ without quotes.it means that a
given value does not exist.
7. **Symbol:** symbols are unique identifiers, useful in more complex coding.
8. **Object:** collection of related data.
The first 7 datatype are consider as primitive data types.

### Arithmatic Operators
It performs a task in our code. Js has several built-in arithmetic operators that allow us
to perform mathematical calculations on numbers.
1. Add: +
2. Subtract: -
3. Multiply: *
4. Divide: /
5. Remainder: %

```javascript
console.log(3 + 4); // Prints 7
console.log(5 - 1); // Prints 4
console.log(4 * 2); // Prints 8
console.log(9 / 3); // Prints 3
console.log(11 % 3); // Prints 2
console.log(12 % 3); // Prints 0
```

### string concatenation
the process of appending one string to the another is called concatenation. When a `+` operator is used on two strings, it appends the right string to the left string:
```javascript
console.log(&#39;hi&#39; + &#39;ya&#39;); // Prints &#39;hiya&#39;
console.log(&#39;wo&#39; + &#39;ah&#39;); // Prints &#39;woah&#39;
console.log(&#39;I love to &#39; + &#39;code.&#39;)
// Prints &#39;I love to code.&#39;
```

### Properties

All datatypes have access to specific properties that are passed down to each instance. which are created in the js code. Ex: .length
```javascript
console.log(&#39;Hello&#39;.length); // Prints 5
```

### methods
methods are actions we can perform. Datatypes have access to specific methods that allow us to handle instance of that data type.
```javascript
console.log(&#39;hello&#39;.toUpperCase()); // Prints &#39;HELLO&#39;
console.log(&#39;Hey&#39;.startsWith(&#39;H&#39;)); // Prints true
```

### Built in objects
In addition to console, there are other objects built into JavaScript.
Ex: Math is a built in object that performs more complex mathematical operations than
arithmetic.
```javascript
console.log(Math.random()); // Prints a random number between 0 and 1
console.log(Math.floor(Math.random() * 50)); // Prints a random whole number between
0 and 50
```

To see all of the properties and methods on the Math object, take a look at the
documentation here.

## Javascript variables
A variable is a container for a value. Informations are stored in variables. It provide a way of labeling data with a descriptive name.

### Create a variable using var
Before es6 version of js we could only use var keyword to declare variables. Var is short
for variable. In given example Arya is stored in a variable labeled as myName.
```javascript
var myName = &#39;Arya&#39;;
console.log(myName);
// Output: Arya
```
Rules for creating a variable:
* Can't start with number
* Variable name are case sensitive
* Cant be same as keywords
### Create a variable using let
Let and const are introduced in es6. Let keyword signals that the variable can be
reassigned a diff value later on.
```javascript
let meal = &#39;Enchiladas&#39;;
console.log(meal); // Output: Enchiladas
meal = &#39;Burrito&#39;;
console.log(meal); // Output: Burrito
```
{{< admonition type=note title="Note" open=true >}}
If we don’t assign a value to a variable declared using the `let` keyword it automatically has a value of `undefined`. We can reassign the value in let. Can not be redeclare.

{{< /admonition >}}


### Create a variable using const
The const keyword was also introduced in ES6, and is short for the word constant.
However, a const variable cannot be reassigned because it is constant. If we try to
reassign a const variable, we’ll get a TypeError. Constant variables must be assigned a
value when declared. If we try to declare a const variable without a value, we’ll get
a SyntaxError.
```javascript
const myName = &#39;Gilberto&#39;;
console.log(myName); // Output: Gilberto
```
### mathematical assignment operator
```javascript
let w = 4;
w += 1;
console.log(w); // Output: 5
let x = 20;
x -= 5; // Can be written as x = x - 5
console.log(x); // Output: 15

let y = 50;
y *= 2; // Can be written as y = y * 2
console.log(y); // Output: 100

let z = 8;
z /= 2; // Can be written as z = z / 2
console.log(z); // Output: 4
```
### the increment and decrement operator
Other mathematical assignment operators include the increment operator (++)
and decrement operator (--).The increment operator will increase the value of the
variable by 1. The decrement operator will decrease the value of the variable by 1. For
example:
```javascript
let a = 10;

a++;
console.log(a); // Output: 11
let b = 20;
b--;
console.log(b); // Output: 19
```
### string concatenation with variable
```javascript
let myPet = &#39;armadillo&#39;;
console.log(&#39;I own a pet &#39; + myPet + &#39;.&#39;);
// Output: &#39;I own a pet armadillo.&#39;
```
### String interpolation
In the ES6 version of JavaScript, we can insert, or interpolate, variables into strings
using template literals. A template literal is wrapped by backticks `. it inc the redability of
the code.
```javascript
const myPet = &#39;armadillo&#39;;
console.log(`I own a pet ${myPet}.`);
// Output: I own a pet armadillo.
```
### Typeof operator
If we need to check the data type of a variable’s value, we can use the typeof operator.
The typeof operator checks the value to its right and returns, or passes back, a string of
the data type.
```javascript
const unknown1 = &#39;foo&#39;;
console.log(typeof unknown1); // Output: string

const unknown2 = 10;
console.log(typeof unknown2); // Output: number

const unknown3 = true;
console.log(typeof unknown3); // Output: Boolean
```

## Js control flow
A conditional statement checks a specific condition(s) and performs a task based on the
condition(s).
### If statement
In programming, we can also perform a task based on a condition using an if statement:
```javascript
if (true) {
console.log(&#39;This message will print!&#39;);
}
// Prints: This message will print!
```
### If…Else statements
If we wanted to add some default behavior to the if statement, we can add
an else statement to run a block of code when the condition evaluates to false.
An else statement must be paired with an if statement, and together they are referred to
as an if...else statement.
```javascript
if (false) {
console.log(&#39;The code in this block will not run.&#39;);
} else {
console.log(&#39;But the code in this block will!&#39;);
}
```
// Prints: But the code in this block will!
### Comparison operaor
sometimes we need to use different types of operators to compare values. These
operators are called comparison operators. Comparison operators compare the value
on the left with the value on the right.
Here is a list of some handy comparison operators and their syntax:
* Less than: &lt;
* Greater than: &gt;
* Less than or equal to: &lt;=
* Greater than or equal to: &gt;=
* Is equal to: ===
* Is not equal to: !==
### Logical operaors
Working with conditionals means that we will be using booleans, true or false values. In
JavaScript, there are operators that work with boolean values known as logical
operators
There are three logical operators:
* the and operator (&amp;&amp;)
* the or operator (||)
* the not operator, otherwise known as the bang operator (!)
```javascript
if (stopLight === &#39;green&#39; &amp;&amp; pedestrians === 0) {
console.log(&#39;Go!&#39;);

} else {
console.log(&#39;Stop&#39;);
}
if (day === &#39;Saturday&#39; || day === &#39;Sunday&#39;) {
console.log(&#39;Enjoy the weekend!&#39;);
} else {
console.log(&#39;Do some work.&#39;);
}
let excited = true;
console.log(!excited); // Prints false

let sleepy = false;
console.log(!sleepy); // Prints true
```
### Truthy and Falsy
The list of falsy values includes:
* 0
* Empty strings like &quot;&quot; or &#39;&#39;
* null, which represents when there is no value at all
* undefined, which represents when a declared variable lacks a value
* NaN, or Not a Number

### Truthy and Falsy Assignment
```javascript
let username = &#39;&#39;;
let defaultName;

if (username) {
defaultName = username;
} else {

defaultName = &#39;Stranger&#39;;
}

console.log(defaultName); // Prints: Stranger
```
### ternary operator
In the spirit of using short-hand syntax, we can use a ternary operator to simplify
an if...else statement.
Take a look at the if...else statement example:
```javascript
let isNightTime = true;
if (isNightTime) {
  console.log(&#39;Turn on the lights!&#39;);
} else {
  console.log(&#39;Turn off the lights!&#39;);
}
```
We can use a ternary operator to perform the same functionality:
```javascript
isNightTime ? console.log(&#39;Turn on the lights!&#39;) : console.log(&#39;Turn off the lights!&#39;);
```

* The condition, isNightTime, is provided before the ?.
* Two expressions follow the ? and are separated by a colon :.
* If the condition evaluates to true, the first expression executes.
* If the condition evaluates to false, the second expression executes.

### Else if statement
We can add more conditions to our if...else with an else if statement. The else
```javascript
if statement allows for more than two possible outcomes. You can add as many else
if statements as you’d like, to make more complex conditionals!
let stopLight = &#39;yellow&#39;;

if (stopLight === &#39;red&#39;) {
console.log(&#39;Stop!&#39;);
} else if (stopLight === &#39;yellow&#39;) {

console.log(&#39;Slow down.&#39;);
} else if (stopLight === &#39;green&#39;) {
console.log(&#39;Go!&#39;);
} else {
console.log(&#39;Caution, unknown!&#39;);
}
```
### The switch keyword
A switch statement provides an alternative syntax that is easier to read and write.
A switch statement looks like this:
```javascript 
let groceryItem = &#39;papaya&#39;;
switch (groceryItem) {
  case &#39;tomato&#39;:
    console.log(&#39;Tomatoes are $0.49&#39;);
    break;
  case &#39;lime&#39;:
    console.log(&#39;Limes are $1.49&#39;);
    break;
  case &#39;papaya&#39;:
    console.log(&#39;Papayas are $1.29&#39;);
    break;
  default:
    console.log(&#39;Invalid item&#39;);
    break;
}
// Prints &#39;Papayas are $1.29&#39;
```

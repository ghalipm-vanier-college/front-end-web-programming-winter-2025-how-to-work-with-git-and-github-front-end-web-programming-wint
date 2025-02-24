# **Lecture 3: Introduction to JavaScript**

## Table of Contents

1. [Introduction to JavaScript](#1-introduction-to-javascript)  
   1.1 [What is JavaScript?](#11-what-is-javascript)  
   1.2 [History and Evolution of JavaScript](#12-history-and-evolution-of-javascript)  
   1.3 [Role of JavaScript in Web Development](#13-role-of-javascript-in-web-development)  
   1.4 [How JavaScript Works in the Browser](#14-how-javascript-works-in-the-browser)  
   1.5 [Benefits and Use Cases of JavaScript](#15-benefits-and-use-cases-of-javascript)  

2. [Types of JavaScript](#2-types-of-javascript)  
   2.1 [Inline JavaScript](#21-inline-javascript)  
   2.2 [Internal JavaScript](#22-internal-javascript)  
   2.3 [External JavaScript](#23-external-javascript)  
   2.4 [Differences and Best Practices](#24-differences-and-best-practices)  

3. [JavaScript Basics](#3-javascript-basics)  
   3.1 [Variables and Constants](#31-variables-and-constants)  
       3.1.1 [Declaring Variables (`var`, `let`, `const`)](#311-declaring-variables-var-let-const)  
       3.1.2 [Constants in JavaScript](#312-constants-in-javascript)  
   3.2 [Data Types](#32-data-types)  
       3.2.1 [Primitive Data Types](#321-primitive-data-types)  
       3.2.2 [Reference Data Types](#322-reference-data-types)  
   3.3 [Data Type Conversion](#33-data-type-conversion)  
       3.3.1 [Implicit and Explicit Conversion](#331-implicit-and-explicit-conversion)  
       3.3.2 [Converting between Data Types](#332-converting-between-data-types)  
   3.4 [Operators](#34-operators)  
       3.4.1 [Arithmetic Operators](#341-arithmetic-operators)  
       3.4.2 [Comparison Operators](#342-comparison-operators)  
       3.4.3 [Logical Operators](#343-logical-operators)  
       3.4.4 [Assignment Operators](#344-assignment-operators)  
   3.5 [Control Structures](#35-control-structures)  
       3.5.1 [If-Else Statements](#351-if-else-statements)  
       3.5.2 [Switch Case](#352-switch-case)  
       3.5.3 [Loops](#353-loops)  
   3.6 [Arrays](#36-arrays)  
       3.6.1 [Creating Arrays](#361-creating-arrays)  
       3.6.2 [Accessing and Modifying Elements](#362-accessing-and-modifying-elements)  
       3.6.3 [Array Methods](#363-array-methods)  
   3.7 [Functions and Scope](#37-functions-and-scope)  
       3.7.1 [Declaring and Using Functions](#371-declaring-and-using-functions)  
       3.7.2 [Parameters and Return Values](#372-parameters-and-return-values)  
       3.7.3 [Function Scope](#373-function-scope)  
       3.7.4 [Anonymous Functions and Arrow Functions](#374-anonymous-functions-and-arrow-functions)  

4. [JavaScript: An Object-Based Programming Language](#4-javascript-an-object-based-programming-language)  
   4.1 [Objects in JavaScript](#41-objects-in-javascript)  
   4.2 [Creating an Object](#42-creating-an-object)  
       4.2.1 [Object Literals](#421-object-literals)  
       4.2.2 [Using `new Object()`](#422-using-new-object)  
   4.3 [Using an Object’s Properties](#43-using-an-objects-properties)  
   4.4 [Calling an Object’s Methods](#44-calling-an-objects-methods)  

5. [Using JavaScript’s Native Object Types](#5-using-javascripts-native-object-types)  
   5.1 [String Object](#51-string-object)  
       5.1.1 [String Methods](#511-string-methods)  
   5.2 [Array Object](#52-array-object)  
       5.2.1 [Array Methods](#521-array-methods)  
   5.3 [Math Object](#53-math-object)  
       5.3.1 [Common Methods](#531-common-methods)  
   5.4 [Number Object](#54-number-object)  
   5.5 [Date Object](#55-date-object)  

6. [Creating Custom Objects](#6-creating-custom-objects)  
   6.1 [Introduction to Custom Objects](#61-introduction-to-custom-objects)  
   6.2 [Creating Custom Objects Using Constructor Functions](#62-creating-custom-objects-using-constructor-functions)  
   6.3 [Adding Properties and Methods](#63-adding-properties-and-methods)  
   6.4 [Using Custom Objects](#64-using-custom-objects)  

7. [Creating and Using New Types of Objects (Reference Types)](#7-creating-and-using-new-types-of-objects-reference-types)  
   7.1 [Understanding Reference Types](#71-understanding-reference-types)  
   7.2 [Introduction to Prototypes](#72-introduction-to-prototypes)  
   7.3 [Creating New Types of Objects Using Prototypes](#73-creating-new-types-of-objects-using-prototypes)  
   7.4 [Extending Object Prototypes](#74-extending-object-prototypes) 

## 1. Introduction to JavaScript

### 1.1 What is JavaScript?

JavaScript is a versatile, high-level programming language primarily used to enhance web pages, making them interactive and dynamic. It enables developers to implement complex features such as animations, form validations, and asynchronous content updates.

### 1.2 History and Evolution of JavaScript

- **1995**: Created by Brendan Eich at Netscape and originally named Mocha.
- **Renamed**: Became LiveScript and finally JavaScript to reflect Netscape's support of Java within its browser.
- **Standardization**: ECMAScript was established to standardize JavaScript.
- **Evolution**: Regular updates have introduced features like ES6 modules, arrow functions, and async/await.

### 1.3 Role of JavaScript in Web Development

- **Client-Side Scripting**: Runs directly in the user's browser without needing server interaction.
- **Interactivity**: Enhances user experience through interactive elements.
- **Full-Stack Development**: With environments like Node.js, JavaScript is used on both the client and server sides.

### 1.4 How JavaScript Works in the Browser

- **Execution Environment**: JavaScript code is executed by the browser's JavaScript engine (e.g., V8 in Chrome).
- **DOM Manipulation**: Interacts with the Document Object Model to modify HTML and CSS in real-time.
- **Event Handling**: Responds to user actions like clicks, hovers, and key presses.

### 1.5 Benefits and Use Cases of JavaScript

- **Dynamic Websites**: Creates responsive and interactive web pages.
- **Web Applications**: Powers single-page applications (SPAs) using frameworks like React and Angular.
- **Server-Side Development**: Utilized in backend development with Node.js.
- **Cross-Platform Apps**: Develops mobile apps using React Native and desktop apps with Electron.

---

## 2. Types of JavaScript

### 2.1 Inline JavaScript

Code written directly within an HTML element's attribute.

```html
<button onclick="alert('Button clicked!')">Click Me</button>
```

- **Use Case**: Simple, quick scripts tied to specific elements.
- **Limitation**: Harder to maintain and not recommended for larger projects.

### 2.2 Internal JavaScript

Script embedded within the `<script>` tag inside an HTML document.

```html
<!DOCTYPE html>
<html>
<head>
  <script>
    function greet() {
      alert('Hello, World!');
    }
  </script>
</head>
<body>
  <button onclick="greet()">Greet</button>
</body>
</html>
```

- **Use Case**: Scripts specific to a single page.
- **Limitation**: Can clutter HTML files and is less reusable.

### 2.3 External JavaScript

Script written in a separate `.js` file and linked using the `<script>` tag with the `src` attribute.

```html
<script src="app.js"></script>
```

- **Use Case**: Reusable code across multiple pages.
- **Advantage**: Enhances maintainability and keeps HTML files clean.

### 2.4 Differences and Best Practices

- **Maintainability**: External scripts are easier to manage.
- **Performance**: External scripts can be cached by browsers.
- **Best Practice**: Use external scripts for scalability and cleaner code separation.

---

## 3. JavaScript Basics

### 3.1 Variables and Constants

#### 3.1.1 Declaring Variables (`var`, `let`, `const`)

- **`var`**: Function-scoped or globally scoped.

  ```javascript
  var age = 30;
  ```

- **`let`**: Block-scoped, introduced in ES6.

  ```javascript
  let name = 'Alice';
  ```

- **`const`**: Block-scoped, cannot be reassigned.

  ```javascript
  const PI = 3.14;
  ```

#### 3.1.2 Constants in JavaScript

- **Immutable Bindings**: `const` variables cannot be reassigned.
- **Mutable Objects**: Objects declared with `const` can have their properties changed.

  ```javascript
  const person = { name: 'Bob' };
  person.name = 'Charlie'; // Allowed
  ```

### 3.2 Data Types

#### 3.2.1 Primitive Data Types

- **String**

  ```javascript
  let greeting = 'Hello';
  ```

- **Number**

  ```javascript
  let score = 100;
  ```

- **Boolean**

  ```javascript
  let isActive = true;
  ```

- **Null**

  ```javascript
  let data = null;
  ```

- **Undefined**

  ```javascript
  let result;
  ```

- **Symbol** (ES6)

  ```javascript
  let sym = Symbol('id');
  ```

#### 3.2.2 Reference Data Types

- **Object**

  ```javascript
  let user = { name: 'Dave', age: 25 };
  ```

- **Array**

  ```javascript
  let colors = ['red', 'green', 'blue'];
  ```

### 3.3 Data Type Conversion

#### 3.3.1 Implicit and Explicit Conversion

- **Implicit Conversion**

  ```javascript
  let x = '5' * 2; // 10 (string '5' converted to number)
  ```

- **Explicit Conversion**

  ```javascript
  let y = Number('5'); // Converts string to number 5
  ```

#### 3.3.2 Converting between Data Types

- **String to Number**

  ```javascript
  Number('123'); // 123
  parseInt('123.45'); // 123
  ```

- **Number to String**

  ```javascript
  String(123); // '123'
  (123).toString(); // '123'
  ```

- **Boolean Conversion**

  ```javascript
  Boolean(1); // true
  Boolean(0); // false
  ```

### 3.4 Operators

#### 3.4.1 Arithmetic Operators

- Addition `+`, Subtraction `-`, Multiplication `*`, Division `/`, Modulus `%`, Exponentiation `**`

  ```javascript
  let sum = 10 + 5; // 15
  ```

#### 3.4.2 Comparison Operators

- Equal `==`, Strict Equal `===`, Not Equal `!=`, Greater Than `>`, Less Than `<`

  ```javascript
  5 == '5'; // true
  5 === '5'; // false
  ```

#### 3.4.3 Logical Operators

- AND `&&`, OR `||`, NOT `!`

  ```javascript
  if (isMember && age > 18) { /* ... */ }
  ```

#### 3.4.4 Assignment Operators

- Basic `=`, Addition `+=`, Subtraction `-=`

  ```javascript
  let count = 1;
  count += 2; // count is now 3
  ```

### 3.5 Control Structures

#### 3.5.1 If-Else Statements

```javascript
if (score >= 60) {
  console.log('Pass');
} else {
  console.log('Fail');
}
```

#### 3.5.2 Switch Case

```javascript
switch (day) {
  case 1:
    console.log('Monday');
    break;
  default:
    console.log('Another day');
}
```

#### 3.5.3 Loops

- **For Loop**

  ```javascript
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }
  ```

- **While Loop**

  ```javascript
  while (n > 0) {
    n--;
  }
  ```

- **Do-While Loop**

  ```javascript
  do {
    n--;
  } while (n > 0);
  ```

### 3.6 Arrays

#### 3.6.1 Creating Arrays

```javascript
let fruits = ['Apple', 'Banana', 'Cherry'];
```

#### 3.6.2 Accessing and Modifying Elements

```javascript
let firstFruit = fruits[0]; // 'Apple'
fruits[1] = 'Blueberry'; // Replaces 'Banana' with 'Blueberry'
```

#### 3.6.3 Array Methods

- **`push()`**: Adds element to end.

  ```javascript
  fruits.push('Durian');
  ```

- **`pop()`**: Removes last element.

  ```javascript
  fruits.pop();
  ```

### 3.7 Functions and Scope

#### 3.7.1 Declaring and Using Functions

```javascript
function add(a, b) {
  return a + b;
}
```

#### 3.7.2 Parameters and Return Values

- **Parameters**: Inputs to the function.
- **Return Value**: Output of the function.

  ```javascript
  let total = add(5, 7); // 12
  ```

#### 3.7.3 Function Scope

- **Global Scope**: Accessible anywhere.
- **Local Scope**: Accessible within the function.

  ```javascript
  let globalVar = 'Global';

  function scopeTest() {
    let localVar = 'Local';
    console.log(globalVar); // Accessible
    console.log(localVar); // Accessible
  }

  console.log(localVar); // Error: localVar is not defined
  ```

#### 3.7.4 Anonymous Functions and Arrow Functions

- **Anonymous Function**

  ```javascript
  let multiply = function (a, b) {
    return a * b;
  };
  ```

- **Arrow Function**

  ```javascript
  let divide = (a, b) => a / b;
  ```

---

## 4. JavaScript: An Object-Based Programming Language

### 4.1 Objects in JavaScript

Objects are collections of key-value pairs.

```javascript
let book = {
  title: '1984',
  author: 'George Orwell',
  pages: 328,
  read: function () {
    console.log('Reading');
  },
};
```

### 4.2 Creating an Object

#### 4.2.1 Object Literals

Defined using curly braces.

```javascript
let laptop = {
  brand: 'Dell',
  model: 'XPS 13',
};
```

#### 4.2.2 Using `new Object()`

```javascript
let phone = new Object();
phone.brand = 'Apple';
phone.model = 'iPhone 12';
```

### 4.3 Using an Object’s Properties

- **Accessing Properties**

  ```javascript
  console.log(book.title); // '1984'
  ```

- **Modifying Properties**

  ```javascript
  book.pages = 350;
  ```

### 4.4 Calling an Object’s Methods

```javascript
book.read(); // Outputs: 'Reading'
```

---

## 5. Using JavaScript’s Native Object Types

### 5.1 String Object

#### 5.1.1 String Methods

- **`length`**

  ```javascript
  'Hello'.length; // 5
  ```

- **`toUpperCase()`**

  ```javascript
  'hello'.toUpperCase(); // 'HELLO'
  ```

- **`split()`**

  ```javascript
  'a,b,c'.split(','); // ['a', 'b', 'c']
  ```

### 5.2 Array Object

#### 5.2.1 Array Methods

- **`concat()`**

  ```javascript
  [1, 2].concat([3, 4]); // [1, 2, 3, 4]
  ```

- **`slice()`**

  ```javascript
  [1, 2, 3, 4].slice(1, 3); // [2, 3]
  ```

- **`indexOf()`**

  ```javascript
  ['a', 'b', 'c'].indexOf('b'); // 1
  ```

### 5.3 Math Object

#### 5.3.1 Common Methods

- **`Math.random()`**

  ```javascript
  Math.random(); // Random number between 0 and 1
  ```

- **`Math.floor()`**

  ```javascript
  Math.floor(4.7); // 4
  ```

- **`Math.sqrt()`**

  ```javascript
  Math.sqrt(16); // 4
  ```

### 5.4 Number Object

- **`toFixed()`**

  ```javascript
  let num = 3.14159;
  num.toFixed(2); // '3.14'
  ```

- **`toString()`**

  ```javascript
  (255).toString(16); // 'ff'
  ```

### 5.5 Date Object

#### 5.5.1 Working with Dates

- **Current Date and Time**

  ```javascript
  let now = new Date();
  ```

- **Specific Date**

  ```javascript
  let birthday = new Date('1990-01-01');
  ```

- **Date Methods**

  ```javascript
  now.getFullYear(); // e.g., 2024
  now.getMonth(); // 0 (January)
  now.getDate(); // Day of the month
  ```

---

## 6. Creating Custom Objects

### 6.1 Introduction to Custom Objects

Custom objects allow for the creation of complex data structures tailored to specific needs.

### 6.2 Creating Custom Objects Using Constructor Functions

```javascript
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
```

### 6.3 Adding Properties and Methods

```javascript
Car.prototype.getInfo = function () {
  return `${this.make} ${this.model} (${this.year})`;
};
```

### 6.4 Using Custom Objects

```javascript
let myCar = new Car('Tesla', 'Model S', 2020);
console.log(myCar.getInfo()); // 'Tesla Model S (2020)'
```

---

## 7. Creating and Using New Types of Objects (Reference Types)

### 7.1 Understanding Reference Types

- **Reference Types**: Objects that reference memory locations.
- **Mutability**: Reference types are mutable and can be altered.

### 7.2 Introduction to Prototypes

- **Prototype Chain**: Mechanism by which objects inherit features from one another.
- **`prototype` Property**: Every function has a `prototype` property used to attach methods and properties.

### 7.3 Creating New Types of Objects Using Prototypes

```javascript
function Employee(name, position) {
  this.name = name;
  this.position = position;
}

Employee.prototype.work = function () {
  console.log(`${this.name} is working as a ${this.position}`);
};
```

### 7.4 Extending Object Prototypes

- **Adding Methods to Built-in Objects**

  ```javascript
  Array.prototype.last = function () {
    return this[this.length - 1];
  };

  let nums = [1, 2, 3];
  console.log(nums.last()); // 3
  ```

- **Caution**: Modifying built-in prototypes can lead to conflicts and unexpected behaviors.

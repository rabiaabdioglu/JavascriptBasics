
- [Javascript Basics](#javascript-basics)
  - [Data Types](#data-types)
  - [Var Let Const](#var-let-const)
  - [Data Type Conversions](#data-type-conversions)
  - [Loops](#loops)
  - [Math](#math)
  - [String](#string)
  - [Array](#array)
  - [Function](#function)
  - [Scope](#scope)
  - [Object](#object)
  - [DOM Manipulation](#dom-manipulation)
  - [Elements](#elements)
  - [Navigating DOM Elements](#navigating-dom-elements)
  - [Dynamic Element](#dynamic-element)
  - [Dynamic Attributes](#dynamic-attributes)
  - [Event Listeners and Objects](#event-listeners-and-objects)
  - [Error Handling](#error-handling)


## Javascript Basics
#### Data Types

```javascript
var variable = 3.14;                 // Number Data Type
console.log(typeof variable);        // Data type of the variable

var name = "Jane";                  // String Data Type
console.log(name);                   // Print to the console

var a = false;                       // Boolean
var numbers = [1, 2, 3];             // Array

var person = {                       // Object
    name: "Jane",
    age: 24
};

var date = new Date();               // Date

var print = function() {             // Function
    console.log("Hello");
};

```

#### Var Let Const
###### var: Global/function scope
###### Can be reassigned later
###### Scoped only within functions (function scope)
###### Variables declared with var inside function curly braces are not accessible from outside.



```javascript

var name = "Jane Doe";
console.log(name);

name = "Jane";   // Can be reassigned later
console.log(name);



```

###### let: Block scope
###### Can be reassigned later
###### Can only be declared once within the same scope.
###### Trying to redeclare it will result in an error that stops the code execution.



```javascript


let a, b;

a = 50;   // Can assign a value later
b = 77;

console.log(a + b);

```

###### const: Block scope, immutable
###### Cannot be reassigned after the initial assignment
###### Can only be declared once within the same scope.
###### Trying to redeclare it will result in an error that stops the code execution


```javascript


const name = "Jane Doe";     // Value assigned once and remains constant

console.log(name);

name = "Jane";    // Will throw an error



```
###### In arrays, 'a' points to the starting position of the array.
###### Therefore, 'a' cannot be changed, but elements can be pushed into the array.



```javascript

const a = [1, 2, 3, 4, 5];

console.log(a);

a = [1, 2, 3, 4, 5];    // This will result in an error

a.push(6);


```

#### Data Type Conversions

```javascript

let value;

value = String([1, 2, 3, 4]);      // Convert to string
value = (10).toString();

value = Number([1, 2, 3, 4]);    // Convert to number

value = parseFloat("3.14");   // Convert to float
  
value = parseInt("3");        // Convert to integer

value = Boolean(0);           // Convert to boolean


```

#### Loops

```javascript

const students = ["Jack", "Janice", "Joe"];

let i = 0;

// While loop
while (i < students.length) {
    console.log(students[i]);
    i++;
}

// For loop
for (i = 0; i < students.length; i++) {
    console.log(students[i]);
}

// forEach loop
students.forEach(function(student, i) {
    console.log(student, i);
});



```

#### Math

```javascript

value = Math.PI;                // value is assigned to the constant pi (π)
value = Math.E;                // value is assigned to the base of the natural logarithm (e)

value = Math.round(3.6);      // rounds to the nearest integer
value = Math.ceil(3.7);       // rounds up to the nearest integer
value = Math.floor(3.7);      // rounds down to the nearest integer
value = Math.sqrt(36);        // calculates the square root
value = Math.abs(-85);        // calculates the absolute value
value = Math.pow(x, y);       // calculates x raised to the power of y
value = Math.max(96, -56);    // returns the maximum value between two numbers
value = Math.min(5, 32);      // returns the minimum value between two numbers

value = Math.random();        // generates a random number between 0 and 1
value = Math.floor(Math.random() * 20 + 1);  // generates a random integer between 1 and 20


```

#### String

```javascript

const firstName = "Jane";
const lastName = "Doe";
const fullName = "Jane Doe";

firstName.length;               // length of the string

firstName.concat(" ", lastName);  // concatenate two strings

firstName.toLowerCase();        // convert to lowercase

firstName.toUpperCase();        // convert to uppercase

firstName[firstName.length - 1];  // get the character at the last index

lastName.indexOf("o");          // find the first index of the character "o"

firstName.charAt(4);            // get the character at the 4th index

fullName.split(" ");            // split the string by spaces

fullName.replace("Jane", "Janice");  // replace "Jane" with "Janice"

fullName.includes("ne");        // check if the string includes the substring "ne"

// Template Literal Example
const templateExample = `Name: ${firstName}\nLast Name: ${lastName}`;




```

#### Array


```javascript


const array = [1, 2, 3, 6, 5, 92, 53];    // Creating an array

// You can also create an array using: 
// const array = new Array(1, 2, 3, 6, 5, 92, 53);

array.length;           // Length of the array

array[0];               // Accessing element at index 0

array[0] = 80;          // Modifying the element at index 0

array.indexOf(92);      // Finding the first index of value 92

array.push(2000);       // Adding a value to the end of the array

array.unshift(3000);    // Adding a value to the beginning of the array

array.pop();            // Removing and returning the last element

array.shift();          // Removing and returning the first element

array.splice(x, y);     // Removing y elements starting from index x

array.reverse();        // Reversing the order of elements in the array

value = array.sort();   // Sorting the array

value = array.sort(function(x, y){  // Sorting from small to large
    return x - y;
});

value = array.sort(function(x, y){  // Sorting from large to small
    return y - x;
});



```

#### Function


```javascript
   
  // Function    -- Outside an object 
      
        const greetFunction = function(name){
        console.log("Hello " + name);};

        greetFunction("Jane");
   
   // (IIFE)

       (function(name){
        console.log("Hello: " + name);})("Jane");

  // Method    -- Inside an object 

      const database = {
          host: "localhost",
          add: function(){                  // No parameters
              console.log("Added");
          },
          update:function(id){               // With parameters
            console.log(`Id: ${id} Updated`);  
          },
          delete:function(id){
            console.log(`Id: ${id} Deleted`);  
          }
      }

      console.log(database.host);
      database.delete(10);


```

#### Function for Calculating Factorials using Recursion
###### Demonstrating function calls and recursive techniques for optimized coding solutions.


```javascript
function factorial(n) {
  if (n === 0 || n === 1) {
    return 1; // Factorial is 1 for 0 and 1
  } else {
    return n * factorial(n - 1); // Recursive call
  }
}

const num = 5;
const result = factorial(num);
console.log(`Factorial of ${num} is ${result}`);

```

#### Scope
###### An example illustrating variable scope in JavaScript.

```javascript
// Global scope
let globalVar = "I am global";

function exampleFunction() {
  // Function scope
  let localVar = "I am local";
  console.log(localVar); // Accessible here
  console.log(globalVar); // Accessible here
}

exampleFunction();

console.log(localVar); // Error: localVar is not defined
console.log(globalVar); // Accessible here

if (true) {
  // Block scope
  let blockVar = "I am inside a block";
  console.log(blockVar); // Accessible here
}

console.log(blockVar); // Error: blockVar is not defined

```


#### Object

#### Object Literals and Dynamic Property Management

###### Object literals create structured data. Dot notation easily adds/modifies properties. Combined, they empower flexible and dynamic object management.


```javascript

// Creating an object using object literal notation
var car = {
    brand: "Toyota",
    model: "Camry",
    year: 2022
};

// Adding a new property using dot notation
car.color = "Blue";

// Modifying an existing property using dot notation
car.year = 2023;

// Displaying the updated object
console.log(car); // { brand: 'Toyota', model: 'Camry', year: 2023, color: 'Blue' }


```



#### Utilizing Brackets Notation for Dynamic Object Management

###### Brackets notation offers dynamic key selection and evaluation. Easily create, update, and access object properties. Enhance flexibility with space characters and expressions.

```javascript

// Creating and manipulating objects using the brackets notation

var person = {};
person["name"] = "John";
person["age"] = 30;

var property = "location";
person[property] = "New York";

console.log(person); // {name: 'John', age: 30, location: 'New York'}

// Evaluating expressions within brackets notation

var keys = ['name', 'age', 'location'];
var drone = {
    name: "Skyler",
    age: 2,
    location: "City"
};

for (var i = 0; i < keys.length; i++) {
    console.log(drone[keys[i]]);
}

// Output: 'Skyler', 2, 'City'

```



#### Object Example


```javascript


let output;

const person = {
    name: "Jane Doe",
    age: 24,
    skills: ["Running", "Breathing"],

    address: {
        city: "Istanbul",
        street: "Bahçelievler"
    },

    breatheIn: function(){
        console.log("Taking a breath in...");
    },
    
    breatheOut: function(){
        console.log("Breathing out...");
    }
};

output = person;

output = person.email; 
output = person["name"];
output = person.skills;
output = person.address.city;

person.breatheIn();
person.breatheOut();

// Objects in arrays
const animals = [
    {type: "Chicken", legs: 2},
    {type: "Sheep", legs: 4}
];

value = animals[1].legs;  // Number of legs of the animal at index 1

console.log(value);



```

#### DOM Manipulation


###### The Document Object Model (DOM) serves as a dynamic tool to enhance static web pages. Within this model, there exists a parent-child relationship among HTML elements and their corresponding tags. Element interactions can be manipulated through the use of element IDs.
###### Furthermore, the Window object houses essential properties related to the document and links
#### Document Object



```javascript

let value;

value = document.all;
value = document.all[document.all.length - 1];  // Accessing the last row

const elements = document.all; // HTML collection

for (let i = 0; i < elements.length; i++) {
  console.log(elements[i]);
}

// Conversion to an array is necessary for forEach

const collections = Array.from(document.all);
collections.forEach(function(collection) {
  console.log(collection);
});

value = document.characterSet;  // Retrieve the character set, e.g. utf-8

value = document.scripts.length; // Number of script elements

// Links

value = document.links[2];      // Accessing the 3rd link
value = document.links[0].getAttribute("class");  // Retrieve the class attribute
// Alternatively, use className or classList for accessing classes

// Forms

value = document.forms[2];  
value = document.links["form"];  
value = document.forms[0].getAttribute("name");   // Retrieve the form's name attribute

value = document.forms[0].method;  




```

#### Elements



```javascript


let element;

element = document.getElementById("todo-form");  // Select by ID
element = document.getElementsByClassName("list-group-item")[0]; // Select by class (returns an array)
element = document.getElementsByTagName("div"); // Select all div elements

element = document.querySelector("#todo-form");  // Select by ID
element = document.querySelector(".list-group-item");  // Select by class

// Selecting multiple elements
element = document.querySelectorAll(".list-group-item"); 

element.forEach(function(el){
  console.log(el);
});

// Accessing properties
console.log(element.id);  
console.log(element.classList[1]);  

// Viewing the element's style
console.log(element.style);

// Changing CSS properties
element.className = "btn btn-primary";
element.style.color = "#000";
element.href = "http...";
element.target = "_blank";
element.textContent = "Delete";
element.innerHTML = "<span style='color:red'>Delete</span>";

// Applying styles to elements with the same class
elements = document.querySelectorAll(".list-group-item");
elements.forEach(function(el) {
  el.style.color = "red";
  el.style.background = "white";
});

// Selecting specific list items
let element2 = document.querySelector("li:nth-child(2)");


```

#### Navigating DOM Elements



```javascript

let value;
const todoList = document.querySelector(".list-group");
const todo = document.querySelector(".list-group-item:nth-child(odd)");
const cardRow = document.querySelector(".card.row");

value = todoList; // All li elements are selected
value = todo;     // The selected li element is retrieved
value = cardRow;  // Elements with the "card" and "row" class are selected

value = todoList.childNodes;  // Retrieves text nodes

value = todoList.children;    // Retrieves only element nodes, excluding text nodes

// Accessing nested children
value = cardRow.children[2].children[1].textContent = "XXXX"; 

value = todoList.lastElementChild; 
value = todoList.children.length;
value = todoList.childElementCount;

// Accessing the parent's parent
value = cardRow.parentElement.parentElement;

// Accessing the previous sibling
value = todo.previousElementSibling;   



```
#### Dynamic Element

###### Dynamic Element Addition, Removal, and Modification


```javascript

// ADDITION

// In the HTML page: under card header, there are 2 card bodies.
// <a id="clear-todos" class="btn btn-dark" href="#">xx</a>

const newLink = document.createElement("a");
const cardBody = document.getElementsByClassName("card-body")[1];
newLink.id = "clear-todos";
newLink.href = "https....";
newLink.target = "_blank"; // Opens in a new tab
newLink.textContent = "xxxx"; // Unsafe for production

// Text Nodes - added as children at the desired location

const text = document.createTextNode("xxxxx");
cardBody.appendChild(text);

newLink.appendChild(document.createTextNode("Go to a Different Page"));
cardBody.appendChild(newLink);

// REMOVAL
const todoList = document.querySelector("ul.list-group");
const todos = document.querySelectorAll("li.list-group-item");

todos[0].remove();

// Remove child
todoList.removeChild(todoList.lastElementChild);

// MODIFICATION
const cardBody = document.querySelectorAll(".card-body")[1];

const newElement = document.createElement("h3");
newElement.className = "card-title"; // Other attributes can also be added

cardBody.replaceChild(newElement, oldElement);


```

#### Dynamic Attributes



```javascript

const todoInput = document.getElementById("todo");
let element;
element = todoInput.placeholder; // 1.
element = todoInput.getAttribute("placeholder"); // 2

todoInput.setAttribute("placeholder", "xxxxx");

todoInput.setAttribute("title", "Input");

todoInput.removeAttribute("name");


```

#### Event Listeners and Objects


```javascript

const filter = document.getElementById("filter");
filter.onFocus = function() {
  console.log("xxxx");
}

filter.addEventListener("focus", function(e) {
  console.log(e);
  // e.type
  // e.target.className, and other event details can be accessed.

  const todoForm = document.getElementById("todo-form");

  todoForm.addEventListener("submit", submitForm);

  function submitForm(e) {
    console.log("Submit Event");
    e.preventDefault();

    // Further actions related to form submission
  }
});

```
#### Error Handling
#### Handling Common JavaScript Error Types

```javascript

// ReferenceError Example
try {
    console.log(nonExistentVariable); // Throws ReferenceError
} catch (error) {
    console.error("ReferenceError:", error.message);
}

// SyntaxError Example
try {
    var x = "invalid syntax" // Missing semicolon
} catch (error) {
    console.error("SyntaxError:", error.message);
}

// TypeError Example
try {
    const num = 42;
    num.toUpperCase(); // Throws TypeError
} catch (error) {
    console.error("TypeError:", error.message);
}

// RangeError Example
try {
    const arr = new Array(-1); // Throws RangeError
} catch (error) {
    console.error("RangeError:", error.message);
}

```

#### Using the throws Statement for Custom Errors in JavaScript



```javascript

function validateAge(age) {
    if (typeof age !== 'number' || age < 0) {
        throw new Error("Invalid age value: Age must be a non-negative number.");
    }
    if (age < 18) {
        throw new Error("Underage: You must be at least 18 years old.");
    }
    return "Age is valid.";
}

try {
    const userAge = 15;
    const validationResult = validateAge(userAge);
    console.log(validationResult); // Throws "Underage" error
} catch (error) {
    console.error("Error:", error.message);
}

```

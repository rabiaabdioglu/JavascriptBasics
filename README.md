- [Javascript Basics](#javascript-basics)
  - [Data Types](#data-types)
  - [Var Let Const](#var-let-const)
  - [Data Type Conversions](#data-type-conversions)
  - [Loops](#loops)
  - [Math](#math)
  - [String](#string)
  - [Template Literals](#template-literals)
  - [Array](#array)
  - [Function](#function)
- [Advanced Javascript Features](#advanced-javascript-features)
  - [Scope](#scope)
  - [Object](#object)
  - [Error Handling](#error-handling)
  - [Object Oriented Programming](#object-oriented-programming)
  - [Array Iteration](#array-iteration)
  - [Spread Operator](#spread-operator)
- [JavaScript in Browser](#javascript-in-browser)
  - [DOM Manipulation](#dom-manipulation)
  - [JavaScript Interactivity](#javascript-interactivity)
  - [Elements](#elements)
  - [DOM Element Selection](#dom-element-selection)
  - [Dynamic Element](#dynamic-element)
  - [Dynamic Attributes](#dynamic-attributes)
  - [Event Listeners and Objects](#event-listeners-and-objects)
  - [JSON](#json)
  - [XML](#xml)


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

value = String([1, 2, 3, 4]);     // Convert to string
value = (10).toString();

value = Number([1, 2, 3, 4]);     // Convert to number

value = parseFloat("3.14");       // Convert to float
  
value = parseInt("3");            // Convert to integer

value = Boolean(0);               // Convert to boolean


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

value = Math.PI;              // value is assigned to the constant pi (π)
value = Math.E;               // value is assigned to the base of the natural logarithm (e)

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

#### Template Literals


```javascript

const item = "Apples";
const quantity = 5;
const pricePerUnit = 1.5;

// Using template literals for a more complex string
const invoice = `
    Item: ${item}
    Quantity: ${quantity}
    Total Price: $${quantity * pricePerUnit}
`;

console.log(invoice);

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
## Advanced Javascript Features

#### Object Oriented Programming
###### Constructor

```javascript

class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log(`Hi, I'm ${this.name} and I'm ${this.age} years old.`);
  }
}

const person1 = new Person("Alice", 30);
const person2 = new Person("Bob", 25);

person1.introduce(); // Çıktı: Hi, I'm Alice and I'm 30 years old.
person2.introduce(); // Çıktı: Hi, I'm Bob and I'm 25 years old.

```

###### Inheritance

```javascript
// Base class
class Shape {
  constructor(name) {
    this.name = name;
  }

  calculateArea() {
    console.log(`Calculating area of ${this.name}`);
  }
}

// Derived class
class Circle extends Shape {
  constructor(name, radius) {
    super(name);
    this.radius = radius;
  }

  calculateArea() {
    const area = Math.PI * this.radius ** 2;
    console.log(`Area of ${this.name} (Circle) is ${area.toFixed(2)}`);
  }
}

class Rectangle extends Shape {
  constructor(name, width, height) {
    super(name);
    this.width = width;
    this.height = height;
  }

  calculateArea() {
    const area = this.width * this.height;
    console.log(`Area of ${this.name} (Rectangle) is ${area}`);
  }
}

// Creating instances of derived classes
const circle = new Circle("Circle", 5);
const rectangle = new Rectangle("Rectangle", 4, 6);

// Calling the calculateArea method on instances
circle.calculateArea(); // Output: Area of Circle (Circle) is 78.54
rectangle.calculateArea(); // Output: Area of Rectangle (Rectangle) is 24

```

#### Array Iteration

###### For in Loops
###### The for...in loop is used to iterate over the properties of an object or the indices of an array. In each iteration, the loop variable represents the property names of the specified object or the indices of the array

```javascript
const person = {
    name: "Alice",
    age: 28,
    profession: "engineer"
};

for (const key in person) {
    console.log(key + ": " + person[key]);
}
// Output: name: Alice   age: 28   profession: engineer


```
###### For of Loops
###### The for...of loop is used to iterate over an iterable object, such as an array or any other iterable. In each iteration, the loop variable takes on the values of the elements in the specified iterable.

```javascript
const student = {
    name: "John",
    age: 20,
    grade: "A"
};

for (const key in student) {
    console.log(`${key}: ${student[key]}`);
}

```
###### for...of loop is typically used with arrays to iterate over their values directly. When working with objects, the for...in loop is more commonly used to iterate over keys.
###### However, if you want to iterate over the values of an object, you can combine Object.keys() or Object.values() with a for...of loop.


```javascript

const student = {
    name: "John",
    age: 20,
    grade: "A"
};

for (const value of Object.values(student)) {
    console.log(value);
}

```

###### Built-in methods
###### The Object.keys() method örneği

```javascript
const student = {
    name: "John",
    age: 20,
    grade: "A"
};

const keys = Object.keys(student);

for (const key of keys) {
    console.log(`${key}: ${student[key]}`);
}

```



#### Data Structures

###### forEach
###### The forEach method is used to iterate over elements in an array and apply a function to each element.


```javascript

const numbers = [1, 2, 3, 4, 5];
numbers.forEach((number) => {
  console.log(number * 2);
});


```
###### Filter
###### The filter method creates a new array with all elements that pass the test implemented by the provided function.


```javascript

const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter((number) => number % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]


```

###### Map
###### A Map is a collection of key-value pairs where keys can be of any data type.

```javascript

const fruitMap = new Map();
fruitMap.set('apple', 5);
fruitMap.set('banana', 3);
console.log(fruitMap.get('apple')); // Output: 5

```
###### Set
###### A Set is a collection of unique values.

```javascript

const uniqueNumbers = new Set([1, 2, 3, 2, 4, 4]);
console.log(uniqueNumbers); // Output: Set { 1, 2, 3, 4 }

```

###### Stack
###### A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle.


```javascript

const stack = [];
stack.push('apple');
stack.push('banana');
console.log(stack.pop()); // Output: 'banana'


```

###### Queue
###### A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle.


```javascript

const queue = [];
queue.push('apple');
queue.push('banana');
console.log(queue.shift()); // Output: 'apple'


```

###### Linked List
###### A linked list is a linear data structure where elements are stored in nodes, and each node points to the next node.


```javascript

class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}
const node1 = new Node('apple');
const node2 = new Node('banana');
node1.next = node2;


```
###### Tree
###### A tree is a hierarchical data structure consisting of nodes connected by edges. Each node has a parent and zero or more children.



```javascript

class TreeNode {
  constructor(value) {
    this.value = value;
    this.children = [];
  }
}
const root = new TreeNode('root');
const child1 = new TreeNode('child1');
const child2 = new TreeNode('child2');
root.children.push(child1, child2);


```

#### Spread Operator
###### The spread operator is a versatile feature in JavaScript that provides a concise and powerful way to work with arrays and objects. It allows us to easily manipulate and combine data, making our code more efficient and readable.


###### 1- Combining Arrays


```javascript

const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combinedArray = [...arr1, ...arr2];
console.log(combinedArray); // Output: [1, 2, 3, 4, 5, 6]

```
###### 2- Copying Arrays


```javascript

const originalArray = [10, 20, 30];
const copiedArray = [...originalArray];
console.log(copiedArray); // Output: [10, 20, 30]


```

###### 3- Adding Elements to an Array

```javascript

const numbers = [2, 4, 6];
const newNumbers = [...numbers, 8, 10];
console.log(newNumbers); // Output: [2, 4, 6, 8, 10]

```


###### 4- Function Arguments

```javascript

function add(a, b, c) {
  return a + b + c;
}
const numbers = [5, 10, 15];
const sum = add(...numbers);
console.log(sum); // Output: 30

```


###### 5- Merging Objects



```javascript

const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const mergedObject = { ...obj1, ...obj2 };
console.log(mergedObject); // Output: { a: 1, b: 2, c: 3, d: 4 }

```


###### 6- Rest Parameters (Summing)



```javascript

function sum(...numbers) {
  return numbers.reduce((total, number) => total + number, 0);
}
const result = sum(3, 6, 9, 12);
console.log(result); // Output: 30

```


## JavaScript in Browser


#### DOM Manipulation


###### The Document Object Model (DOM) serves as a dynamic tool to enhance static web pages. Within this model, there exists a parent-child relationship among HTML elements and their corresponding tags. Element interactions can be manipulated through the use of element IDs.
###### Furthermore, the Window object houses essential properties related to the document and links
#### Document Object



```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Manipulation Example</title>
</head>
<body>
    <h1 id="main-heading">Welcome to DOM Manipulation</h1>
    <button id="change-color-button">Change Color</button>
    <div id="output"></div>

    <script>
        // Selecting elements
        const mainHeading = document.getElementById('main-heading');
        const changeColorButton = document.getElementById('change-color-button');
        const outputDiv = document.getElementById('output');

        // Changing color on button click
        const colors = ['red', 'blue', 'green', 'orange', 'purple'];
        let colorIndex = 0;

        changeColorButton.addEventListener('click', () => {
            mainHeading.style.color = colors[colorIndex];
            colorIndex = (colorIndex + 1) % colors.length;
        });

        // Creating and appending new elements
        const newParagraph = document.createElement('p');
        newParagraph.textContent = 'This is a dynamically added paragraph.';
        newParagraph.style.fontWeight = 'bold';
        outputDiv.appendChild(newParagraph);

        const newLink = document.createElement('a');
        newLink.textContent = 'Click me';
        newLink.href = 'https://www.example.com';
        outputDiv.appendChild(newLink);
    </script>
</body>
</html>


```
#### JavaScript Interactivity

###### JavaScript interactivity greatly enhances the user experience by enabling dynamic content updates, real-time feedback, and user-driven actions on web pages. It plays a crucial role in creating modern and interactive web applications

#### Elements 
###### JavaScript allows you to define event handlers that respond to user actions such as clicks, mouse movements, keyboard input, and more

```javascript
const button = document.getElementById('myButton');

button.addEventListener('click', () => {
    alert('Button clicked!');
});

```


#### Form Handling
###### You can use JavaScript to validate form input, submit forms, and provide real-time feedback to users

```javascript

const form = document.getElementById('myForm');

form.addEventListener('submit', (event) => {
    const inputValue = document.getElementById('inputField').value;
    if (inputValue === '') {
        event.preventDefault();
        alert('Please enter a value.');
    }
});

```

#### Dynamic Content
###### JavaScript enables you to modify the content of a web page dynamically without requiring a full page reload


```javascript

const button = document.getElementById('changeTextButton');
const output = document.getElementById('output');

button.addEventListener('click', () => {
    output.textContent = 'New text content';
});


```

#### Animations
###### JavaScript can be used to create animations and transitions to enhance the visual experience of a web page.



```javascript

const element = document.getElementById('animatedElement');

element.addEventListener('click', () => {
    element.style.animation = 'bounce 1s ease-in-out';
});



```

#### AJAX and Fetch
###### JavaScript allows you to make asynchronous requests to a server and update the page with the retrieved data.


```javascript

fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => {
        const output = document.getElementById('output');
        output.textContent = data.message;
    });

```

#### DOM Element Selection 



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



#### JSON


```javascript



// JSON data
const jsonData = {
  employee: {
    name: "Alice",
    age: 28,
    department: "Marketing"
  }
};

// Convert JSON data to a string
const jsonString = JSON.stringify(jsonData);

// Parse and use JSON data
const parsedData = JSON.parse(jsonString);
console.log(`Employee: ${parsedData.employee.name}`);
console.log(`Age: ${parsedData.employee.age}`);
console.log(`Department: ${parsedData.employee.department}`);


```



#### XML


```javascript

// XML data
const xmlData = `
<employee>
  <name>Alice</name>
  <age>28</age>
  <department>Marketing</department>
</employee>
`;

// Parse and use XML data
const parser = new DOMParser();
const xmlDoc = parser.parseFromString(xmlData, "text/xml");

const nameElement = xmlDoc.querySelector("name");
const ageElement = xmlDoc.querySelector("age");
const departmentElement = xmlDoc.querySelector("department");

console.log(`Employee: ${nameElement.textContent}`);
console.log(`Age: ${ageElement.textContent}`);
console.log(`Department: ${departmentElement.textContent}`);


```



#### JSON


```javascript



# JavaScript Essentials

---

## 01: Memory Management in JavaScript

### Primitive and Non-Primitive Types
- **Primitive Data Types**: Stored in the **Stack**. Values are copied when assigned or passed.
    - Examples: `String`, `Number`, `Boolean`, `null`, `undefined`, `Symbol`, `BigInt`.
- **Non-Primitive Data Types**: Stored in the **Heap**. References are passed, not the actual data.
    - Examples: `Object`, `Array`, `Function`.

### Example:
```javascript
let myYtName = "codewithbeluga";
let anotherName = myYtName;
anotherName = "anotherChannel";

console.log(myYtName);    // "codewithbeluga"
console.log(anotherName);  // "anotherChannel"
```

---

## 02: Strings in JavaScript

### String Declarations:
- Traditional: `'single quotes'`, `"double quotes"`.
- Modern: **Template Literals** using backticks `` ` `` for string interpolation.

### Example:
```javascript
const name = "Alok";
const repoCount = 10;

console.log(`My name is ${name} and I have ${repoCount} repos in my GitHub.`);
```

### String Object & Methods:
```javascript
const gameName = new String('alok');

console.log(gameName[0]);           // "a"
console.log(gameName.__proto__);    // Shows the prototype of the String object
```

### Common String Methods:
- `length()`: Returns the length of the string.
- `toUpperCase()`: Converts to uppercase.
- `toLowerCase()`: Converts to lowercase.
- `charAt(index)`: Returns character at specified index.
- `indexOf(substring)`: Returns the index of the first occurrence of substring.
- `substring(start, end)`: Extracts characters between start and end.
- `slice(start, end)`: Similar to substring but can take negative indices.
- `trim()`: Removes whitespace from both ends.
- `replace(oldValue, newValue)`: Replaces occurrences of a substring.
- `includes(substring)`: Checks if the string contains the substring.
- `split(delimiter)`: Splits string into an array based on the delimiter.

---

## 03: Numbers & Math in JavaScript

### Number Declarations:
```javascript
const score = 400;
const balance = new Number(100);
```

### Number Methods:
- `toString()`: Converts number to string.
- `toFixed(decimalPlaces)`: Formats number to a fixed number of decimal places.
- `toPrecision(significantDigits)`: Formats to specified significant digits.
- `toLocaleString(locale)`: Converts to a string with local formatting.

### Math Object:
```javascript
Math.abs(-4);        // 4
Math.round(4.3);     // 4
Math.ceil(4.2);      // 5
Math.floor(4.9);     // 4
Math.min(4, 7, 2.9); // 2.9
Math.max(2, 9, 1, 5);// 9
Math.random();       // Random number between 0 and 1
```

### Random Number Generation:
```javascript
const min = 10;
const max = 20;
console.log(Math.floor(Math.random() * (max - min + 1)) + min); // Random number between 10 and 20
```

---

## 04: Dates in JavaScript

### Date Declarations:
```javascript
let myDate = new Date();
console.log(myDate.toString());      // Full date string
console.log(myDate.toDateString());  // Date part only
console.log(myDate.toLocaleString()); // Localized date and time string
console.log(typeof myDate);          // "object"
```

### Creating Dates:
```javascript
let myCreatedDate = new Date(2023, 0, 23); // January 23, 2023
let anotherDate = new Date("2023-01-14");  // January 14, 2023 (ISO format)
```

### Date Methods:
```javascript
let myTimeStamp = Date.now();  // Current timestamp in milliseconds

let newDate = new Date();
console.log(newDate.toLocaleString()); // Localized string of the current date and time
```

---

## 05: Arrays in JavaScript

### Array Declarations:
```javascript
const myArr = [0, 1, 2, 3, 4];
```

### Array Methods:
- `push(value)`: Adds value to the end.
- `pop()`: Removes the last element.
- `unshift(value)`: Adds value to the beginning.
- `shift()`: Removes the first element.
- `includes(value)`: Checks if value exists in the array.
- `indexOf(value)`: Returns the index of the first occurrence of value.
- `join(delimiter)`: Joins array elements into a string.
- `slice(start, end)`: Returns a new array without modifying the original.
- `splice(start, deleteCount, ...items)`: Modifies the array by removing, adding, or replacing elements.

### Example:
```javascript
myArr.push(6);      // [0, 1, 2, 3, 4, 6]
myArr.pop();        // [0, 1, 2, 3, 4]
myArr.unshift(9);   // [9, 0, 1, 2, 3, 4]
myArr.shift();      // [0, 1, 2, 3, 4]
```

### Combining Arrays:
```javascript
const marvelHeroes = ["Thor", "Ironman", "Spiderman"];
const dcHeroes = ["Superman", "Flash", "Batman"];

const allHeroes = marvelHeroes.concat(dcHeroes);
const allNewHeroes = [...marvelHeroes, ...dcHeroes];
```

### Array Flattening:
```javascript
const mixedArray = [1, 2, 3, [4, 5], 6, 7, [6, 7, [4, 5]]];
const flatArray = mixedArray.flat(Infinity);
console.log(flatArray); // Fully flattened array
```

---

## 06: Objects in JavaScript

### Object Declarations:
- Objects can be created using literals, constructors, or `Object.create`.

#### Example:
```javascript
const mySym = Symbol("key1");

const jsUser = {
    name: "Alok",
    age: 18,
    "Full Name": "Alok Thakur",
    email: "alok@google.com",
    location: "Delhi",
    isLoggedIn: false,
    lastLoginDays: ["Monday", "Saturday"],
    [mySym]: "myKey1",
};
```

### Accessing Properties:
```javascript
console.log(jsUser.email);          // Dot notation
console.log(jsUser["email"]);       // Bracket notation
console.log(jsUser["Full Name"]);   // Accessing property with space
console.log(jsUser[mySym]);         // Accessing property with Symbol
```

### Freezing an Object:
```javascript
Object.freeze(jsUser); // Prevents modifications to the object
```

### Adding Methods to Objects:
```javascript
jsUser.greeting = function() {
    console.log("Hello, JS User!");
};

jsUser.greetingTwo = function() {
    console.log(`Hello, JS User, ${this.name}`);
};

jsUser.greeting();    // "Hello, JS User!"
jsUser.greetingTwo(); // "Hello, JS User, Alok"
```

### Object Methods:
- `Object.keys(obj)`: Returns an array of keys.
- `Object.values(obj)`: Returns an array of values.
- `Object.entries(obj)`: Returns an array of key-value pairs.
- `Object.hasOwnProperty(key)`: Checks if the object has the specified property.

### Merging Objects:
```javascript
const obj1 = { a: '23', b: '24' };
const obj2 = { c: '25', d: '26' };

const obj3 = Object.assign({}, obj1, obj2); // Using Object.assign
const obj4 = { ...obj1, ...obj2 };          // Using spread operator
```

### Object Destructuring:
```javascript
const course = {
    courseName: "JS in Hindi",
    price: '499',
    courseInstructor: "Hitesh",
};

const { courseInstructor: instructor } = course;
console.log(instructor); // "Hitesh"
```

---

## 07: Functions in JavaScript

### Function Declaration:
```javascript
function sayMyName() {
    console.log("A");
    console.log("L");
    console.log("O");
    console.log("K");
}

sayMyName(); // Calls the function
```

### Function Parameters & Arguments:
```javascript
function add(a, b) {
    return a + b;
}

const sum = add(3, 4); // a and b are parameters, 3 and 4 are arguments
console.log(sum);      // 7
```

### Rest Operator (`...`):
```javascript
function calCartPrice(...num1) {
    return num1;
}

console.log(calCartPrice(20, 30, 40)); // [20, 30, 40]
```

### Functions with Objects:
```javascript
const jsUser = {
    name: "Alok",
    greet() {
        console.log(`Hello, ${this

.name}`);
    }
};

jsUser.greet(); // "Hello, Alok"
```

### Scope and Hoisting:
- Variables and functions declared with `var` are hoisted.
- `let` and `const` are block-scoped and not hoisted.

### Arrow Functions:
```javascript
const greet = () => {
    console.log("Hello, JS!");
};

greet(); // "Hello, JS!"
```

---

### Summary:
This guide covers the basics of memory management, strings, numbers, dates, arrays, objects, and functions in JavaScript, with modern syntax and best practices.
```
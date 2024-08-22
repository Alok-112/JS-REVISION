
# JavaScript in One Shot

---

## 04: Let, Var, & Const

### Understanding Variable Declarations

- **`let`**: Block-scoped variable declaration.
- **`var`**: Function-scoped variable declaration.
- **`const`**: Block-scoped constant declaration, value cannot be reassigned.

### Example:
```javascript
const accountId = 12345;
let accountEmail = "abc@gmail.com";
var accountPassword = "12345";
accountCity = "Delhi"; // implicit global declaration due to missing keyword

console.table([accountId, accountEmail, accountPassword, accountCity]);
```

### Scope:
```javascript
{
    let blockScoped = "I am block scoped!";
    var functionScoped = "I am function scoped!";
}

console.log(functionScoped); // accessible
console.log(blockScoped); // error: blockScoped is not defined
```

### `let` vs `var`:

- `var` has **function scope** or **global scope**.
- `let` has **block scope**.

**Note**: Variables declared without a value are initialized with `undefined`.

---

## 05: Data Types and ECMAScript Standards

### ECMAScript Standards:
- `"use strict";`: Ensures that the code is treated as ECMAScript 5 or higher.
- **Code Readability**: Crucial for maintenance and collaboration.
- **ECMA Standard**: Guides the development of JavaScript engines.

### Data Types in JavaScript:

#### Primitive Data Types:
1. `Number`: Example: `2**53` (Safe integer range).
2. `BigInt`: Example: `const bigNumber = 15616516586418948n;`.
3. `String`: Example: `"Hello"`.
4. `Boolean`: Example: `true` or `false`.
5. `null`: Represents the absence of any object value.
6. `undefined`: Variable declared but not assigned.
7. `Symbol`: Unique identifier. Example: `const id = Symbol('123');`.

#### Non-Primitive (Reference) Data Types:
1. `Object`: Example: `let myObj = { name: "Alok", age: 20 };`.
2. `Array`: Example: `const heroes = ["Superman", "Batman"];`.
3. `Function`: Example: `const myFunction = function() { console.log("Hello!"); }`.
4. `typeof()`: To check the data type. Example: `typeof "Hello" // returns "string"`.

---

## 06: Data Type Conversion

### Number Conversion:
- `"33"` -> `33`
- `"33abc"` -> `NaN`
- `true` -> `1`
- `false` -> `0`

### Boolean Conversion:
- `1` -> `true`
- `0` -> `false`
- `""` -> `false`
- `"Alok"` -> `true`

### String Conversion:
- `33` -> `"33"`

**Investigation Study**: Check these conversions on your own.

---

## 07: Operators and Precedence

### Operator Precedence:
- **Prefix**: Operators before the operand.
- **Postfix**: Operators after the operand.

---

## 08: Comparison

Understanding comparison operators and their precedence is key to avoiding unexpected results in your code.

---

## 09: Objects & Web Events

### Data Types Summary:
- **Primitive (7 types)**: Call by value.
    - String, Number, Boolean, null, undefined, Symbol, BigInt.
- **Non-Primitive (Reference)**: Call by reference.
    - Array, Object, Function.

---

## 10: Memory & Threads in JavaScript

### Memory Management:
- **C/C++**: Manual memory management.
- **JavaScript**: Automatic memory management.

### Memory Types:
- **Stack**: Stores primitive data types (copy of the original value).
- **Heap**: Stores non-primitive data types (reference to the original value).

### Example:
```javascript
let myName = "alok";
let difName = myName;
difName = "thakur";

console.log(difName);  // "thakur"
console.log(myName);   // "alok"

let userOne = { email: "a@gmail.com", upi: "athakur@fam" };
let userTwo = userOne;
userTwo.email = "b@gmail.com";

console.log(userOne.email);  // "b@gmail.com"
console.log(userTwo.email);  // "b@gmail.com"
```

---

## 11: Strings in JavaScript

### String Operations:
```javascript
const name = "alok";
const repoCount = 17;

console.log(`My name is ${name} and my repo count is ${repoCount}`);

console.log(name[0]);          // "a"
console.log(name.length);      // 4
console.log(name.toUpperCase());  // "ALOK"
console.log(name.charAt(2));   // "o"
console.log(name.indexOf('a')); // 0
```

### Substring, Slice, and Trimming:
```javascript
const gameName = 'BattleGroundsMobilesIndia';
console.log(gameName.substring(0, 6));   // "Battle"
console.log(gameName.slice(20, 26));     // "India"

const newStringOne = "    akm     ";
console.log(newStringOne.trim());        // "akm"
```

### String Replacement and Splitting:
```javascript
const url = 'https://alok.com/alok%20thakur';
console.log(url.replace('%20', '-')); // "https://alok.com/alok-thakur"
console.log(url.includes('alok'));    // true

const newStringTwo = 'alok-ranjan-thakur';
console.log(newStringTwo.split('-')); // ["alok", "ranjan", "thakur"]
```

---

## 12: Numbers & Math

### Number Operations:
```javascript
const score = 400;
const balance = new Number(100);

console.table(score);
console.log(balance.toString());        // "100"
console.log(balance.toString().length); // 3
console.log(balance.toFixed(2));        // "100.00"

const otherNum = 23.8745;
console.log(otherNum.toPrecision(2));   // "24"
```

### Math Operations:
```javascript
console.log(Math.abs(-4));        // 4
console.log(Math.round(4.3));     // 4
console.log(Math.ceil(4.2));      // 5
console.log(Math.floor(4.9));     // 4
console.log(Math.min(4, 7, 2.9)); // 2.9
console.log(Math.max(2, 9, 1, 5)); // 9
console.log(Math.random());        // random number between 0 and 1

const min = 10;
const max = 20;
console.log(Math.floor(Math.random() * (max - min + 1) + min)); // random number between 10 and 20
```

---

## 13: Date & Time in JavaScript

### Date Operations:
```javascript
let myDate = new Date();
console.log(myDate.toString());      // "Thu Aug 22 2024 12:00:00 GMT+0530 (India Standard Time)"
console.log(myDate.toDateString());  // "Thu Aug 22 2024"
console.log(myDate.toISOString());   // "2024-08-22T06:30:00.000Z"
console.log(myDate.toLocaleString()); // "8/22/2024, 12:00:00 PM"

let myCreatedDate = new Date(2024, 0, 22);
console.log(myCreatedDate.toDateString()); // "Mon Jan 22 2024"
```

### Timestamp and Date Manipulations:
```javascript
let myTimeStamp = Date.now(); // current timestamp in milliseconds
console.log(Math.floor(Date.now() / 1000)); // current timestamp in seconds

let newDate = new Date();
console.log(newDate.getMonth() + 1); // current month
console.log(newDate.getDay());       // day of the week (0-6)
```

---

## 14: Arrays in JavaScript

### Array Declarations:
```javascript
const myArr = [0, 1, 2, 3, 4, 5];
const myAnimes = ["One-Punch-Man", "One-Piece", "Naruto"];
const myArr2 = new Array(1, 2, 3, 4);

console.log(myArr[0]); // 0
```

### Array Methods:
```javascript
myArr.push(6);    // adds 6 to the end
myArr.pop();      // removes the last element
myArr.unshift(9); // adds 9 to the start
myArr.shift();    // removes the first element

console.log(myArr.includes(9));  // true
console.log(myArr.indexOf(9));   // index of 9 in the array
```

### Array Slicing and Splicing:
```javascript
const myn1 = myArr.slice(1, 3); // creates a new array, does not modify original
console.log(myn1);

const myn2 = myArr.splice(1, 3); // modifies the original array
console.log(myn2);
```

---

## 15: Arrays Part 2

### Combining Arrays:
```javascript
const marvel_heroes = ["Thor", "Ironman", "Spiderman"];
const dc_heroes = ["Superman", "Flash", "Batman"];

const all

Heroes = marvel_heroes.concat(dc_heroes);
console.log(allHeroes);

const all_new_heroes = [...marvel_heroes, ...dc_heroes];
console.log(all_new_heroes);
```

### Array Flattening:
```javascript
const arr = [1, 2, [3, 4, [5, 6, [7, 8]]]];
const newArray = arr.flat(Infinity);
console.log(newArray);
```

### Iterating Over Arrays:
```javascript
console.log(marvel_heroes);

marvel_heroes.forEach((hero) => {
  console.log(hero.toUpperCase());
});
```

### Map, Filter, Reduce:
```javascript
const herosWithPower = marvel_heroes.map((hero) => `${hero} has power!`);
console.log(herosWithPower);

const scores = [10, 20, 30, 40];
const gt20 = scores.filter((score) => score > 20);
console.log(gt20);

const totalScore = scores.reduce((accumulator, score) => accumulator + score, 0);
console.log(totalScore);
```
```
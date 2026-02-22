# JavaScript and TypeScript Basics

Welcome to this introductory lesson on JavaScript and TypeScript. In this session, you will learn key concepts that form the foundation of modern web development. We will cover variable declarations, naming conventions, data types, operators, and more, with practical examples and exercises to solidify your understanding.

---

## What You'll Learn

- Variable Declarations (`var`, `let`, `const`) and their differences.
- Best practices for naming variables.
- Data types and their use cases.
- Operators and their applications.
- Conditional statements and loops.
- Objects and Arrays.
- How TypeScript enhances JavaScript with types.

---

## Setting Up Your Environment

To follow along and practice, we will set up a project using the Vite `vanilla-ts` template. Below are the steps to guide you in creating and running your project:

1. **Install Node.js**: Ensure Node.js is installed on your system. You can download it from [nodejs.org](https://nodejs.org).
2. **Create a Vite Project**:
   ```bash
   npm create vite@latest my-js-ts-project --template vanilla-ts
   cd my-js-ts-project
   npm install
   npm run dev
   ```
3. Open the project in your favorite code editor (e.g., VSCode).

---

## Variable Declarations

### JavaScript Variables

JavaScript variables are containers for storing data values. There are three ways to declare variables:

- `var` (function-scoped)
- `let` (block-scoped)
- `const` (block-scoped, immutable)

### Key Differences

#### Example 1: Scope

```javascript
    var tester = "hey hi";

    function newFunction() {
        var hello = "hello";
    }
    // console.log(tester); 
    console.log(hello); 
```

```javascript
function testVar() {
   if (true) {
      var x = 10; 
   }
   console.log(x); 
}

testVar();

function testLet() {
   if (true) {
      let y = 20; 
   }
   console.log(y); 
}

testLet();
```

#### Example 2: Re-declaration and Re-assignment

```javascript
var a = 5;
var a = 10; 

let b = 5;


const c = 5;

```

### Tricky Questions

1. What will the following code output, and why?

   ```javascript
    var a = 1;
    let b = 2;
    const c = 3;
    
    {
    var a = 4;
    let b = 5;
    const c = 6;
    console.log(a, b, c); 
    }
    console.log(a, b, c); 
   ```
   
      ```javascript
    var x = 10;
    var x = 20; 
   ```

2. What happens here?

   ```javascript
    let y = 30;
    let y = 40; 
   ```

3. Can you reassign a `const` variable if it’s an object?

   ```javascript
   const obj = { name: "John" };
   obj.name = "Doe";
   console.log(obj.name); 
   ```

---

## Nomenclature

### Rules for Naming Variables

- Use `lowerCamelCase` for variables.
- Variable names can begin with a letter, `_`, or `$`.
- Avoid reserved keywords.

#### Examples

```javascript
let userName = "John"; 
let _privateVar = 42;  
let $jQueryVar = "selector"; 
```

### Tricky Questions

1. Why would someone use `_` to start a variable?
2. Why might a developer use `$` at the beginning of a variable name?

---

## Data Types

JavaScript has dynamic types, but TypeScript allows you to specify types for safety and clarity.

### Primitive Data Types

- `string`
- `number`
- `boolean`
- `null`
- `undefined`

#### Example

```typescript
let message: string = "Hello, World!";
let count: number = 42;
let isValid: boolean = true;
```

### Tricky Questions

1. What will the following code output?

   ```javascript
   console.log(typeof null); 
   console.log(typeof undefined); 
   ```

2. Predict the type of `NaN` in JavaScript:

   ```javascript
   console.log(typeof NaN); 
   ```

---

## Operators

### Comparison Operators

These compare two values and return a boolean result.

#### Examples

```javascript
console.log(5 == "5");  
console.log(5 === "5"); 
console.log(10 > 5);     
console.log(10 <= 10);   


```

### Logical Operators

These combine multiple conditions.

#### Examples

```javascript
console.log(true && false); 
console.log(true || false); 
console.log(!true);         
```

### Tricky Questions

1. What will the various code outputs?

   ```javascript
   console.log(0 == false);  
   console.log(0 === false); 
   ```
   
    ```javascript
    let a = 5;
    let b = "5";
    a = b == a;
    console.log(a);
   ```
   
    ```javascript
    let result = null ?? "default";
    console.log(result);
    
    result = undefined ?? "default";
    console.log(result);
    
    result = 0 ?? "default";
    console.log(result);
   ```   
   
    ```javascript
    let x = 5;
    console.log(x++);
    console.log(++x);
   ```

2. Evaluate this expression:

   ```javascript
   console.log(1 && 0 || 2); 
   ```

---

## Conditional Statements and Loops

### Conditional Statements

#### Example: if-else

```javascript
let age = 18;
if (age >= 18) {
   console.log("You are an adult.");
} else {
   console.log("You are a minor.");
}
```

### Loops

#### Example: for Loop

```javascript
for (let i = 0; i < 5; i++) {
   console.log(i);
}
```

---

## Objects

### JavaScript Objects

Objects are collections of key-value pairs.

#### Example

```javascript
const person = {
   name: "Alice",
   age: 25,
   greet: function() {
      console.log("Hello, " + this.name);
   }
};

person.greet();
```

#### Tricky Questions

1. Can you add properties to an object declared with `const`?
2. What happens when you try to access a property that doesn’t exist?

---

## Arrays

### JavaScript Arrays

Arrays store ordered collections of values.

#### Example

```javascript
const fruits = ["apple", "banana", "cherry"];
fruits.push("date");
console.log(fruits);
```

#### Tricky Questions

1. What happens if you use `delete` on an array element?
2. How can you iterate over an array efficiently?

---

## Exercises

### **Classwork**

#### **1. Data Types and TypeScript**
Write a function that:

1. **Accepts multiple inputs** of types `string`, `number`, `boolean`, `null`, `undefined`, and `NaN`.
2. **Converts these inputs** into a specific type (`string` or `number`) based on certain conditions. For instance:
    - If the input is a `string` or `boolean`, convert it to a `number`.
    - If the input is `null` or `undefined`, return a default value of `0`.
    - If the input is `NaN`, handle it gracefully by returning the string "Not a number".
3. **Uses TypeScript features** such as:
    - Type guards (`typeof`, etc.).
    - Type assertions.
4. **Logs the final output** and handles edge cases like `NaN`, `null`, and `undefined` properly. You should include a mechanism to print the result and any potential errors or unexpected behaviors.


#### **2. Complex Operators**
Create a program to:
- Evaluate the result of expressions involving multiple comparison and logical operators (e.g., `(5 > 3) && !(2 < 1)`).
- Predict the behavior of non-boolean values used with logical operators (e.g., `0 && 1 || 2`).

#### **3. Conditions and Loops**
Build a mini-game that:
- Asks the user to guess a random number between 1 and 10.
- Gives hints if the guess is too high or too low.
- Allows a maximum of 3 attempts, after which the game ends.

#### **4. Objects and Arrays**
Write a program to:
- Create an object representing a library book, including properties like `title`, `author`, and `isAvailable`.
- Implement a method to borrow a book, which changes its `isAvailable` status.
- Use an array to manage a collection of books and find a specific book by its title.

## Take-Home Assignment: Create a Student Grading System

### Goal:
Build a program that allows instructors to input student grades, calculate averages, and assign letter grades. This project will involve creating functions, working with objects and arrays, and applying conditional logic.

---

## Requirements:

### 1. Collect Student Data:
- Create a way to input multiple students' details:
   - `name` (string)
   - `scores` (array of numbers for different subjects)

### 2. Calculate Averages:
- Write a function that calculates the average score for each student.

### 3. Assign Letter Grades:
- Create a function that assigns letter grades based on the average score:
   - `90-100`: `A`
   - `80-89`: `B`
   - `70-79`: `C`
   - `60-69`: `D`
   - Below `60`: `F`

### 4. Display Results:
- Print a summary of all students in a tabular format:
   - `Name`, `Scores`, `Average`, `Grade`
- Include an option to display the highest and lowest scores in the class.

### 5. Error Handling:
- Ensure the program validates:
   - Scores are numbers between `0` and `100`.
   - Names are non-empty strings.

---

## Bonus Challenges:
1. Add sorting functionality to display students by:
   - `Name` (alphabetical order)
   - `Grade` (highest to lowest)
   - `Average` score (highest to lowest)
2. Include functionality to update a student’s scores after input.
3. Save the students’ data in local storage or a file (if running in a Node.js environment) so it persists after closing the program.



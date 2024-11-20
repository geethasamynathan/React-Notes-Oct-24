# What is mean destructuring in javascript? When to use ? why to use?
Destructuring in JavaScript is a convenient way to extract values from arrays or properties from objects and assign them to variables. It provides a concise syntax to extract multiple elements or properties from an array or object, respectively, into distinct variables.

# What is Destructuring?
## Array Destructuring Example:

```javascript
const numbers = [1, 2, 3];

// Using destructuring to extract values
const [first, second, third] = numbers;

console.log(first);  // Output: 1
console.log(second); // Output: 2
console.log(third);  // Output: 3
Object Destructuring Example:

javascript
const user = {
  name: 'Alice',
  age: 25,
  city: 'Wonderland'
};

// Using destructuring to extract properties
const { name, age, city } = user;

console.log(name); // Output: Alice
console.log(age);  // Output: 25
console.log(city); // Output: Wonderland
```
## When to Use Destructuring?
Extracting Multiple Values: When you need to extract multiple values from an array or object.

**Function Parameters:** When passing objects as function parameters and you want to extract specific properties.

**Swapping Variables:** When you need to swap values between variables.

**Function Parameters:** When you want to assign default values if the property does not exist.

## Why Use Destructuring?
**Concise Syntax:** Destructuring provides a shorter and cleaner syntax to extract values compared to traditional methods.

**Readability:** Code becomes more readable and easier to understand when you can see the properties or elements being extracted directly.

**Avoiding Repetition:** Destructuring reduces the repetition of accessing properties or elements multiple times.

**Improved Maintainability:** Easier to refactor and maintain code as destructuring allows clear extraction of required values.

## Examples of Destructuring in Different Scenarios
### Function Parameters:

```javascript
function displayUser({ name, age, city }) {
  console.log(`Name: ${name}, Age: ${age}, City: ${city}`);
}

const user = { name: 'Alice', age: 25, city: 'Wonderland' };
displayUser(user); // Output: Name: Alice, Age: 25, City: Wonderland
```
### Swapping Variables:

```javascript
let a = 1;
let b = 2;

// Swapping values using destructuring
[a, b] = [b, a];

console.log(a); // Output: 2
console.log(b); // Output: 1
### Default Values:

```javascript
const settings = { theme: 'dark' };

// Destructuring with default values
const { theme, fontSize = '16px' } = settings;

console.log(theme);   // Output: dark
console.log(fontSize); // Output: 16px (default value)
```
Destructuring is a powerful and flexible feature in JavaScript that enhances code clarity and efficiency. It simplifies the process of extracting values from arrays and objects, making your code more elegant and easier to maintain. 

## what not possible in destructuring in javascript?
While destructuring in JavaScript is a powerful and flexible feature, there are certain limitations and scenarios where it cannot be applied. 
## 1. Destructuring Non-Iterable Values
Destructuring requires the value to be an iterable (for arrays) or an object. Non-iterable values, such as null or undefined, cannot be destructured.

```javascript
const [a, b] = null; // TypeError: null is not iterable
```
## 2. Destructuring a Non-Object
When destructuring objects, the value must be an object. Primitive values like numbers, strings, or booleans cannot be destructured as objects.
```javascript
const { length } = 'hello'; // Works because strings have a length property

const { toFixed } = 123; // TypeError: 123 is not an object
```
### 3. Skipping Nested Properties
Destructuring does not support skipping over nested properties directly. You need to explicitly access the nested structure.
```javascript
const user = {
  name: 'Alice',
  address: {
    city: 'Wonderland',
    country: 'Fiction'
  }
};

const { address: { city } } = user; // Works
const { address: { postalCode } } = user; // Undefined if postalCode is not present
```
## 4. Reassigning Variable Names Without Renaming
Destructuring cannot reassign variables without renaming them. If the variable names are already used, you must rename them using aliasing.
```javascript
const user = { name: 'Alice', age: 25 };
const name = 'Bob';

// Trying to destructure into an existing variable
const { name } = user; // SyntaxError: Identifier 'name' has already been declared

// Using aliasing to avoid conflicts
const { name: userName } = user;
console.log(userName); // Output: Alice
```
### 5. Destructuring into a Variable Declaration with let/const
You cannot destructure into a variable that has already been declared with let or const. You must do it in a separate line.
```javascript
let user = { name: 'Alice', age: 25 };

// Incorrect: destructuring into an already declared variable
let { name, age } = user; // Error

// Correct way
({ name, age } = user); // Note the parentheses
console.log(name, age); // Output: Alice 25
```
### 6. Destructuring with Default Values and Nullish Coalescing
Default values in destructuring only work if the value is undefined. If the property exists but is set to null, the default value will not be used.
```javascript
const user = { name: 'Alice', age: null };

// Default values
const { name, age = 30 } = user;
console.log(name, age); // Output: Alice null (not 30)
```
To use default values in the case of null, you can combine destructuring with the nullish coalescing operator (??).

```javascript
const { name, age } = user;
const adjustedAge = age ?? 30; // Output: 30 if age is null or undefined
console.log(adjustedAge); // Output: 30

```
# Summary
While destructuring is a powerful tool in JavaScript for simplifying code and improving readability, it has certain limitations:

Cannot destructure non-iterable values.

Cannot destructure non-object values.

Cannot skip nested properties without explicit access.

Cannot reassign variables without renaming.

Cannot destructure into already declared variables without additional syntax.

Default values in destructuring do not work with null.
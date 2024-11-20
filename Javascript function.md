# what is functions in javascript

## 1. Normal Function Declaration
**Example:**

```javascript
// Function Declaration
function greet(name) {
  return `Hello, ${name}!`;
}

// Calling the function
console.log(greet("Alice"));  // Output: Hello, Alice!
console.log(greet("Bob"));    // Output: Hello, Bob!
```
## Explanation:
**Function Declaration:** Defined with the function keyword, followed by the function name, parameters, and the function body.

**Calling the Function:** The function is called using its name and passing arguments.

# 2. Immediately Invoked Function Expression (IIFE)
## Example:

```javascript
// IIFE (Immediately Invoked Function Expression)
(function (name) {
  console.log(`Hello, ${name}!`);
})("Alice");
```
# Explanation:
**IIFE:** Defined and executed immediately. Enclosed in parentheses to treat it as an expression and then invoked with another set of parentheses.

**Usage:** Useful for creating a scope to avoid polluting the global namespace.

# 3. Arrow Function
## Example:

```javascript
// Arrow Function
const greet = (name) => {
  return `Hello, ${name}!`;
};

// Calling the function
console.log(greet("Alice"));  // Output: Hello, Alice!
console.log(greet("Bob"));    // Output: Hello, Bob!
```
# Explanation:
**Arrow Function:** Defined using the => syntax. Provides a more concise way to write functions and lexically binds this.

**Calling the Function:** Similar to normal functions, called using the variable name and passing arguments.

# Comparison
## Normal Function Declaration:

**Syntax:** function functionName(params) { ... }

**Advantages:** Hoisted, can be called before declaration.

# IIFE:

**Syntax:** (function(params) { ... })(args);

**Advantages:** Executes immediately, useful for initialization tasks or creating scope.

# Arrow Function:

**Syntax:** const functionName = (params) => { ... };

**Advantages:** Concise syntax, this context is lexically bound, useful in callbacks and functional programming.

# Summary
**Normal Function Declaration:** Standard way to define reusable functions.

**IIFE:** Executes immediately after definition, useful for immediate initialization or creating scope.

**Arrow Function:** Concise and lexically binds this, useful in various modern JavaScript applications.
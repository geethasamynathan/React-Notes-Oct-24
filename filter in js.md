# filter()
The filter() method creates a new array with all elements that pass the test implemented by the provided function.

Example:

```javascript
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(number => number % 2 === 0);
console.log(evenNumbers); 
```

Different example for filter in javascript with basic to advanced lavel with code and explanation.
Basic Example: Filtering Even Numbers
Example:

javascript
// Basic array of numbers
const numbers = [1, 2, 3, 4, 5, 6];

// Filtering even numbers
const evenNumbers = numbers.filter(number => number % 2 === 0);

console.log(evenNumbers); // Output: [2, 4, 6]
Explanation:

Array Definition: const numbers = [1, 2, 3, 4, 5, 6];

Filtering: numbers.filter(number => number % 2 === 0); creates a new array with only the even numbers.

Intermediate Example: Filtering Objects in an Array
Example:

javascript
// Array of objects
const users = [
  { id: 1, name: 'Alice', age: 25 },
  { id: 2, name: 'Bob', age: 30 },
  { id: 3, name: 'Charlie', age: 35 },
];

// Filtering users older than 30
const usersOver30 = users.filter(user => user.age > 30);

console.log(usersOver30); // Output: [ { id: 3, name: 'Charlie', age: 35 } ]
Explanation:

Array Definition: const users = [ ... ]; with objects representing users.

Filtering: users.filter(user => user.age > 30); creates a new array with users older than 30.

Advanced Example: Filtering Nested Objects
Example:

javascript
// Array of objects with nested properties
const products = [
  { id: 1, name: 'Laptop', details: { price: 999, inStock: true } },
  { id: 2, name: 'Phone', details: { price: 599, inStock: false } },
  { id: 3, name: 'Tablet', details: { price: 399, inStock: true } },
];

// Filtering products that are in stock
const inStockProducts = products.filter(product => product.details.inStock);

console.log(inStockProducts); 
// Output: 
// [
//   { id: 1, name: 'Laptop', details: { price: 999, inStock: true } },
//   { id: 3, name: 'Tablet', details: { price: 399, inStock: true } }
// ]
Explanation:

Array Definition: const products = [ ... ]; with nested details objects.

Filtering: products.filter(product => product.details.inStock); creates a new array with products that are in stock.

Real-World Example: Filtering and Displaying Data in React
Example:

javascript
import React from 'react';

const products = [
  { id: 1, name: 'Laptop', price: 999, inStock: true },
  { id: 2, name: 'Phone', price: 599, inStock: false },
  { id: 3, name: 'Tablet', price: 399, inStock: true },
];

function ProductList() {
  const inStockProducts = products.filter(product => product.inStock);

  return (
    <div>
      <h3>In Stock Products</h3>
      <ul>
        {inStockProducts.map(product => (
          <li key={product.id}>
            {product.name} - ${product.price}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ProductList;
Explanation:

Array Definition: The products array contains product objects.

Filtering in React: products.filter(product => product.inStock); filters products that are in stock.

Rendering: The ProductList component maps the filtered array to display each in-stock product.

Advanced Filtering with Multiple Conditions
Example:

javascript
// Array of objects with multiple properties
const students = [
  { id: 1, name: 'Alice', grade: 85, passed: true },
  { id: 2, name: 'Bob', grade: 68, passed: false },
  { id: 3, name: 'Charlie', grade: 95, passed: true },
];

// Filtering students who passed and have a grade above 80
const topStudents = students.filter(student => student.passed && student.grade > 80);

console.log(topStudents); 
// Output: 
// [
//   { id: 1, name: 'Alice', grade: 85, passed: true },
//   { id: 3, name: 'Charlie', grade: 95, passed: true }
// ]
Explanation:

Array Definition: const students = [ ... ]; with properties grade and passed.

Filtering: students.filter(student => student.passed && student.grade > 80); creates a new array with students who passed and have a grade above 80.

Summary
Basic Filtering: Filtering even numbers from an array.

Intermediate Filtering: Filtering objects in an array based on a property.

Advanced Filtering: Filtering nested objects and displaying data in React.

Real-World Example: Filtering and rendering in-stock products in a React component.

Advanced Multiple Conditions: Filtering with multiple conditions in an array of objects.
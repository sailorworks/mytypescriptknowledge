# Functions in javascript:

a function is a block of code designed to perform a particular task. Functions are one of the fundamental building blocks in JavaScript and allow you to write reusable code.

### Declaring a Function

There are several ways to declare a function in JavaScript:

1. **Function Declaration:**
   This is the most common way to define a function. A function declaration starts with the `function` keyword, followed by the name of the function, a list of parameters (enclosed in parentheses), and a block of code (enclosed in curly braces).

   ```javascript
   function sayHello() {
     console.log("Hello, world!");
   }
   ```

   You can call this function using its name:

   ```javascript
   sayHello(); // Output: Hello, world!
   ```

2. **Function Expression:**
   A function expression is when a function is assigned to a variable. This can be anonymous (without a name) or named.

   ```javascript
   const greet = function () {
     console.log("Hello, world!");
   };

   greet(); // Output: Hello, world!
   ```

3. **Arrow Function:**
   Arrow functions are a shorthand for writing functions, introduced in ES6.

   ```javascript
   const add = (a, b) => {
     return a + b;
   };

   console.log(add(2, 3)); // Output: 5
   ```

   For even shorter functions, if the body of the function is a single expression, you can omit the `return` keyword and the curly braces:

   ```javascript
   const multiply = (a, b) => a * b;

   console.log(multiply(2, 3)); // Output: 6
   ```

### arr.forEach(funcCallback)

The forEach() method executes a provided function once for each array element.

example:

```javascript
const numbers = [65, 44, 12, 4];

numbers.forEach(function print(numbers) {
  console.log(numbers);
});

//better version lesser code with arrow functions
const numbers = [65, 44, 12, 4];
numbers.forEach((numbers) => console.log(numbers));
```

Here I've created a function that is wrapped around with "forEach"

### arr.map(funcCallback)

The map() method creates a new array with the results of calling a provided function on every element in the array.

Example:

```Javascript
const numbers = [65, 44, 12, 4];

let panda = numbers.map((val) => {
  return val;
});
console.log(panda);
```

### arr.filter(funcCallback)

The filter() method creates a new array with all elements that pass the test implemented by the provided function.

Example:

```Javascript
const numbers = [65, 44, 12, 4];
let panda = numbers.filter(val => {
    return val > 10;
});
console.log(panda);
```

### arr.reduce(funcCallback)

The reduce() method applies a function against an accumulator and each element in the array from left to right.

go through this code and you'll understand it simply.

Example:

```Javascript
const numbers = [65, 44, 12, 4];

let panda = numbers.reduce((prev, curr) => {
  return prev + curr;
})/ numbers.length;
console.log(panda);

```

Here we are calculating avg of the array.
Now to understand this assume prev and curr as pointers and prev is pointing to index 0 and curr- index 1. The values of these indices will be added one after the other and be saved to prev variable till the end of the array.
Then we divide the sum by the length of the array to get the avg.

note:

a callback is a functions that passed to another function as an argument.

Higher Order Function (HOF) takes a function as a parameter and returns a function.

Major difference between arr.forEach and arr.map is arr.forEach does not create a new arr on the other hand arr.map creates a new array.

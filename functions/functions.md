# Functions
Let us understand functions in typescript.
### 1. Simple Function

A simple function in TypeScript includes a function name, parameters, and a return type. TypeScript allows you to specify the types of parameters and the return type, which helps in catching type-related errors at compile time.

syntax:

`function functionName(parameter1: type, parameter2: type): returnType {
    // Function body
}
`

Example:

```
function greet(name: string): string {
    return ` `Hello, ${name}!`;
}
console.log(greet("Alice")); // Output: Hello, Alice!
```
if you match above syntax with the below example you will understand it easily.

### Function with Optional Parameters
In TypeScript, you can define optional parameters by adding a question mark (?) after the parameter name.

Syntax:

`function functionName(parameter1: type, optionalParameter?: type): returnType {
    // Function body
}
`

Example:

```
function greet(name: string, age?: number): string {
    if (age) {
        return `Hello, ${name}. You are ${age} years old.`;
    }
    return `Hello, ${name}!`;
}

console.log(greet("Alice"));          // Output: Hello, Alice!
console.log(greet("Bob", 30));        // Output: Hello, Bob. You are 30 years old.
```
Basic if statement is self explanatory.

### Function with Default Parameters
In TypeScript, you can define default parameters by assigning a default value to the parameter.

Syntax:

`function functionName(parameter1: type, parameter2: type = defaultValue): returnType {
    // Function body
}`

example:
```
function greet(name: string, greeting: string = "Hello"): string {
    return `${greeting}, ${name}!`;
}

console.log(greet("Alice"));          // Output: Hello, Alice!
console.log(greet("Bob", "Hi"));      // Output: Hi, Bob!
```
You must understand that values are assigned left to right in typescript for example in the above case. First "Alice" argument in the `console.log(greet("Alice"));` goes to the parameter "name", then to the function body that has greeting and then name. 

In the code `console.log(greet("Bob", "Hi"));  ` bob goes to the parameter name and then hi goes to the parameter greeting. But then function body rearranges it to create the output.

###  Function with Rest Parameters

Rest parameters allow you to pass an arbitrary number of arguments to a function. The rest parameters are collected into an array.

Syntax:
`
function functionName(...restParameter: type[]): returnType {
    // Function body
}
`

Example:
```
function addNumbers(...numbers: number[]): number {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(addNumbers(1, 2, 3, 4, 5)); // Output: 15
```

Here, the parameter ...numbers is taking values 1, 2, 3, 4, 5. One by one each argument is going to the function body and total being 0 from the start, is getting added to the number.
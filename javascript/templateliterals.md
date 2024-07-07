# Template literals


In JavaScript, template literals (also known as template strings) are a way to include variables and expressions inside a string. They are enclosed by backticks (`) instead of single quotes (') or double quotes ("). Template literals can contain placeholders, which are indicated by the ${expression} syntax. The expressions inside the placeholders are evaluated and then inserted into the resulting string.

```javascript
let person = {
  name: "John",
  age: 30,
};

// this is the comparison when we type string 
console.log(
  "name of the person",
  person.name,
  "and age of the person",
  person.age
);

// this is string literal

let personobj = `name of the person ${person.name} and age of the person ${person.age}`;
console.log(personobj)
console.log(typeof personobj)
```

note:

property jo hai voh value deti hai.

method kaam karta hai.

strings are immutable.

arrays are mutable

# array methods in javascript:
Arrays come with a variety of built-in methods to manipulate and interact with the data they contain. Here are some key array methods in JavaScript explained:

### Push( ) : add to end
The `push()` method adds one or more elements to the end of an array and returns the new length of the array.
```javascript
let fruits = ['apple', 'banana'];
fruits.push('orange'); // ['apple', 'banana', 'orange']
```

### Pop( ) : delete from end & return
The `pop()` method removes the last element from an array and returns that element.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let lastFruit = fruits.pop(); // lastFruit = 'orange', fruits = ['apple', 'banana']
```

### toString( ) : converts array to string
The `toString()` method converts an array to a string, with each element separated by a comma.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let str = fruits.toString(); // 'apple,banana,orange'
```

### Concat( ) : joins multiple arrays & returns result
The `concat()` method is used to merge two or more arrays. This method does not change the existing arrays, but returns a new array.
```javascript
let fruits = ['apple', 'banana'];
let moreFruits = ['orange', 'grape'];
let allFruits = fruits.concat(moreFruits); // ['apple', 'banana', 'orange', 'grape']
```

### Unshift( ) : add to start
The `unshift()` method adds one or more elements to the beginning of an array and returns the new length of the array.
```javascript
let fruits = ['banana', 'orange'];
fruits.unshift('apple'); // ['apple', 'banana', 'orange']
```

### Shift( ) : delete from start & return
The `shift()` method removes the first element from an array and returns that element.
```javascript
let fruits = ['apple', 'banana', 'orange'];
let firstFruit = fruits.shift(); // firstFruit = 'apple', fruits = ['banana', 'orange']
```

### Slice( ) : returns a piece of the array
The `slice()` method returns a shallow copy of a portion of an array into a new array object selected from `startIdx` to `endIdx` (end not included). The original array will not be modified.
```javascript
let fruits = ['apple', 'banana', 'orange', 'grape'];
let citrus = fruits.slice(1, 3); // ['banana', 'orange']
```

### Splice( ) : change original array (add, remove, replace)
The `splice()` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place. This method modifies the original array.
```javascript
let fruits = ['apple', 'banana', 'orange', 'grape'];
fruits.splice(2, 1, 'lemon', 'kiwi'); // ['apple', 'banana', 'lemon', 'kiwi', 'grape']
```
- `startIdx` is the index at which to start changing the array.
- `delCount` is the number of elements to be removed.
- `newEl1, newEl2, ...` are the elements to add to the array.


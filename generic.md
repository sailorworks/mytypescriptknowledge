# Generic in Typescript

Generics in TypeScript provide a way to create reusable components that can work with any data type. They enable you to write functions, classes, and interfaces that operate on various types while still being type-safe. Here's a detailed explanation of generics in TypeScript with examples:

### 1. Understanding Generics

Generics allow you to define a placeholder type, which can be specified later when the function, class, or interface is used. This makes your code more flexible and reusable.

### 2. Generic Functions

Let's start with a simple example of a generic function.

#### Without Generics:
You might write a function to return the argument passed to it.

```typescript
function identity(arg: any): any {
  return arg;
}
```

The problem with this approach is that it loses the type information.

#### With Generics:
You can define a generic function to retain the type information.

```typescript
function identity<T>(arg: T): T {
  return arg;
}
```

Here, `<T>` is a type parameter that acts as a placeholder for the type that will be provided when the function is called.

```typescript
let output1 = identity<string>("Hello TypeScript");
let output2 = identity<number>(42);
```

TypeScript infers the type if not explicitly specified:

```typescript
let output3 = identity("Inferred TypeScript");
```

### 3. Generic Interfaces

Generics can also be used with interfaces.

```typescript
interface GenericIdentityFn<T> {
  (arg: T): T;
}

function identity<T>(arg: T): T {
  return arg;
}

let myIdentity: GenericIdentityFn<number> = identity;
```

### 4. Generic Classes

Generics in classes allow you to create a class that can work with different types without specifying the exact type.

```typescript
class GenericNumber<T> {
  zeroValue: T;
  add: (x: T, y: T) => T;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function (x, y) {
  return x + y;
};
```
this is not studied yet as it is not required a lot of time

### 5. Generic Constraints

Sometimes you want to limit the types you can use with your generic. You can achieve this by using constraints.

```typescript
interface Lengthwise {
  length: number;
}

function loggingIdentity<T extends Lengthwise>(arg: T): T {
  console.log(arg.length);
  return arg;
}

// This works
loggingIdentity({ length: 10, value: 3 });

// This gives an error
// loggingIdentity(3);
```

### 6. Using Multiple Type Parameters

You can also use multiple type parameters in your generics.

```typescript
function merge<T, U>(obj1: T, obj2: U): T & U {
  return { ...obj1, ...obj2 };
}

const result = merge({ name: "John" }, { age: 30 });
console.log(result.name); // John
console.log(result.age);  // 30
```

### 7. Generic Classes with Default Types

You can provide default types for generics in classes.

```typescript
class Container<T = string> {
  value: T;

  constructor(value: T) {
    this.value = value;
  }
}

let stringContainer = new Container("Hello");
let numberContainer = new Container<number>(123);
```

### 8. Conclusion

Generics are a powerful feature in TypeScript that enable you to write flexible, reusable, and type-safe code. By using generics, you can create components that can work with any type while retaining type information and constraints.

### Examples Recap

1. **Generic Function:**

    ```typescript
    function identity<T>(arg: T): T {
      return arg;
    }
    ```

2. **Generic Interface:**

    ```typescript
    interface GenericIdentityFn<T> {
      (arg: T): T;
    }

    let myIdentity: GenericIdentityFn<number> = identity;
    ```

3. **Generic Class:**

    ```typescript
    class GenericNumber<T> {
      zeroValue: T;
      add: (x: T, y: T) => T;
    }

    let myGenericNumber = new GenericNumber<number>();
    myGenericNumber.zeroValue = 0;
    myGenericNumber.add = function (x, y) {
      return x + y;
    };
    ```

4. **Generic Constraints:**

    ```typescript
    interface Lengthwise {
      length: number;
    }

    function loggingIdentity<T extends Lengthwise>(arg: T): T {
      console.log(arg.length);
      return arg;
    }
    ```

5. **Multiple Type Parameters:**

    ```typescript
    function merge<T, U>(obj1: T, obj2: U): T & U {
      return { ...obj1, ...obj2 };
    }
    ```

By mastering generics, you can significantly enhance the versatility and robustness of your TypeScript code.
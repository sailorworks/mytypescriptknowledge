# Type keyword:

In TypeScript, both `type` and `interface` are used to define the shape of objects. They have similar functionalities but differ in some key aspects. Here’s an in-depth explanation:

### Type Alias

**Definition:** The `type` keyword in TypeScript is used to create a type alias. A type alias is a name for any type, including primitive `` type ID = number;
type Name = string;
``
, object ``type Point = {
  x: number;
  y: number;
};
`` and function types - ``type Callback = (value: string) => void;
``.
Some type alias example:

**Syntax:**
```typescript
type AliasName = someType;
```

**Example:**
```typescript
type Point = {
  x: number;
  y: number;
};

type ID = number | string;

type Callback = (value: string) => void;
```

**Features:**
1. **Flexibility:** `type` can represent complex types such as unions, intersections, and tuples.
2. **Union and Intersection Types:** Allows combining multiple types.
3. **Primarily used for complex type definitions and unions.**

**Usage:**
- **Union Types:**
  ```typescript
  type ID = number | string;
  ```
- **Intersection Types:**
  ```typescript
  type Person = { name: string } & { age: number };
  ```
- **Function Types:**
  ```typescript
  type Callback = (value: string) => void;
  ```

### Interface

**Definition:** The `interface` keyword is used to define the structure of an object. Interfaces are more focused on object shapes and are extendable and implementable.

**Syntax:**
```typescript
interface InterfaceName {
  property: type;
  method(): returnType;
}
```

**Example:**
```typescript
interface Point {
  x: number;
  y: number;
}

interface Person {
  name: string;
  age: number;
  greet(): void;
}
```

**Features:**
1. **Extendable:** Interfaces can extend other interfaces or types, allowing for a flexible and scalable object-oriented design.
2. **Implementable:** Classes can implement interfaces, enforcing a contract on class instances.
3. **Primarily used for defining object shapes and contracts within your code.**

**Usage:**
- **Object Shapes:**
  ```typescript
  interface Point {
    x: number;
    y: number;
  }
  ```
- **Class Implementation:**
  ```typescript
  interface Greetable {
    greet(): void;
  }

  class Person implements Greetable {
    name: string;
    constructor(name: string) {
      this.name = name;
    }
    greet() {
      console.log(`Hello, my name is ${this.name}`);
    }
  }
  ```

### Differences and Best Practices

**Differences:**
1. **Capabilities:**
   - `type` can be used for more complex type manipulations (unions, intersections).
   - `interface` is mainly used for object shapes and is extendable and implementable by classes.
   
2. **Extension:**
   - Interfaces can extend types and other interfaces.
   - Types cannot extend interfaces, but they can use intersections to achieve similar functionality.

3. **Declaration Merging:**
   - Interfaces support declaration merging, meaning you can define the same interface in multiple locations, and TypeScript will merge them.
   - Types do not support declaration merging.

**Best Practices:**

1. **Use `interface` for defining objects and class contracts:**
   - If you are defining the shape of an object or creating a contract for a class, prefer using `interface`.
   ```typescript
   interface User {
     name: string;
     age: number;
   }

   class Employee implements User {
     name: string;
     age: number;
     constructor(name: string, age: number) {
       this.name = name;
       this.age = age;
     }
   }
   ```

2. **Use `type` for complex type manipulations and unions:**
   - When working with unions, intersections, or more complex type definitions, prefer using `type`.
   ```typescript
   type ID = number | string;
   type Coordinates = { x: number; y: number; } & { z: number };
   ```

3. **Consistency:**
   - Maintain consistency within your codebase. If your project primarily uses `interface`, try to stick with it unless `type` offers a clear advantage for a particular use case.

4. **Declaration Merging:**
   - Use `interface` when you need declaration merging features.
   ```typescript
   interface Animal {
     name: string;
   }

   interface Animal {
     age: number;
   }

   // Merged interface
   const dog: Animal = { name: "Rex", age: 5 };
   ```

By understanding the differences and best practices for `type` and `interface`, you can use them effectively in your TypeScript projects to create clear, maintainable, and robust code.

Just go through this once.
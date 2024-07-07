# Classes

### Basics of Classes

A class is a blueprint for creating objects. Classes encapsulate data (properties) and behaviors (methods) that operate on that data.

### Defining a Class

Here's how you define a basic class in TypeScript:

```typescript
class Animal {
  // Properties
  name: string;
  age: number;

  // Constructor
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  // Method
  makeSound() {
    console.log("Some generic sound");
  }
}
```

### Properties

Properties are variables that belong to the class. In the example above, `name` and `age` are properties of the `Animal` class.

### Constructor

The constructor is a special method that gets called when a new instance of the class is created. It’s typically used to initialize properties:

### Methods

Methods are functions that belong to the class and can operate on its properties. T

### Access Modifiers

TypeScript provides three access modifiers: `public`, `private`, and `protected`.

- **public**: By default, properties and methods are public, meaning they can be accessed from anywhere.
- **private**: Private properties and methods can only be accessed within the class they are declared.
- **protected**: Protected properties and methods can be accessed within the class and its subclasses.

Example:

```typescript
class Animal {
  public name: string;
  private age: number;
  protected species: string;

  constructor(name: string, age: number, species: string) {
    this.name = name;
    this.age = age;
    this.species = species;
  }

  private makeSound() {
    console.log("Some generic sound");
  }

  public getAge() {
    return this.age;
  }
}

const myAnimal = new Animal("Lion", 3, "Panthera leo");
console.log(myAnimal.name); // Accessible
console.log(myAnimal.getAge()); // Accessible
// console.log(myAnimal.age); // Error: Property 'age' is private
// myAnimal.makeSound(); // Error: Method 'makeSound' is private
```

Not mostly used in the code.

### Inheritance

Classes can inherit from other classes using the `extends` keyword. This allows a class to inherit properties and methods from another class.

```typescript
class Dog extends Animal {
  constructor(name: string, age: number) {
    super(name, age);
  }

  makeSound() {
    console.log("Bark");
  }
}

const myDog = new Dog("Rex", 2);
myDog.makeSound(); // Output: Bark
```

### Abstract Classes

Abstract classes are classes that cannot be instantiated directly. They are used as base classes for other classes. Abstract methods in an abstract class do not have an implementation and must be implemented in derived classes.

```typescript
abstract class Animal {
  abstract makeSound(): void; // Abstract method

  move() {
    console.log("Moving...");
  }
}

class Dog extends Animal {
  makeSound() {
    console.log("Bark");
  }
}

const myDog = new Dog();
myDog.makeSound(); // Output: Bark
myDog.move(); // Output: Moving...
```

### Interfaces

TypeScript interfaces are used to define the structure of an object. Classes can implement interfaces to ensure they adhere to a specific contract.

```typescript
interface AnimalInterface {
  name: string;
  age: number;
  makeSound(): void;
}

class Cat implements AnimalInterface {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }

  makeSound() {
    console.log("Meow");
  }
}

const myCat = new Cat("Whiskers", 4);
myCat.makeSound(); // Output: Meow
```

### Getters and Setters

Getters and setters allow you to define how properties are accessed and mutated.

```typescript
class Animal {
  private _name: string;

  constructor(name: string) {
    this._name = name;
  }

  get name(): string {
    return this._name;
  }

  set name(newName: string) {
    if (newName.length > 0) {
      this._name = newName;
    } else {
      console.log("Name cannot be empty");
    }
  }
}

const myAnimal = new Animal("Lion");
console.log(myAnimal.name); // Output: Lion
myAnimal.name = "Tiger";
console.log(myAnimal.name); // Output: Tiger
```

### Static Members

Static properties and methods belong to the class itself rather than instances of the class.

```typescript
class Animal {
  static kingdom: string = "Animalia";

  static getKingdom() {
    return Animal.kingdom;
  }
}

console.log(Animal.kingdom); // Output: Animalia
console.log(Animal.getKingdom()); // Output: Animalia
```

### Conclusion

Classes in TypeScript are a powerful feature that allows you to create structured, reusable, and maintainable code. They extend JavaScript's classes with type annotations, access modifiers, and other features that help enforce proper coding practices and improve code quality.
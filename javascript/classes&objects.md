### Prototype

An object is an entity having state and behavior(properties and method)

Js objects have special property called prototype

basically prototype helps in using object into another object.

We can set prototype using ** proto **

### class

Class is a blueprint of an object. Those objects have some state variables and some behavioural function inside it.

Syntax:

```
class MyClass{
    constructor(){...}
    method1(){...}
}

let myObj = new MyClass();

```

Example:

```Javascript
class myCar {
  start() {
    console.log("Car started");
  }
  stop() {
    console.log("Car stopped");
  }
}

let lalacar = new myCar();
```

### Constructor

Constructor is a special method which is called when an object is created from a class.

Syntax:

```
class MyClass {
    constructor(param1, param2) {
        // Initialize properties
        this.property1 = param1;
        this.property2 = param2;
    }

    method1() {
        // Method definition
    }
}

let myObj = new MyClass(value1, value2);


```

Example:

```Javascript
class Car {
    constructor(brand, model) {
        this.brand = brand; // Assigning value to the brand property
        this.model = model; // Assigning value to the model property
    }

    start() {
        console.log(`${this.brand} ${this.model} started`);
    }

    stop() {
        console.log(`${this.brand} ${this.model} stopped`);
    }
}

// Creating an instance of the Car class
let myCar = new Car("Toyota", "Corolla");


```

### Inheritance

Inheritance is a fundamental concept in object-oriented programming that allows a class to inherit properties and methods from another class. In JavaScript, inheritance is implemented using the `extends` keyword.

Syntax:

```javascript
class ParentClass {
  // Parent class methods and properties
}

class ChildClass extends ParentClass {
  // Child class methods and properties
}
```

Example:

```javascript
class Vehicle {
  constructor(brand) {
    this.brand = brand;
  }

  start() {
    console.log(`${this.brand} vehicle started`);
  }
}

class Car extends Vehicle {
  honk() {
    console.log("Beep beep!");
  }
}

let myCar = new Car("Toyota");
myCar.start(); // Output: Toyota vehicle started
myCar.honk(); // Output: Beep beep!
```

In this example, `Car` inherits from `Vehicle`. The `Car` class has access to the `start` method from `Vehicle` and adds its own `honk` method.

### super()

The `super` keyword is used in classes to call corresponding methods of the parent class. It's particularly useful in the constructor of a child class to invoke the constructor of its parent class.

Syntax:

```javascript
class ChildClass extends ParentClass {
  constructor(childParam, parentParam) {
    super(parentParam);
    // Additional initialization for ChildClass
  }

  someMethod() {
    super.parentMethod();
    // Additional code for ChildClass method
  }
}
```

Example:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // Call the parent constructor
    this.breed = breed;
  }

  speak() {
    super.speak(); // Call the parent method
    console.log(`${this.name} barks.`);
  }
}

let myDog = new Dog("Buddy", "Labrador");
myDog.speak();
// Output:
// Buddy makes a sound.
// Buddy barks.
```

In this example, `super(name)` in the `Dog` constructor calls the `Animal` constructor, and `super.speak()` in the `Dog` `speak` method calls the `Animal` `speak` method before adding its own functionality.

### simple try and catch

If you think that your code would generate some error and you would like to test it. you can use try - catch. It will not interrupt the code and execute further code as well.

Syntax:

```
try{
    //code
}
catch(error){
    //code
}
```

Example:

```Javascript
let a = 6
let b = 7
console.log("a is ", a)
console.log("b is ", b)
console.log("a+b is equal to", a + b)
console.log("a+b is equal to", a + b)
try {
    console.log("a+b is equal to", a + c)
}
catch (err) {
    console.log(err)
}

console.log("a+b is equal to", a + b)


```

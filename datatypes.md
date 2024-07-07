# Datatypes
In TypeScript, datatypes are used to define the type of data a variable can hold. This helps catch errors early and makes your code more predictable. Here are the main datatypes in TypeScript explained simply:

1. **Boolean**: 
   - Represents true or false values.
   - Example: `let isActive: boolean = true;`

2. **Number**: 
   - Represents all kinds of numbers: integers, floats, etc.
   - Example: `let age: number = 25;`

3. **String**: 
   - Represents text.
   - Example: `let name: string = "John";`

4. **Array**: 
   - Represents a list of values of the same type.
   - Example: `let scores: number[] = [10, 20, 30];`
   - Another(best/generic way you can define) way to declare: `let scores: Array<number> = [10, 20, 30];`

5. **Tuple**: 
   - Represents an array with a fixed number of elements, where each element can have a different type.
   - Example: `let person: [string, number] = ["Alice", 30];`

6. **Enum**: 
   - Represents a collection of related values that can be numeric or string-based.
   - Example: 
     ```typescript
     enum Color { Red, Green, Blue }
     let c: Color = Color.Green;
     ```

7. **Any**: 
   - Can hold any type of value. Use sparingly as it disables type checking.
   - Example: `let data: any = "hello";`
   - Later, `data = 10;` is also valid.

8. **Void**: 
   - Represents the absence of a type. Commonly used as the return type of functions that do not return a value.
   - Example: 
     ```typescript
     function greet(): void {
       console.log("Hello");
     }
     ```

9. **Null and Undefined**: 
   - `null` represents an intentionally absent object.
   - `undefined` represents an uninitialized variable.
   - Example: `let x: null = null;` and `let y: undefined = undefined;`

10. **Object**: 
    - Represents a non-primitive type (i.e., anything that's not `number`, `string`, `boolean`, `symbol`, `null`, or `undefined`).
    - Example: 
      ```typescript
      let person: { name: string, age: number } = {
        name: "John",
        age: 30
      };
      ```

11. **Union Types**: 
    - Represents a variable that can hold more than one type.
    - Example: `let id: string | number;`
    - `id = "123";` and `id = 123;` are both valid.

These are the basic datatypes in TypeScript that help you define the shape and behavior of your data more precisely.

This is simiply a copy paste from chatgpt.
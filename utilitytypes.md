TypeScript provides several utility types to facilitate common type transformations and operations. Here are ten of the most commonly used utility types:

1. **`Partial<T>`**:
   - Constructs a type with all properties of `T` set to optional.
   ```typescript
   interface User {
     id: number;
     name: string;
     age: number;
   }
   
   const updateUser: Partial<User> = {
     name: "Alice"
   };
   ```

2. **`Required<T>`**:
   - Constructs a type consisting of all properties of `T` set to required.
   ```typescript
   interface User {
     id?: number;
     name?: string;
     age?: number;
   }
   
   const newUser: Required<User> = {
     id: 1,
     name: "Alice",
     age: 30
   };
   ```

3. **`Readonly<T>`**:
   - Constructs a type with all properties of `T` set to readonly(does not allow to change ).
   ```typescript
   interface User {
     id: number;
     name: string;
     age: number;
   }
   
   const user: Readonly<User> = {
     id: 1,
     name: "Alice",
     age: 30
   };
   ```

4. **`Record<K, T>`**:
   - Constructs a type with a set of properties `K` of type `T`.
   ```typescript
   type Role = "admin" | "user" | "guest";
   
   const rolePermissions: Record<Role, string[]> = {
     admin: ["read", "write", "delete"],
     user: ["read", "write"],
     guest: ["read"]
   };
   ```

5. **`Pick<T, K>`**:
   - Constructs a type by picking the set of properties `K` from `T`.
   ```typescript
   interface User {
     id: number;
     name: string;
     age: number;
   }
   
   const user: Pick<User, "id" | "name"> = {
     id: 1,
     name: "Alice"
   };
   ```

6. **`Omit<T, K>`**:
   - Constructs a type by omitting the set of properties `K` from `T`.
   ```typescript
   interface User {
     id: number;
     name: string;
     age: number;
   }
   
   const user: Omit<User, "age"> = {
     id: 1,
     name: "Alice"
   };
   ```

7. **`Exclude<T, U>`**:
   - Constructs a type by excluding from `T` all properties that are assignable to `U`.
   ```typescript
   type T = "a" | "b" | "c";
   type U = "a" | "b";
   
   type Result = Exclude<T, U>; // "c"
   ```

8. **`Extract<T, U>`**:
   - Constructs a type by extracting from `T` all properties that are assignable to `U`.
   ```typescript
   type T = "a" | "b" | "c";
   type U = "a" | "b";
   
   type Result = Extract<T, U>; // "a" | "b"
   ```

9. **`NonNullable<T>`**:
   - Constructs a type by excluding `null` and `undefined` from `T`.
   ```typescript
   type T = string | number | null | undefined;
   
   type Result = NonNullable<T>; // string | number
   ```

10. **`ReturnType<T>`**:
    - Constructs a type consisting of the return type of function `T`.
    ```typescript
    function getUser() {
      return {
        id: 1,
        name: "Alice",
        age: 30
      };
    }
    
    type User = ReturnType<typeof getUser>;
    ```

These utility types are extremely useful for transforming and manipulating types in TypeScript, making type definitions more flexible and reusable.
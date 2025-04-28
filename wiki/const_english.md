<!--
Meta Description: # Understanding "const" in TypeScript: A Comprehensive Guide ## Synopsis The `const` keyword in TypeScript is a powerful feature used to declare varia...
Meta Keywords: const, typescript, constant, cannot, object
-->

# Understanding "const" in TypeScript: A Comprehensive Guide

## Synopsis
The `const` keyword in TypeScript is a powerful feature used to declare variables that are block-scoped and immutable, meaning their values cannot be reassigned after their initial assignment.

## Documentation
### Purpose
The `const` keyword serves to create constants in TypeScript, providing a way to define variables that should not change throughout their lifecycle. This is particularly useful when you want to ensure that certain values remain consistent and prevent accidental changes to them.

### Usage
To declare a constant in TypeScript, use the `const` keyword followed by the variable name and its initial value. The syntax is as follows:

```typescript
const variableName: dataType = initialValue;
```

- **variableName**: The identifier for the constant.
- **dataType**: (Optional) The type of the constant (TypeScript uses type inference if not explicitly provided).
- **initialValue**: The value assigned to the constant, which cannot be changed later.

### Details
- **Block Scope**: Constants declared with `const` are block-scoped, meaning they are only accessible within the block in which they are defined.
- **Immutable Binding**: While the reference to the constant cannot be changed, if the constant is an object or array, the properties or elements of that object/array can still be modified.
- **Error on Reassignment**: Attempting to reassign a value to a constant will result in a compilation error.

## Examples
### Basic Usage
Here are some simple examples demonstrating the use of `const` in TypeScript:

#### Example 1: Basic Constant Declaration
```typescript
const pi: number = 3.14;
console.log(pi); // Output: 3.14
```

#### Example 2: Block Scope
```typescript
if (true) {
    const message: string = "Hello, TypeScript!";
    console.log(message); // Output: Hello, TypeScript!
}
// console.log(message); // Error: Cannot find name 'message'
```

#### Example 3: Object Constant
```typescript
const user = { name: "Alice", age: 30 };
user.age = 31; // Valid: properties can be modified
console.log(user); // Output: { name: "Alice", age: 31 }
// user = {}; // Error: Cannot assign to 'user' because it is a constant.
```

## Explanation
### Common Pitfalls
- **Reassignment Error**: One of the most common issues developers face is trying to reassign a `const` variable, which will lead to a compilation error.
- **Object Mutability**: New developers might misunderstand `const` as making an object immutable. While the reference to the object cannot be changed, the properties of the object can still be modified.

### Gotchas
- **Global Constants**: Be cautious when declaring `const` variables at the global scope, as they can lead to variable shadowing or conflicts with similarly named variables in other scopes.
- **Array Modifications**: While you cannot reassign a `const` array, you can modify its contents (e.g., using methods like `push`, `pop`, etc.).

## One Line Summary
The `const` keyword in TypeScript is used to declare block-scoped, immutable variables, ensuring that their bindings remain constant throughout their lifecycle.
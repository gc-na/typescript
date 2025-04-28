<!--
Meta Description: # Understanding `undefined` in TypeScript: Definition, Usage, and Examples ## Synopsis In TypeScript, `undefined` is a primitive data type that repres...
Meta Keywords: undefined, typescript, value, type, not
-->

# Understanding `undefined` in TypeScript: Definition, Usage, and Examples

## Synopsis
In TypeScript, `undefined` is a primitive data type that represents the absence of a value. It is often used to indicate that a variable has been declared but not yet assigned a value, playing a crucial role in type safety and error handling.

## Documentation
### Purpose
The `undefined` type in TypeScript serves as a marker for uninitialized variables and provides a way to express optional values in functions and objects. This helps developers avoid runtime errors that can occur when attempting to access non-existent properties or methods.

### Usage
In TypeScript, every variable is implicitly assigned the value `undefined` upon declaration unless explicitly initialized. The `undefined` type can also be used in function parameters and return types to indicate that certain values may not be provided.

#### Declaration
```typescript
let myVariable: number | undefined; // myVariable can be a number or undefined
```

#### Function Example
```typescript
function getLength(value?: string): number {
    return value ? value.length : 0; // value can be undefined
}
```

### Details
- **Type Checking**: TypeScript checks for `undefined` values during compile-time, allowing developers to handle potential errors before code execution.
- **Optional Chaining**: Combined with optional chaining (`?.`), `undefined` allows safe access to nested properties.
- **Strict Null Checks**: When `strictNullChecks` is enabled in the TypeScript configuration, `undefined` is treated as a distinct type. This requires developers to manage `undefined` values explicitly.

## Examples
### Basic Usage Example
```typescript
let x: string | undefined; // x can be a string or undefined
x = "Hello, TypeScript!";
console.log(x); // Output: Hello, TypeScript!

x = undefined; // x is now undefined
console.log(x); // Output: undefined
```

### Function with Optional Parameter
```typescript
function greet(name?: string): string {
    return `Hello, ${name || "Guest"}!`;
}

console.log(greet("Alice")); // Output: Hello, Alice!
console.log(greet()); // Output: Hello, Guest!
```

## Explanation
### Common Pitfalls
1. **Accidental Overwriting**: Developers may inadvertently overwrite variables with `undefined`, leading to unexpected behavior.
2. **Type Compatibility**: When using strict type checks, attempting to assign `undefined` to a variable that does not explicitly allow it will result in a compilation error.

### Gotchas
- **Nullable Types**: In TypeScript, `null` and `undefined` are distinct; `null` represents an intentional absence of any object value, while `undefined` signifies that a variable has not been assigned a value.
- **Default Parameter Values**: If a function parameter is not provided, it is set to `undefined` unless a default value is specified.

## One Line Summary
In TypeScript, `undefined` is a primitive type that indicates an uninitialized variable or an optional value that may not be provided.
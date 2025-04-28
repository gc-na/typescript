<!--
Meta Description: # Understanding "readonly" in TypeScript: A Comprehensive Guide ## Synopsis The `readonly` modifier in TypeScript is a powerful feature that allows de...
Meta Keywords: readonly, typescript, only, properties, can
-->

# Understanding "readonly" in TypeScript: A Comprehensive Guide

## Synopsis
The `readonly` modifier in TypeScript is a powerful feature that allows developers to define properties in interfaces and classes as immutable, ensuring that they cannot be changed after initialization.

## Documentation
The `readonly` modifier is used in TypeScript to create properties that can only be assigned a value when they are declared or within the constructor of a class. This feature is particularly useful for creating immutable data structures, helping to prevent accidental modifications and enhancing code safety.

### Purpose
The primary purpose of the `readonly` modifier is to enforce immutability on object properties. By limiting the ability to change values, developers can create more predictable and maintainable code.

### Usage
To use `readonly`, you simply place it before a property declaration in an interface or class. Here’s the syntax:

```typescript
readonly propertyName: type;
```

### Details
- **Interfaces**: When used in an interface, properties marked with `readonly` can only be set during object creation.
- **Classes**: In classes, `readonly` properties can only be initialized in their declaration or in the class constructor.
- **Arrays**: You can also use `readonly` with arrays to create immutable array types.

## Examples

### Basic Usage with Interfaces
```typescript
interface User {
    readonly id: number;
    name: string;
}

const user: User = { id: 1, name: "Alice" };
user.name = "Bob"; // Allowed
user.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.
```

### Basic Usage with Classes
```typescript
class Point {
    readonly x: number;
    readonly y: number;

    constructor(x: number, y: number) {
        this.x = x;
        this.y = y;
    }
}

const point = new Point(10, 20);
console.log(point.x); // 10
point.x = 15; // Error: Cannot assign to 'x' because it is a read-only property.
```

### Using `readonly` with Arrays
```typescript
const numbers: readonly number[] = [1, 2, 3];
numbers[0] = 10; // Error: Index signature in type 'readonly number[]' only permits reading.
```

## Explanation
While the `readonly` modifier is a simple yet effective feature, there are some common pitfalls to be aware of:

- **Deep Immutability**: The `readonly` modifier only applies to the immediate property. For example, if a `readonly` property is an object, its internal properties can still be modified unless they are also marked as `readonly`.
  
- **Class Instances**: In classes, if a `readonly` property is initialized outside of the constructor or declaration, TypeScript will throw an error.

- **Use Cases**: `readonly` is particularly useful in functional programming paradigms and in scenarios where data integrity is critical, such as in state management.

## One Line Summary
The `readonly` modifier in TypeScript enforces immutability on properties, ensuring they can only be assigned at initialization or within a class constructor.
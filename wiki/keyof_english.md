<!--
Meta Description: # Understanding "keyof" in TypeScript: A Comprehensive Guide ## Synopsis The `keyof` operator in TypeScript is a powerful utility type that allows dev...
Meta Keywords: type, keyof, object, keys, typescript
-->

# Understanding "keyof" in TypeScript: A Comprehensive Guide

## Synopsis
The `keyof` operator in TypeScript is a powerful utility type that allows developers to create a union type from the keys of an object type, facilitating type-safe access to object properties.

## Documentation
The `keyof` operator is a TypeScript feature that maps object properties to a union type of their keys. This operator is particularly useful when you need to work with object types dynamically and ensures type safety when accessing properties.

### Purpose
The primary purpose of `keyof` is to provide a way to extract keys from an object type, enabling better type inference and making code more robust and maintainable.

### Usage
The `keyof` operator can be applied to any object type, including interfaces and classes. When used, it returns a union of string literal types corresponding to the keys of the object.

#### Syntax
```typescript
keyof T
```

Where `T` is an object type.

### Details
- The keys extracted using `keyof` can be used in type definitions, function parameters, or any other context where a type is expected.
- It works with both string and numeric keys, but keys must be present in the type definition.
- The `keyof` operator can be combined with other utility types and TypeScript features to create complex types.

## Examples

### Basic Usage
Here’s a simple example demonstrating how `keyof` can be utilized:

```typescript
interface Person {
    name: string;
    age: number;
    isStudent: boolean;
}

type PersonKeys = keyof Person;  // "name" | "age" | "isStudent"

function getProperty<T>(obj: T, key: keyof T) {
    return obj[key];
}

const person: Person = { name: "John", age: 30, isStudent: false };
const name = getProperty(person, "name"); // "John"
const age = getProperty(person, "age"); // 30
```

### Using with Generics
You can also use `keyof` with generics for flexible code:

```typescript
function getValue<T>(obj: T, key: keyof T) {
    return obj[key];
}

const car = { make: "Tesla", model: "Model 3", year: 2020 };
const model = getValue(car, "model"); // "Model 3"
```

## Explanation
While using `keyof`, there are a few common pitfalls and gotchas to be aware of:

- **Non-Object Types**: Applying `keyof` to non-object types (like primitive types) results in a compilation error.
- **Index Signatures**: When using `keyof` with an object that has index signatures, the resulting type may not include all keys explicitly defined.
- **Readonly Properties**: If the object has readonly properties, `keyof` will still return those keys, but you cannot modify them without type assertions.
- **Dynamic Properties**: If properties are added dynamically (e.g., using `Object.assign`), `keyof` will not recognize them unless they are defined in the type.

## One Line Summary
The `keyof` operator in TypeScript generates a union type of the keys of an object type, enabling type-safe property access.
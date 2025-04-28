<!--
Meta Description: # Understanding "unique" in TypeScript: A Comprehensive Guide ## Synopsis In TypeScript, the `unique` type operator is not a built-in feature but a co...
Meta Keywords: type, unique, types, userid, typescript
-->

# Understanding "unique" in TypeScript: A Comprehensive Guide

## Synopsis
In TypeScript, the `unique` type operator is not a built-in feature but a conceptual term often associated with creating unique types for improved type safety and better code maintainability. This article explores how to implement unique types in TypeScript, enhancing your type system.

## Documentation
### Purpose
The purpose of creating unique types in TypeScript is to prevent type collisions and ensure that different values, even if they are of the same underlying type, are treated as distinct types. This is particularly useful in scenarios where you want to enforce stricter type checks and avoid accidental mixing of types.

### Usage
To create a unique type in TypeScript, you can leverage the concept of "branding" using intersection types. This involves creating a new type that combines an existing type with a unique identifier. Here’s how you can achieve this:

```typescript
type UniqueID = string & { readonly brand: unique symbol };
```

In the above example, `UniqueID` is a new type that is based on `string`, but it has a unique branding that distinguishes it from regular strings.

### Details
- **Branding:** The use of a `unique symbol` in TypeScript ensures that the type cannot be accidentally assigned a value of the base type (in this case, `string`). 
- **Readonly:** Adding `readonly` makes the branding immutable, further enhancing the uniqueness of the type.
- **Type Safety:** Using unique types helps in enforcing type safety across your application, reducing the chances of bugs related to type mismatches.

## Examples
### Basic Usage Example

```typescript
type UserID = string & { readonly brand: unique symbol };
type ProductID = string & { readonly brand: unique symbol };

function getUser(id: UserID) {
    // Implementation to fetch user by id
}

function getProduct(id: ProductID) {
    // Implementation to fetch product by id
}

const userId: UserID = "123" as UserID; // Correctly branded UserID
const productId: ProductID = "456" as ProductID; // Correctly branded ProductID

getUser(userId); // Valid usage
getProduct(productId); // Valid usage
// getUser(productId); // Error: Argument of type 'ProductID' is not assignable to parameter of type 'UserID'.
```

### Advanced Usage Example
You can also use unique types in more complex scenarios such as combining them with interfaces.

```typescript
interface User {
    id: UserID;
    name: string;
}

const user: User = {
    id: "789" as UserID, // Correctly branded UserID
    name: "John Doe"
};

// user.id = "abc" as UserID; // Error: Cannot assign to 'id' because it is a read-only property.
```

## Explanation
### Common Pitfalls
- **Type Assertion:** Be cautious with type assertions (e.g., using `as`). While they can help you create unique types, overusing them can lead to loss of type safety.
- **Accidental Mixing:** Without proper branding, you might accidentally assign a `string` to a unique type. Always ensure that your types are properly branded.

### Gotchas
- **Symbol Uniqueness:** Remember that the `unique symbol` type is only unique within the scope of the file or module. If you are using unique types across different files, ensure that the symbols are not redefined.
- **Performance:** Although unique types provide better type safety, they can add complexity to your type definitions. Use them judiciously to maintain code readability.

## One Line Summary
In TypeScript, creating unique types enhances type safety by preventing type collisions through branding with unique symbols.
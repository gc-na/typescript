<!--
Meta Description: # Understanding the `export` Keyword in TypeScript: A Comprehensive Guide ## Synopsis The `export` keyword in TypeScript is used to make variables, fu...
Meta Keywords: export, exports, default, typescript, can
-->

# Understanding the `export` Keyword in TypeScript: A Comprehensive Guide

## Synopsis
The `export` keyword in TypeScript is used to make variables, functions, classes, and interfaces available for use in other files or modules, facilitating modular programming and code organization.

## Documentation
In TypeScript, the `export` keyword serves a crucial role in module-based architecture. It allows developers to define which parts of a module can be accessed from other modules, promoting encapsulation and reusability of code.

### Purpose
- **Encapsulation**: To hide implementation details and expose only the necessary parts of the module.
- **Reusability**: To enable the sharing of code across different modules, making codebase management easier.

### Usage
The `export` keyword can be used in several ways:
1. **Named Exports**: You can export multiple values from a module using named exports.
2. **Default Exports**: You can designate a single export as the default export, which can be imported without curly braces.

### Details
- **Named Exports**: To export variables, functions, or classes, you prefix them with the `export` keyword.
  ```typescript
  export const name = "TypeScript";
  export function greet() {
      console.log("Hello, TypeScript!");
  }
  export class User {
      constructor(public username: string) {}
  }
  ```

- **Default Exports**: To define a default export, use the `export default` syntax.
  ```typescript
  export default function main() {
      console.log("This is the default export!");
  }
  ```

- **Importing Exports**: You can import named exports using curly braces and default exports without them.
  ```typescript
  import { name, greet } from './module';
  import main from './module';
  ```

## Examples

### Example 1: Named Exports
```typescript
// module.ts
export const PI = 3.14;
export function calculateArea(radius: number): number {
    return PI * radius * radius;
}

// app.ts
import { PI, calculateArea } from './module';
console.log(calculateArea(5)); // Outputs: 78.5
```

### Example 2: Default Export
```typescript
// logger.ts
export default function log(message: string) {
    console.log(message);
}

// app.ts
import log from './logger';
log("Logging a message."); // Outputs: Logging a message.
```

## Explanation
### Common Pitfalls
- **Forget to use `export`**: If you forget to add the `export` keyword, the variable or function will not be accessible from other modules.
- **Confusion between named and default exports**: Mixing up named exports and default exports can lead to import errors. Always remember to use curly braces for named imports and not for default imports.

### Gotchas
- **Circular Dependencies**: Using exports can sometimes lead to circular dependencies, where two modules depend on each other, potentially causing runtime issues.
- **Re-exporting**: You can re-export items from other modules without needing to import them first, which can simplify module exports.

## One Line Summary
The `export` keyword in TypeScript is essential for sharing code across modules, enabling better organization and reusability of code components.
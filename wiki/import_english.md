<!--
Meta Description: # Understanding the "import" Statement in TypeScript: A Comprehensive Guide ## Synopsis The `import` statement in TypeScript is essential for includin...
Meta Keywords: import, typescript, from, module, importing
-->

# Understanding the "import" Statement in TypeScript: A Comprehensive Guide

## Synopsis
The `import` statement in TypeScript is essential for including modules, enabling code reuse, and maintaining modularity in applications. It provides a standardized way to bring in functionality from other files or libraries, fostering better organization and collaboration in codebases.

## Documentation
### Purpose
The `import` statement allows developers to include modules, classes, functions, or variables defined in other files or libraries within TypeScript applications. This modular approach enhances code organization, promotes reusability, and simplifies dependency management.

### Usage
The `import` statement can be used in several forms, depending on what is being imported and how it is structured. Here are the primary ways to use `import` in TypeScript:

1. **Importing a Default Export**:
   ```typescript
   import DefaultExport from './module';
   ```
   This imports the default export from the specified module.

2. **Importing Named Exports**:
   ```typescript
   import { NamedExport1, NamedExport2 } from './module';
   ```
   This imports specific named exports from the module.

3. **Importing All Exports**:
   ```typescript
   import * as ModuleName from './module';
   ```
   This imports all exports from the module and groups them under a single namespace.

4. **Importing with Aliases**:
   ```typescript
   import { NamedExport as Alias } from './module';
   ```
   This allows you to import a named export under a different name.

5. **Dynamic Imports**:
   ```typescript
   const module = await import('./module');
   ```
   This allows for loading modules dynamically at runtime, useful for code splitting.

### Importing Type Declarations
TypeScript also allows you to import types separately:
```typescript
import type { MyType } from './types';
```
This is particularly useful for keeping the code clean and optimizing performance by only loading type information.

## Examples
### Basic Example
**Importing a Default Export**
```typescript
// module.ts
export default function greet() {
    console.log("Hello, World!");
}

// main.ts
import greet from './module';
greet();
```

**Importing Named Exports**
```typescript
// math.ts
export const PI = 3.14;
export function add(x: number, y: number) {
    return x + y;
}

// main.ts
import { PI, add } from './math';
console.log(`PI: ${PI}`);
console.log(`Sum: ${add(5, 3)}`);
```

**Importing All Exports**
```typescript
// shapes.ts
export const circle = { radius: 5 };
export const square = { side: 5 };

// main.ts
import * as Shapes from './shapes';
console.log(Shapes.circle);
```

## Explanation
While the `import` statement is straightforward, there are several common pitfalls and considerations developers should be aware of:

- **File Extensions**: In TypeScript, you generally do not need to specify the `.ts` or `.js` file extensions when importing. However, ensure that your module resolution strategy is correctly configured in your `tsconfig.json`.
  
- **Circular Dependencies**: Avoid circular dependencies where two modules depend on each other, as this can lead to unpredictable behavior and runtime errors.

- **Type-Only Imports**: Use `import type` when you only need type information, as it helps reduce the bundle size by preventing unnecessary code from being included.

- **ES Modules vs CommonJS**: Ensure that your TypeScript configuration (`tsconfig.json`) is set up to support the desired module system (e.g., `esnext`, `commonjs`) to prevent issues with module resolution.

## One Line Summary
The `import` statement in TypeScript facilitates modular programming by allowing developers to include and utilize code from other files and libraries efficiently.
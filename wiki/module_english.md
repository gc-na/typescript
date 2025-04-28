<!--
Meta Description: # Understanding Modules in TypeScript: A Comprehensive Guide ## Synopsis Modules in TypeScript are a crucial feature that enables developers to organi...
Meta Keywords: typescript, export, module, log, modules
-->

# Understanding Modules in TypeScript: A Comprehensive Guide

## Synopsis
Modules in TypeScript are a crucial feature that enables developers to organize and encapsulate code in a scalable and maintainable way. They allow for the separation of code into distinct files, promoting better code management through encapsulation and reusability.

## Documentation
### What are Modules?
Modules in TypeScript are files that contain code which can be exported and imported in other files. A module can be as simple as a single file or as complex as a directory containing multiple files. TypeScript uses the ES6 module syntax, which promotes the use of `import` and `export` statements.

### Purpose of Modules
The primary purpose of using modules is to avoid global scope pollution by encapsulating code. By organizing code into modules, developers can create reusable components and libraries, making it easier to manage large codebases.

### Usage
To declare a module in TypeScript, you simply create a `.ts` file and use the `export` keyword to expose certain variables, functions, or classes. The `import` statement allows other files to access these exported modules.

#### Example of Exporting
```typescript
// mathUtils.ts
export function add(a: number, b: number): number {
    return a + b;
}

export function subtract(a: number, b: number): number {
    return a - b;
}
```

#### Example of Importing
```typescript
// app.ts
import { add, subtract } from './mathUtils';

console.log(add(5, 3)); // Outputs: 8
console.log(subtract(5, 3)); // Outputs: 2
```

### Types of Module Declarations
1. **Named Exports**: Allow you to export multiple values from a module.
2. **Default Exports**: Allow you to export a single value from a module.

#### Example of Default Export
```typescript
// logger.ts
export default function log(message: string): void {
    console.log(message);
}
```

#### Example of Importing Default Export
```typescript
// app.ts
import log from './logger';

log('This is a log message.'); // Outputs: This is a log message.
```

## Examples
### Example 1: Basic Module Usage
Creating a simple module that exports functions.
```typescript
// greetings.ts
export function greet(name: string): string {
    return `Hello, ${name}!`;
}

// app.ts
import { greet } from './greetings';

console.log(greet('Alice')); // Outputs: Hello, Alice!
```

### Example 2: Using Default Exports
```typescript
// config.ts
const config = {
    apiUrl: 'https://api.example.com',
};

export default config;

// app.ts
import config from './config';

console.log(config.apiUrl); // Outputs: https://api.example.com
```

## Explanation
### Common Pitfalls
1. **File Path Issues**: Ensure that the import path is correct relative to the importing file.
2. **Circular Dependencies**: Be cautious of circular dependencies, as they can lead to unexpected results or runtime errors.
3. **Namespace Conflicts**: When using named exports, ensure that the imported names do not conflict with local variable names.

### Additional Notes
- TypeScript automatically treats each file as a module if it contains at least one `import` or `export` statement.
- The `--module` option in the TypeScript compiler allows you to specify the module system, such as CommonJS or ES6.

## One Line Summary
Modules in TypeScript enhance code organization and reusability by allowing developers to encapsulate and share code across different files.
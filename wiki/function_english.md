<!--
Meta Description: # Understanding Functions in TypeScript: A Comprehensive Guide ## Synopsis Functions in TypeScript are blocks of reusable code that perform a specific...
Meta Keywords: typescript, function, functions, return, number
-->

# Understanding Functions in TypeScript: A Comprehensive Guide

## Synopsis
Functions in TypeScript are blocks of reusable code that perform a specific task. They enable developers to encapsulate logic, improve code organization, and enhance maintainability through strong typing and interfaces.

## Documentation
### Purpose
Functions in TypeScript serve as fundamental building blocks for structuring applications. They allow developers to define reusable code segments that can take inputs, execute logic, and return outputs.

### Usage
In TypeScript, functions can be declared in several ways:

1. **Function Declarations**: The classic way to define a function.
   ```typescript
   function greet(name: string): string {
       return `Hello, ${name}!`;
   }
   ```

2. **Function Expressions**: Functions can also be defined as expressions.
   ```typescript
   const greet = function(name: string): string {
       return `Hello, ${name}!`;
   };
   ```

3. **Arrow Functions**: A compact syntax for writing functions.
   ```typescript
   const greet = (name: string): string => `Hello, ${name}!`;
   ```

4. **Anonymous Functions**: Functions without names, often used as arguments.
   ```typescript
   setTimeout(function() {
       console.log("This runs after 1 second.");
   }, 1000);
   ```

5. **IIFE (Immediately Invoked Function Expressions)**: Functions that execute immediately after declaration.
   ```typescript
   (function() {
       console.log("This runs right away!");
   })();
   ```

### Function Parameters and Return Types
TypeScript allows the specification of parameter types and return types for functions, enhancing type safety. 
```typescript
function add(a: number, b: number): number {
    return a + b;
}
```

### Optional and Default Parameters
TypeScript supports optional parameters and default parameter values.
```typescript
function multiply(a: number, b: number = 1): number {
    return a * b;
}
```

### Rest Parameters
To handle a variable number of arguments, TypeScript provides rest parameters.
```typescript
function sum(...numbers: number[]): number {
    return numbers.reduce((acc, curr) => acc + curr, 0);
}
```

## Examples
### Basic Function Example
```typescript
function square(num: number): number {
    return num * num;
}

console.log(square(5)); // Output: 25
```

### Using Default Parameters
```typescript
function greetUser(name: string, greeting: string = "Hello"): string {
    return `${greeting}, ${name}!`;
}

console.log(greetUser("Alice")); // Output: Hello, Alice!
```

### Using Rest Parameters
```typescript
function logMessages(...messages: string[]): void {
    messages.forEach(msg => console.log(msg));
}

logMessages("First message", "Second message");
```

## Explanation
While using functions in TypeScript, developers may encounter some common pitfalls:

1. **Type Inference**: TypeScript can infer types, but explicitly defining them can prevent unexpected behavior.
2. **Overloading**: TypeScript supports function overloading, but it requires careful management of type signatures.
3. **Scope and Closures**: Understanding scope is crucial, especially when dealing with nested functions and closures, which can lead to unexpected behavior if not handled properly.
4. **Returning `void`**: A function intended to return a value should not be defined with a `void` return type, as this can lead to confusion and errors during development.

## One Line Summary
Functions in TypeScript are defined blocks of reusable code that enhance organization, maintainability, and type safety in applications.
<!--
Meta Description: # Understanding the "if" Statement in TypeScript: A Comprehensive Guide ## Synopsis The "if" statement in TypeScript is a fundamental control flow str...
Meta Keywords: number, typescript, else, code, statement
-->

# Understanding the "if" Statement in TypeScript: A Comprehensive Guide

## Synopsis
The "if" statement in TypeScript is a fundamental control flow structure that enables developers to execute code conditionally based on boolean expressions.

## Documentation
The "if" statement is a crucial component of TypeScript, allowing developers to control the execution of code based on specific conditions. It evaluates a condition (an expression that returns true or false) and executes a block of code if the condition is true. If the condition is false, the code within the block is skipped.

### Syntax
```typescript
if (condition) {
    // Code to execute if condition is true
}
```

### Usage
- **Basic Conditional Execution**: The most straightforward use case of the "if" statement.
- **Else Clause**: You can extend the "if" statement with an "else" clause to execute alternative code when the condition is false.
- **Else If**: For multiple conditions, "else if" can be used to evaluate additional conditions sequentially.

### Syntax with Else and Else If
```typescript
if (condition1) {
    // Code to execute if condition1 is true
} else if (condition2) {
    // Code to execute if condition2 is true
} else {
    // Code to execute if both conditions are false
}
```

## Examples

### Basic Example
```typescript
let number: number = 10;

if (number > 5) {
    console.log("Number is greater than 5");
}
```

### Using Else
```typescript
let number: number = 3;

if (number > 5) {
    console.log("Number is greater than 5");
} else {
    console.log("Number is 5 or less");
}
```

### Using Else If
```typescript
let number: number = 7;

if (number > 10) {
    console.log("Number is greater than 10");
} else if (number > 5) {
    console.log("Number is greater than 5 but less than or equal to 10");
} else {
    console.log("Number is 5 or less");
}
```

## Explanation
While using the "if" statement in TypeScript, it's important to note the following:

- **Type Safety**: TypeScript's type system ensures that the condition used in the "if" statement evaluates to a boolean. If a non-boolean expression is used, TypeScript will throw a compile-time error.
  
- **Short-circuiting**: Logical operators like `&&` (AND) and `||` (OR) can be used within conditions for more complex evaluations. However, be cautious with the logic to avoid unintended outcomes.

- **Scope**: Variables defined within the "if" block are scoped to that block. Be mindful of variable declarations to prevent scope-related issues.

- **Falsy Values**: In TypeScript (as in JavaScript), certain values are considered falsy (e.g., `0`, `null`, `undefined`, `false`, `NaN`, and `""`). Ensure your conditions account for these to avoid unexpected behavior.

## One Line Summary
The "if" statement in TypeScript is a fundamental control flow structure that executes code based on the truthiness of specified conditions.
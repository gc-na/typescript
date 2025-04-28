<!--
Meta Description: # Understanding `var` in TypeScript: A Comprehensive Guide ## Synopsis The `var` keyword in TypeScript is used to declare variables with function scop...
Meta Keywords: var, variable, function, scope, typescript
-->

# Understanding `var` in TypeScript: A Comprehensive Guide

## Synopsis
The `var` keyword in TypeScript is used to declare variables with function scope, allowing for dynamic variable declaration. It is one of the three ways to declare variables in TypeScript, alongside `let` and `const`.

## Documentation
### Purpose
The `var` keyword is a legacy feature inherited from JavaScript, primarily used for declaring variables that can be reassigned. It has function scope, meaning that variables declared with `var` are accessible within the function they are defined in, or globally if declared outside of any function.

### Usage
To declare a variable using `var`, you simply prefix your variable name with the `var` keyword. The variable can be assigned a value immediately or later in the code.

### Details
- **Scope**: Variables declared with `var` are scoped to the nearest function block or global scope if not within a function. This can lead to unexpected behaviors due to hoisting.
- **Hoisting**: `var` declarations are hoisted to the top of their scope, which means that the variable can be referenced before its declaration line in the code.
- **Re-declaration**: You can declare the same variable multiple times using `var` within the same scope without causing an error.

## Examples
### Basic Usage
```typescript
function exampleFunction() {
    var x = 10;
    if (true) {
        var x = 20; // Same variable, function scoped
        console.log(x); // Outputs: 20
    }
    console.log(x); // Outputs: 20
}

exampleFunction();
```

### Global Scope Example
```typescript
var globalVar = "I am global";

function accessGlobal() {
    console.log(globalVar); // Outputs: I am global
}

accessGlobal();
```

## Explanation
### Common Pitfalls
1. **Variable Shadowing**: Since `var` is function-scoped, declaring a variable inside a block (like an `if` statement) does not create a new variable distinct from the one declared outside the block.
2. **Hoisting Confusion**: Because `var` declarations are hoisted, referencing a variable before its declaration may lead to `undefined` instead of a `ReferenceError`. This can create bugs that are hard to trace.
3. **Re-declaration**: Unlike `let` and `const`, `var` allows re-declaring the same variable within the same scope, which can inadvertently lead to overwriting values.

### Additional Notes
- Despite its historical significance, the use of `var` is generally discouraged in favor of `let` and `const`, which provide block scope and prevent some of the pitfalls associated with `var`.
- TypeScript allows the use of `var`, but developers are encouraged to adopt more modern practices for better maintainability and readability.

## One Line Summary
The `var` keyword in TypeScript declares function-scoped variables, allowing for dynamic variable assignment but potentially leading to confusion with hoisting and scope issues.
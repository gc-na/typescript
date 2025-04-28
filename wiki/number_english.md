<!--
Meta Description: # Understanding the "number" Type in TypeScript: A Comprehensive Guide ## Synopsis The `number` type in TypeScript is a fundamental data type that rep...
Meta Keywords: number, type, typescript, let, infinity
-->

# Understanding the "number" Type in TypeScript: A Comprehensive Guide

## Synopsis
The `number` type in TypeScript is a fundamental data type that represents both integer and floating-point numbers, enabling developers to perform arithmetic operations and numerical manipulations with type safety.

## Documentation
### Purpose
In TypeScript, the `number` type is used to define variables that hold numerical values. This type encompasses both whole numbers (integers) and decimal numbers (floating-point). By using the `number` type, TypeScript provides developers with the ability to leverage static typing, enhancing code reliability and clarity.

### Usage
To declare a variable as a `number`, you can use the following syntax:

```typescript
let myNumber: number;
```

You can initialize the variable with a numeric value:

```typescript
let age: number = 30;
let price: number = 19.99;
```

TypeScript automatically infers the type when you assign a value, so explicit typing can be omitted if desired:

```typescript
let temperature = 25; // inferred as number
```

### Details
The `number` type in TypeScript is based on JavaScript's number type, which follows the IEEE 754 standard for double-precision floating-point arithmetic. This means that any number, whether an integer or a floating-point number, can be represented using the `number` type.

- **Special Values**: The `number` type can also represent special numeric values such as:
  - `Infinity` (positive infinity)
  - `-Infinity` (negative infinity)
  - `NaN` (not a number)

### Operations
TypeScript allows you to perform standard arithmetic operations with `number` types:

```typescript
let sum: number = 10 + 5; // result: 15
let product: number = 4 * 2; // result: 8
let division: number = 10 / 2; // result: 5
```

### Type Checking
TypeScript performs type checking to ensure that operations on `number` types are valid:

```typescript
let result: number = "10" + 5; // Error: Type 'string' is not assignable to type 'number'
```

## Examples
### Basic Usage
1. Declaring and assigning a number:
   ```typescript
   let score: number = 100;
   ```

2. Performing arithmetic operations:
   ```typescript
   let a: number = 10;
   let b: number = 20;
   let total: number = a + b; // total is 30
   ```

3. Using special number values:
   ```typescript
   let notANumber: number = NaN; // notANumber is NaN
   let infinity: number = Infinity; // infinity is Infinity
   ```

## Explanation
While the `number` type is versatile, there are some common pitfalls to be aware of:

- **Precision Issues**: Floating-point arithmetic can lead to precision errors due to how numbers are represented in memory. For example:
  ```typescript
  let result = 0.1 + 0.2; // result is 0.30000000000000004
  ```

- **Type Inference Limitations**: If you perform operations between different types, TypeScript may not always infer the resulting type correctly. It’s essential to ensure that all operands are of type `number` to avoid unexpected errors.

- **NaN Comparisons**: The value `NaN` is not equal to itself, which can lead to unexpected behavior in comparisons:
  ```typescript
  console.log(NaN === NaN); // false
  ```

## One Line Summary
The `number` type in TypeScript is a fundamental type used for representing both integers and floating-point numbers, providing type safety for numeric operations.
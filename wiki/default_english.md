<!--
Meta Description: # Understanding the "default" Keyword in TypeScript ## Synopsis The `default` keyword in TypeScript is primarily used in the context of module exports...
Meta Keywords: default, export, case, typescript, module
-->

# Understanding the "default" Keyword in TypeScript

## Synopsis
The `default` keyword in TypeScript is primarily used in the context of module exports and switch statements, facilitating the export of a single entity from a module and providing a default case in conditional statements.

## Documentation
The `default` keyword serves two main purposes in TypeScript:

1. **Default Exports**: It allows you to export a single variable, function, class, or interface as the default export of a module. This enables simpler import syntax and helps to distinguish the primary export of a module.

   ### Syntax for Default Exports
   ```typescript
   // Exporting a function as default
   export default function myFunction() {
       console.log("This is a default exported function.");
   }

   // Exporting a class as default
   export default class MyClass {
       constructor() {
           console.log("This is a default exported class.");
       }
   }
   ```

   ### Importing Default Exports
   When importing a default export, you can choose any name for it:
   ```typescript
   import myFunction from './myModule';
   import MyClass from './myModule';
   ```

2. **Default Case in Switch Statements**: The `default` keyword is used within switch statements to define a block of code that executes if none of the specified case values match.

   ### Syntax for Default Case
   ```typescript
   switch (value) {
       case 'A':
           console.log('A selected');
           break;
       case 'B':
           console.log('B selected');
           break;
       default:
           console.log('No match found');
   }
   ```

## Examples
### Example of Default Export
```typescript
// module.ts
const greeting = "Hello, World!";
export default greeting;

// main.ts
import greeting from './module';
console.log(greeting); // Output: Hello, World!
```

### Example of Default Case in Switch Statement
```typescript
const fruit = 'orange';
switch (fruit) {
    case 'apple':
        console.log('Apple selected');
        break;
    case 'banana':
        console.log('Banana selected');
        break;
    default:
        console.log('Unknown fruit'); // Output: Unknown fruit
}
```

## Explanation
While using the `default` keyword for exports, it's important to remember that a module can have only one default export. If you try to make multiple default exports in the same module, TypeScript will throw an error. 

For switch statements, the `default` case will execute if none of the specified cases are matched, but it’s not mandatory to include it. Omitting the `default` case simply means that no action will be taken if none of the cases match.

### Common Pitfalls:
- **Multiple Default Exports**: Attempting to have more than one default export in a module will lead to a compile-time error.
- **Importing Default Exports**: Ensure that the import statement matches the exported entity correctly; otherwise, you may encounter undefined errors.

## One Line Summary
The `default` keyword in TypeScript is used for defining a primary export from a module and providing a fallback case in switch statements.
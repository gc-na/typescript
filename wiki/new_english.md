<!--
Meta Description: # Understanding the "new" Keyword in TypeScript: A Comprehensive Guide ## Synopsis The `new` keyword in TypeScript is utilized to create instances of ...
Meta Keywords: new, constructor, object, class, typescript
-->

# Understanding the "new" Keyword in TypeScript: A Comprehensive Guide

## Synopsis
The `new` keyword in TypeScript is utilized to create instances of classes or to invoke constructor functions, enabling object-oriented programming in a type-safe manner.

## Documentation
The `new` keyword is an essential part of object creation in TypeScript, which is a superset of JavaScript. It allows developers to create new objects based on a class or a constructor function.

### Purpose
The primary purpose of the `new` keyword is to instantiate a class. When used, it performs the following actions:

1. **Creates a new object**: An empty object is created.
2. **Sets the prototype**: The prototype of the newly created object is set to the constructor’s prototype.
3. **Binds `this`**: The `this` keyword within the constructor function is bound to the new object.
4. **Returns the object**: If the constructor function does not explicitly return an object, the newly created object is returned by default.

### Usage
The syntax for using the `new` keyword is straightforward:

```typescript
const instance = new ClassName(parameters);
```

### Details
- **Class Declaration**: In TypeScript, classes can be declared using the `class` keyword, and constructors can be defined with the `constructor` method.
- **Type Safety**: TypeScript provides static typing, allowing developers to specify types for class properties and constructor parameters.
- **Inheritance**: Classes can extend other classes, allowing the reuse of properties and methods.

## Examples

### Basic Class Instantiation
```typescript
class Person {
    constructor(public name: string, public age: number) {}
}

const john = new Person("John Doe", 30);
console.log(john.name); // Output: John Doe
```

### Using Constructors with Default Parameters
```typescript
class Car {
    constructor(public make: string, public model: string, public year: number = 2020) {}
}

const myCar = new Car("Toyota", "Corolla");
console.log(myCar.year); // Output: 2020
```

### Inheritance with `new`
```typescript
class Animal {
    constructor(public name: string) {}
}

class Dog extends Animal {
    bark() {
        return `${this.name} says woof!`;
    }
}

const myDog = new Dog("Buddy");
console.log(myDog.bark()); // Output: Buddy says woof!
```

## Explanation
While using the `new` keyword is straightforward, there are a few common pitfalls to be aware of:

1. **Not Calling with `new`**: If a constructor function is called without `new`, it may lead to unexpected behavior, as `this` will not refer to the new instance.
   ```typescript
   const person = Person("Jane Doe", 25); // Incorrect usage
   ```
   This will not create a new instance of `Person` and will result in `this` being undefined.

2. **Return Value**: If a constructor explicitly returns a non-object value (like a number or string), that value will be ignored, and the newly created object will be returned instead.

3. **Static Methods**: The `new` keyword cannot be used with static methods of a class. Static methods are called on the class itself, not on instances.

4. **Abstract Classes**: You cannot instantiate abstract classes directly with `new`. Attempting to do so will result in a compilation error.

## One Line Summary
The `new` keyword in TypeScript is used to create instances of classes, ensuring that the object's constructor is called and the prototype is properly set.
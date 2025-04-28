<!--
Meta Description: # Understanding "super" in TypeScript: A Comprehensive Guide ## Synopsis The `super` keyword in TypeScript is used to access properties and methods fr...
Meta Keywords: class, super, constructor, parent, method
-->

# Understanding "super" in TypeScript: A Comprehensive Guide

## Synopsis
The `super` keyword in TypeScript is used to access properties and methods from a parent class within a derived class, facilitating inheritance and method overriding.

## Documentation
### Purpose
The `super` keyword allows developers to call methods and access properties from a parent class. It is essential in object-oriented programming within TypeScript, enabling code reuse and the creation of more complex structures through inheritance.

### Usage
- **In Constructor**: The `super()` function must be called in the constructor of a derived class before you can use `this`.
- **In Methods**: You can use `super.methodName()` to call a method from the parent class.

### Details
- The `super` keyword can only be used within a class that extends another class.
- It is commonly used to invoke the constructor of the base class as well as to access or override methods and properties.

## Examples
### Basic Example of Using `super` in a Constructor
```typescript
class Animal {
    constructor(public name: string) {
        console.log(`${this.name} is an animal.`);
    }

    sound() {
        console.log(`${this.name} makes a sound.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name); // Calls the constructor of Animal
        console.log(`${this.name} is a dog.`);
    }

    sound() {
        super.sound(); // Calls the sound method of Animal
        console.log(`${this.name} barks.`);
    }
}

const dog = new Dog('Buddy');
dog.sound();
```

### Example of Accessing Parent Class Methods
```typescript
class Shape {
    area(): number {
        return 0;
    }
}

class Circle extends Shape {
    radius: number;

    constructor(radius: number) {
        super(); // Calls the constructor of Shape
        this.radius = radius;
    }

    area(): number {
        return super.area() + Math.PI * this.radius * this.radius; // Accessing the area method of Shape
    }
}

const circle = new Circle(5);
console.log(`Area of circle: ${circle.area()}`);
```

## Explanation
### Common Pitfalls
1. **Missing `super()` Call**: Failing to call `super()` in a derived class constructor will result in a runtime error. Always ensure the parent class constructor is invoked first.
2. **Accessing `this` Before `super()`**: You cannot use `this` before calling `super()`, as the object has not been fully constructed yet.
3. **Method Overriding**: When overriding methods, ensure the method signature matches the parent class method to avoid type errors.

### Gotchas
- The `super` keyword is not available in object literals or standalone functions; it must be used within a class context.
- Using `super` with private or protected members of the parent class may lead to access errors if not handled properly.

## One Line Summary
The `super` keyword in TypeScript enables access to parent class properties and methods, facilitating inheritance and method overriding in object-oriented programming.
<!--
Meta Description: # Understanding "protected" in TypeScript: Access Modifiers Explained ## Synopsis In TypeScript, `protected` is an access modifier that restricts the ...
Meta Keywords: protected, class, access, typescript, subclasses
-->

# Understanding "protected" in TypeScript: Access Modifiers Explained

## Synopsis
In TypeScript, `protected` is an access modifier that restricts the visibility of class properties and methods, allowing them to be accessed within the class itself and by subclasses, but not by instances of the class.

## Documentation
### Purpose
The `protected` access modifier is used to define members of a class that should not be accessible from outside the class, except by derived (subclass) classes. This is especially useful in object-oriented programming where inheritance is involved, allowing for controlled access to class internals while still enabling subclasses to utilize and override them.

### Usage
To declare a member as `protected`, simply prefix it with the `protected` keyword in the class definition. This can be applied to properties, methods, and constructors.

```typescript
class BaseClass {
    protected protectedProperty: string;

    constructor(value: string) {
        this.protectedProperty = value;
    }

    protected protectedMethod(): void {
        console.log("This is a protected method.");
    }
}

class DerivedClass extends BaseClass {
    public showProtectedProperty(): void {
        console.log(this.protectedProperty); // Accessible
    }

    public callProtectedMethod(): void {
        this.protectedMethod(); // Accessible
    }
}

const baseInstance = new BaseClass("Hello");
// baseInstance.protectedProperty; // Error: Property 'protectedProperty' is protected
// baseInstance.protectedMethod(); // Error: Method 'protectedMethod' is protected

const derivedInstance = new DerivedClass("Hello");
derivedInstance.showProtectedProperty(); // Output: Hello
derivedInstance.callProtectedMethod(); // Output: This is a protected method.
```

### Details
- **Inheritance**: The primary benefit of using `protected` is in a class hierarchy where you want to expose certain properties and methods to subclasses while keeping them hidden from the outside world.
- **Constructor Access**: `protected` can also be used with constructors, which allows derived classes to call the constructor of the base class while preventing direct instantiation of the base class.
- **Compatibility with `private`**: Unlike `private`, which restricts access to the defining class only, `protected` allows subclasses to access the protected members.

## Examples
1. **Basic Example of protected Property:**
   ```typescript
   class Animal {
       protected name: string;

       constructor(name: string) {
           this.name = name;
       }
   }

   class Dog extends Animal {
       public bark(): void {
           console.log(`${this.name} says woof!`);
       }
   }

   const dog = new Dog("Rex");
   dog.bark(); // Output: Rex says woof!
   // console.log(dog.name); // Error: Property 'name' is protected
   ```

2. **Using protected Methods:**
   ```typescript
   class Shape {
       protected draw(): void {
           console.log("Drawing shape");
       }
   }

   class Circle extends Shape {
       public drawCircle(): void {
           this.draw(); // Accessible
           console.log("Drawing circle");
       }
   }

   const circle = new Circle();
   circle.drawCircle(); // Output: Drawing shape \n Drawing circle
   // circle.draw(); // Error: Method 'draw' is protected
   ```

## Explanation
### Common Pitfalls
- **Misunderstanding Access**: A common error is assuming that `protected` members are accessible from outside the class. They are only accessible within the class and its subclasses.
- **Abstract Classes**: When using `protected` in abstract classes, ensure that derived classes implement any abstract methods that are declared as `protected`.
- **No Instantiation**: You cannot create instances of a class with a `protected` constructor, which can lead to confusion if not understood properly.

### Additional Notes
- The `protected` modifier is particularly useful in frameworks and libraries where you may want to expose certain functionalities to subclasses without exposing them to the public API.
- TypeScript also allows you to use `public` and `private` alongside `protected` for fine-grained control over member access.

## One Line Summary
In TypeScript, `protected` is an access modifier that allows class members to be accessible within the class and its subclasses, enforcing encapsulation while enabling inheritance.
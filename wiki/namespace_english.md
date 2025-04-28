<!--
Meta Description: # Understanding Namespaces in TypeScript: A Comprehensive Guide ## Synopsis Namespaces in TypeScript provide a way to organize code into logical group...
Meta Keywords: namespaces, namespace, typescript, number, side
-->

# Understanding Namespaces in TypeScript: A Comprehensive Guide

## Synopsis
Namespaces in TypeScript provide a way to organize code into logical groups, enabling better management of larger codebases. They help avoid naming conflicts and enhance code modularity.

## Documentation
### Purpose
Namespaces are a TypeScript feature designed to encapsulate a set of related functionalities. They allow developers to group variables, functions, interfaces, and classes under a single namespace, effectively preventing naming collisions between different parts of an application. This is especially useful in larger projects or when integrating multiple libraries.

### Usage
Namespaces can be declared using the `namespace` keyword followed by a name. Contents of the namespace can be accessed using dot notation. To use a namespace, simply define it in your TypeScript file, and then reference its members as needed.

### Details
- **Declaration**: Use the `namespace` keyword followed by the desired name.
- **Accessing Members**: Members of the namespace can be accessed using the namespace name followed by a dot and the member name.
- **Nested Namespaces**: TypeScript supports nested namespaces, allowing for even finer organization of code.
- **Modules vs. Namespaces**: While namespaces are useful for organizing code within a single file or related files, TypeScript modules (using ES6 module syntax) are preferred for managing dependencies and code across different files. Namespaces are more common in older TypeScript codebases.

## Examples
### Basic Usage
```typescript
namespace Shapes {
    export class Circle {
        radius: number;
        constructor(radius: number) {
            this.radius = radius;
        }
        area() {
            return Math.PI * this.radius ** 2;
        }
    }

    export class Square {
        side: number;
        constructor(side: number) {
            this.side = side;
        }
        area() {
            return this.side ** 2;
        }
    }
}

const circle = new Shapes.Circle(5);
console.log(`Circle Area: ${circle.area()}`);

const square = new Shapes.Square(4);
console.log(`Square Area: ${square.area()}`);
```

### Nested Namespaces
```typescript
namespace Geometry {
    export namespace TwoD {
        export class Rectangle {
            width: number;
            height: number;
            constructor(width: number, height: number) {
                this.width = width;
                this.height = height;
            }
            area() {
                return this.width * this.height;
            }
        }
    }

    export namespace ThreeD {
        export class Cube {
            side: number;
            constructor(side: number) {
                this.side = side;
            }
            volume() {
                return this.side ** 3;
            }
        }
    }
}

const rectangle = new Geometry.TwoD.Rectangle(10, 5);
console.log(`Rectangle Area: ${rectangle.area()}`);

const cube = new Geometry.ThreeD.Cube(3);
console.log(`Cube Volume: ${cube.volume()}`);
```

## Explanation
- **Common Pitfalls**: 
  - Forgetting to use the `export` keyword will make members of the namespace inaccessible from outside. Always remember to export members you want to use elsewhere.
  - Using namespaces in conjunction with ES6 modules can lead to confusion. It's advisable to choose one organizational pattern for better clarity.
  
- **Gotchas**: 
  - Namespaces can lead to a cluttered global scope when not used carefully. It's recommended to encapsulate namespaces within modules whenever possible.
  - TypeScript's behavior with namespaces can differ based on the compilation target (e.g., `CommonJS`, `ES6`), so understanding your target is crucial.

## One Line Summary
Namespaces in TypeScript offer a structured approach to organize code and avoid naming conflicts in larger applications.
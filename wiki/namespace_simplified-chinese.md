<!--
Meta Description: # TypeScript 命名空间（namespace）详解 ## 摘要 TypeScript 的命名空间（namespace）用于将相关的代码组织在一起，以避免全局作用域的污染。它提供了一种结构化的方式来管理大型应用程序中的模块。 ## 文档 命名空间是 TypeScript 中的一种代码组织方式...
Meta Keywords: typescript, namespace, export, mynamespace, console
-->

# TypeScript 命名空间（namespace）详解

## 摘要
TypeScript 的命名空间（namespace）用于将相关的代码组织在一起，以避免全局作用域的污染。它提供了一种结构化的方式来管理大型应用程序中的模块。

## 文档
命名空间是 TypeScript 中的一种代码组织方式，它允许开发者将相关的变量、函数和类封装在一个逻辑上相关的组中。命名空间可以帮助避免命名冲突，并提高代码的可读性和可维护性。

### 目的
- **组织代码**：将相关的代码放在一起，便于管理。
- **避免命名冲突**：通过将代码封装在命名空间中，可以避免与其他代码的命名冲突。
- **提高可读性**：清晰的结构使得代码更易于理解。

### 使用
使用命名空间时，您需要使用 `namespace` 关键字来定义一个命名空间，接着可以在其中声明变量、函数、类等。例如：

```typescript
namespace MyNamespace {
    export class MyClass {
        constructor(public name: string) {}
        greet() {
            return `Hello, ${this.name}!`;
        }
    }

    export function myFunction() {
        return 'This is a function in MyNamespace';
    }
}
```

要使用命名空间中的成员，您可以使用点符号访问，例如：

```typescript
const instance = new MyNamespace.MyClass('TypeScript');
console.log(instance.greet()); // 输出: Hello, TypeScript!
console.log(MyNamespace.myFunction()); // 输出: This is a function in MyNamespace
```

## 示例
以下是一个简单的命名空间示例：

```typescript
namespace Geometry {
    export class Circle {
        constructor(public radius: number) {}

        area() {
            return Math.PI * this.radius ** 2;
        }
    }

    export class Square {
        constructor(public side: number) {}

        area() {
            return this.side ** 2;
        }
    }
}

const circle = new Geometry.Circle(5);
console.log(circle.area()); // 输出: 78.53981633974483

const square = new Geometry.Square(4);
console.log(square.area()); // 输出: 16
```

## 解释
在使用命名空间时，有几个常见的注意事项：

- **导出成员**：只有使用 `export` 关键字声明的成员才能在命名空间外部访问。
- **与模块的区别**：命名空间和 ES6 模块的概念有所不同。命名空间主要用于组织代码，而 ES6 模块则是处理依赖关系和模块化。
- **嵌套命名空间**：命名空间可以嵌套，允许更细粒度的组织。例如：

```typescript
namespace A {
    export namespace B {
        export const value = 42;
    }
}

console.log(A.B.value); // 输出: 42
```

- **避免使用全局命名空间**：尽量避免在全局作用域中暴露命名空间，建议将其限制在模块中。

## 一句话总结
TypeScript 的命名空间（namespace）是一种有效的代码组织工具，帮助开发者管理和避免命名冲突。
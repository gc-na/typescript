<!--
Meta Description: # TypeScript 中的 "protected" 关键字详解 ## 概述 在 TypeScript 中，`protected` 是一种访问修饰符，用于控制类属性和方法的访问权限。它使得某些成员只能在类内部及其子类中访问，从而增强了封装性。 ## 文档 ### 目的 `protected` 关键...
Meta Keywords: protected, typescript, string, derived, name
-->

# TypeScript 中的 "protected" 关键字详解

## 概述
在 TypeScript 中，`protected` 是一种访问修饰符，用于控制类属性和方法的访问权限。它使得某些成员只能在类内部及其子类中访问，从而增强了封装性。

## 文档
### 目的
`protected` 关键字的主要目的是限制对类成员的访问，使得这些成员不能被类的实例直接访问，但可以在类的子类中访问。这对于构建具有继承关系的类时特别有用，确保了子类可以访问其父类中的关键成员。

### 用法
在 TypeScript 中，可以通过在类成员前添加 `protected` 关键字来声明受保护的属性或方法。例如：

```typescript
class Base {
    protected message: string;

    constructor(msg: string) {
        this.message = msg;
    }

    protected showMessage(): void {
        console.log(this.message);
    }
}

class Derived extends Base {
    public display(): void {
        this.showMessage();  // 可以访问父类中的受保护方法
    }
}

const derived = new Derived("Hello, World!");
derived.display();  // 输出: Hello, World!
// derived.showMessage(); // 错误：不能访问受保护的方法
```

### 详细说明
- **访问权限**: `protected` 成员可以被其定义的类和所有子类访问，但不能被类的实例直接访问。
- **继承**: 当一个类继承自另一个类时，它可以访问父类中声明为 `protected` 的成员，这使得子类能够重用父类的功能。
- **构造函数**: 在构造函数中，`protected` 成员可以被赋值，但不能被实例化类直接访问。

## 示例
### 基本用法示例
以下是一个简单的示例，展示了如何使用 `protected` 关键字：

```typescript
class Animal {
    protected name: string;

    constructor(name: string) {
        this.name = name;
    }

    protected speak(): string {
        return `${this.name} makes a noise.`;
    }
}

class Dog extends Animal {
    public bark(): void {
        console.log(this.speak()); // 可以访问父类的受保护方法
    }
}

const dog = new Dog("Buddy");
dog.bark(); // 输出: Buddy makes a noise.
// dog.speak(); // 错误：不能访问受保护的方法
```

## 说明
- **常见问题**: 使用 `protected` 时，开发者可能会忘记在子类中使用父类的受保护成员，导致编译错误。
- **与 `private` 的区别**: `protected` 与 `private` 的主要区别在于，`private` 成员只能在定义它的类内访问，而 `protected` 成员可以在子类中访问。
- **设计考量**: 使用 `protected` 可以帮助开发者设计更具可扩展性的类结构，但过度依赖可能导致代码难以维护。

## 一句话总结
在 TypeScript 中，`protected` 关键字用于限制类成员的访问权限，使其只能在类及其子类内被访问。
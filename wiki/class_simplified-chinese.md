<!--
Meta Description: # TypeScript 中的类：深入了解与应用 ## 摘要 在 TypeScript 中，类是面向对象编程的核心概念，提供了一种创建对象的蓝图，支持继承和封装等特性。 ## 文档 类是 TypeScript 中的一个重要特性，它允许开发者通过定义类来创建对象的结构和行为。使用类，您可以定义属性和方...
Meta Keywords: typescript, class, name, public, string
-->

# TypeScript 中的类：深入了解与应用

## 摘要
在 TypeScript 中，类是面向对象编程的核心概念，提供了一种创建对象的蓝图，支持继承和封装等特性。

## 文档
类是 TypeScript 中的一个重要特性，它允许开发者通过定义类来创建对象的结构和行为。使用类，您可以定义属性和方法，并可以通过实例化类来创建对象。TypeScript 的类不仅支持传统的面向对象编程特性，还提供了类型检查，使得代码更加安全和可维护。

### 定义类
在 TypeScript 中，可以使用 `class` 关键字定义一个类。基本语法如下：

```typescript
class ClassName {
    // 属性
    propertyName: type;

    // 构造函数
    constructor(parameters) {
        // 初始化属性
    }

    // 方法
    methodName(parameters): returnType {
        // 方法逻辑
    }
}
```

### 继承
TypeScript 支持类的继承，允许一个类从另一个类继承属性和方法。使用 `extends` 关键字来实现：

```typescript
class ParentClass {
    // 父类属性和方法
}

class ChildClass extends ParentClass {
    // 子类特有的属性和方法
}
```

### 访问修饰符
TypeScript 提供了三种访问修饰符：`public`、`private` 和 `protected`。这些修饰符控制类的属性和方法的可访问性。

- `public`: 默认修饰符，类外部和内部都可以访问。
- `private`: 仅能在类内部访问。
- `protected`: 仅能在类内部和子类中访问。

## 示例
以下是一个简单的类定义及其使用示例：

```typescript
class Animal {
    public name: string;

    constructor(name: string) {
        this.name = name;
    }

    public speak(): string {
        return `${this.name} makes a noise.`;
    }
}

class Dog extends Animal {
    public speak(): string {
        return `${this.name} barks.`;
    }
}

const dog = new Dog('Rex');
console.log(dog.speak()); // 输出: Rex barks.
```

## 说明
在使用 TypeScript 类时，开发者可能会遇到一些常见的陷阱和注意事项：

1. **构造函数中的属性初始化**：确保在构造函数中初始化所有属性，否则可能导致运行时错误。
2. **访问修饰符的选择**：选择合适的访问修饰符对于保护类的内部状态至关重要。
3. **继承链中的构造函数调用**：在子类中使用 `super()` 调用父类的构造函数，确保父类的属性得到正确初始化。

## 一句话总结
TypeScript 中的类提供了一种结构化的方式来创建对象，支持继承和访问控制，使得代码更具可读性和可维护性。
<!--
Meta Description: # TypeScript 中的 static 关键字详解 ## 概述 在 TypeScript 中，`static` 关键字用于定义类的静态属性和方法。静态成员属于类本身而非类的实例，这意味着它们可以直接通过类名访问，而不需要创建类的实例。静态成员常用于封装与类相关的工具函数或常量。 ## 文档 `...
Meta Keywords: static, typescript, counter, count, number
-->

# TypeScript 中的 static 关键字详解

## 概述
在 TypeScript 中，`static` 关键字用于定义类的静态属性和方法。静态成员属于类本身而非类的实例，这意味着它们可以直接通过类名访问，而不需要创建类的实例。静态成员常用于封装与类相关的工具函数或常量。

## 文档
`static` 关键字可以在类的定义中使用，用于声明静态属性或静态方法。静态成员在内存中只存在一份，不会随着类的实例化而重复创建。以下是 `static` 的主要用途和使用方法：

- **声明静态属性**: 使用 `static` 关键字可以声明一个类的属性，该属性对于所有实例都是共享的。
- **声明静态方法**: 同样，使用 `static` 关键字可以定义一个方法，该方法可以直接通过类名调用，而无需实例化类。

### 语法
```typescript
class ClassName {
    static staticProperty: type;
    
    static staticMethod(parameters): returnType {
        // 方法实现
    }
}
```

## 示例
以下是一些简单的示例，展示如何在 TypeScript 中使用 `static` 关键字。

### 示例 1: 静态属性
```typescript
class Counter {
    static count: number = 0;
    
    static increment() {
        this.count++;
    }
}

Counter.increment();
console.log(Counter.count); // 输出: 1
```

### 示例 2: 静态方法
```typescript
class MathUtil {
    static add(a: number, b: number): number {
        return a + b;
    }
}

console.log(MathUtil.add(5, 3)); // 输出: 8
```

## 说明
使用 `static` 关键字时需注意以下几点：

1. **无法通过实例访问**: 静态成员无法通过类的实例访问，只能通过类名访问。例如，`const counter = new Counter(); counter.count;` 将会产生错误。
2. **共享状态**: 所有实例共享静态属性的值，修改静态属性会影响到所有实例。
3. **静态方法和属性的限制**: 静态方法无法访问类的实例成员（如非静态属性和方法），因为它们不依赖于实例。

## 一句话总结
`static` 关键字在 TypeScript 中用于定义属于类本身的静态属性和方法，允许直接通过类名进行访问。
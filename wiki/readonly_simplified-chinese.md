<!--
Meta Description: # TypeScript中的readonly修饰符详解 ## 摘要 `readonly`是TypeScript中的一个修饰符，用于限制对象属性的可写性，从而增强代码的安全性和可维护性。 ## 文档 在TypeScript中，`readonly`修饰符用于定义只读属性。这意味着一旦属性被赋值，就不能再...
Meta Keywords: readonly, name, number, user, string
-->

# TypeScript中的readonly修饰符详解

## 摘要
`readonly`是TypeScript中的一个修饰符，用于限制对象属性的可写性，从而增强代码的安全性和可维护性。

## 文档
在TypeScript中，`readonly`修饰符用于定义只读属性。这意味着一旦属性被赋值，就不能再被修改。这在处理不可变对象时非常有用，比如在Redux等状态管理库中。

### 目的
`readonly`的主要目的是保护对象的某些属性不被意外修改，从而防止潜在的错误和不一致性。

### 用法
要使用`readonly`，只需在属性声明前加上`readonly`关键字。例如：

```typescript
class User {
    readonly name: string;
    readonly age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
}
```

在这个例子中，`name`和`age`属性都是只读的，不能在类的外部或内部被修改。

### 注意事项
- `readonly`修饰符只能用于属性声明，不能用于方法或函数参数。
- 对于数组和对象的嵌套属性，`readonly`只会影响最外层的属性，内部的属性仍然可以被修改。

## 示例
以下是一些基本的使用示例：

### 示例1：只读属性
```typescript
class Point {
    readonly x: number;
    readonly y: number;

    constructor(x: number, y: number) {
        this.x = x;
        this.y = y;
    }
}

const point = new Point(10, 20);
console.log(point.x); // 输出: 10
// point.x = 15; // 错误: 无法分配到 "x" ，因为它是只读属性。
```

### 示例2：只读数组
```typescript
const numbers: readonly number[] = [1, 2, 3];
// numbers[0] = 10; // 错误: 无法分配到 "0" ，因为它是只读属性。
```

### 示例3：嵌套只读属性
```typescript
interface User {
    readonly name: string;
    readonly address: {
        readonly city: string;
        readonly country: string;
    };
}

const user: User = {
    name: "Alice",
    address: {
        city: "Beijing",
        country: "China"
    }
};

// user.name = "Bob"; // 错误: 不能修改只读属性
// user.address.city = "Shanghai"; // 允许修改，因为`city`不是只读属性
```

## 说明
使用`readonly`时需注意以下几点：
- 尽管你不能修改只读属性，但是如果只读属性是对象或数组，内部的状态仍然可以被更改。
- `readonly`属性在类的构造函数中可以被赋值，但在构造函数外部将无法修改。
- 在函数参数中使用`readonly`修饰符可以防止对对象或数组参数的意外修改。

## 一句话总结
`readonly`修饰符在TypeScript中用于定义只读属性，以增强代码的安全性和可维护性。
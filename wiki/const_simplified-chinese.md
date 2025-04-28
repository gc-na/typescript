<!--
Meta Description: # TypeScript 中的 const：常量声明的最佳实践 ## 概述 在 TypeScript 中，`const` 是用于声明常量的关键字。与 `let` 和 `var` 不同，使用 `const` 声明的变量必须在声明时初始化，并且其值在后续代码中不能被重新赋值。 ## 文档 `const`...
Meta Keywords: const, typescript, console, log, person
-->

# TypeScript 中的 const：常量声明的最佳实践

## 概述
在 TypeScript 中，`const` 是用于声明常量的关键字。与 `let` 和 `var` 不同，使用 `const` 声明的变量必须在声明时初始化，并且其值在后续代码中不能被重新赋值。

## 文档
`const` 关键字的主要目的是提供一种方式来定义一个只读的常量。这意味着一旦常量被赋值，就不能再改变其引用。`const` 在 TypeScript 中的使用与 JavaScript 类似，主要用于声明不需要改变的值。

### 用法
- **声明常量**：使用 `const` 声明常量时，必须立即初始化。
- **作用域**：`const` 的作用域与 `let` 相同，都是块级作用域。
- **对象和数组**：虽然 `const` 声明的变量不能指向不同的对象或数组，但可以修改对象的属性或数组的元素。

### 语法
```typescript
const variableName: type = value;
```

## 示例
以下是 `const` 的基本用法示例：

### 示例 1：基本常量
```typescript
const pi: number = 3.14;
console.log(pi); // 输出: 3.14
```

### 示例 2：对象常量
```typescript
const person = { name: "Alice", age: 25 };
console.log(person.name); // 输出: Alice

// 可以修改对象的属性
person.age = 26;
console.log(person.age); // 输出: 26

// 但不能重新赋值
// person = { name: "Bob", age: 30 }; // 错误：无法重新赋值
```

### 示例 3：数组常量
```typescript
const numbers: number[] = [1, 2, 3];
console.log(numbers); // 输出: [1, 2, 3]

// 可以修改数组的元素
numbers[0] = 10;
console.log(numbers); // 输出: [10, 2, 3]

// 但不能重新赋值
// numbers = [4, 5, 6]; // 错误：无法重新赋值
```

## 说明
使用 `const` 时常见的误区包括：
- 误以为 `const` 声明的对象是不可变的。实际上，您可以修改对象的属性或数组的内容。
- 忘记在声明时初始化 `const` 变量，会导致编译错误。
- 试图重新赋值 `const` 变量，将导致运行时错误。

### 注意事项
- 如果需要一个可以改变的值，应该使用 `let` 或 `var`。
- 在 ES6 及以上版本中，推荐优先使用 `const` 来声明常量，以提高代码的可读性和可维护性。

## 一句话总结
`const` 是 TypeScript 中用于声明不可重新赋值的常量，适用于定义只读变量。
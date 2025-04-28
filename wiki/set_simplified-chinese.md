<!--
Meta Description: # TypeScript 中的 Set：类型安全的集合 ## 概述 在 TypeScript 中，`Set` 是一种用于存储唯一值的数据结构。它允许我们存储不重复的元素，并提供了丰富的方法来操作这些元素，非常适合处理集合操作。 ## 文档 `Set` 是 JavaScript ES6 引入的一个数据...
Meta Keywords: set, numbers, typescript, console, log
-->

# TypeScript 中的 Set：类型安全的集合

## 概述
在 TypeScript 中，`Set` 是一种用于存储唯一值的数据结构。它允许我们存储不重复的元素，并提供了丰富的方法来操作这些元素，非常适合处理集合操作。

## 文档
`Set` 是 JavaScript ES6 引入的一个数据结构，TypeScript 作为 JavaScript 的超集，完全支持 `Set`。使用 `Set`，我们可以确保集合中的每个值都是唯一的，这对于避免重复数据非常有用。

### 目的
- 存储唯一值
- 提供高效的查找、添加和删除操作

### 用法
要使用 `Set`，可以通过构造函数进行初始化，支持传入可迭代对象（如数组）作为初始值。

```typescript
const mySet = new Set<number>([1, 2, 3]);
```

### 主要方法
- `add(value)`: 添加一个新元素到集合中。
- `delete(value)`: 从集合中删除指定元素。
- `has(value)`: 检查集合是否包含指定元素。
- `clear()`: 清空集合。
- `size`: 返回集合的元素数量。
- `forEach(callback)`: 对集合中的每个元素执行指定的回调。

## 示例
以下是使用 `Set` 的一些基本示例：

```typescript
// 创建一个 Set
const numbers = new Set<number>();

// 添加元素
numbers.add(1);
numbers.add(2);
numbers.add(3);
numbers.add(2); // 不会添加重复的元素

console.log(numbers.size); // 输出: 3

// 检查元素
console.log(numbers.has(2)); // 输出: true
console.log(numbers.has(4)); // 输出: false

// 删除元素
numbers.delete(2);
console.log(numbers.has(2)); // 输出: false

// 遍历元素
numbers.forEach(num => {
    console.log(num); // 输出: 1, 3
});

// 清空集合
numbers.clear();
console.log(numbers.size); // 输出: 0
```

## 说明
在使用 `Set` 时，一些常见的陷阱和注意事项包括：
- 值的比较是基于引用的，对于对象或数组，两个不同的实例即使内容相同，也会被视为不同的元素。
- `Set` 中的元素是按插入顺序排列的，但不保证顺序可以被直接访问。
- 使用 `Set` 处理基本数据类型（如字符串、数字）时，比较是基于值的。

## 一句话总结
`Set` 是 TypeScript 中一个强大且灵活的集合类型，用于存储唯一值并提供高效的集合操作。
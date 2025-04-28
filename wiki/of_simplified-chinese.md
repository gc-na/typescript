<!--
Meta Description: # TypeScript 中的 "of" 关键字详解 ## 概述 在 TypeScript 中，"of" 是一个用于提取和处理对象、数组和集合的关键字，特别是在映射和遍历数据结构时非常有用。 ## 文档 "of" 关键字通常与 `for...of` 循环结合使用，用于遍历可迭代对象（如数组、字符串、...
Meta Keywords: typescript, const, num, item, set
-->

# TypeScript 中的 "of" 关键字详解

## 概述
在 TypeScript 中，"of" 是一个用于提取和处理对象、数组和集合的关键字，特别是在映射和遍历数据结构时非常有用。

## 文档
"of" 关键字通常与 `for...of` 循环结合使用，用于遍历可迭代对象（如数组、字符串、集合等）。它允许开发者以简洁的方式访问集合中的每一项。

### 用途
- 提供了一种简洁的方式来遍历数组和其他可迭代对象。
- 使代码更具可读性，减少传统 `for` 循环的复杂性。

### 语法
```typescript
for (const item of iterable) {
    // 处理 item
}
```

### 参数
- `item`：当前迭代的项。
- `iterable`：一个可迭代对象，如数组、字符串、Map、Set 等。

## 示例
### 示例 1：遍历数组
```typescript
const numbers = [1, 2, 3, 4, 5];
for (const num of numbers) {
    console.log(num); // 输出 1, 2, 3, 4, 5
}
```

### 示例 2：遍历字符串
```typescript
const greeting = "Hello";
for (const char of greeting) {
    console.log(char); // 输出 H, e, l, l, o
}
```

### 示例 3：遍历 Set
```typescript
const uniqueNumbers = new Set([1, 2, 3, 4, 5]);
for (const num of uniqueNumbers) {
    console.log(num); // 输出 1, 2, 3, 4, 5
}
```

## 说明
在使用 "of" 的过程中，有几个常见的注意事项：
- `for...of` 不适用于普通对象（即没有实现可迭代接口的对象），尝试对普通对象使用 `for...of` 会抛出错误。
- 如果需要遍历对象的属性，应该使用 `for...in` 循环，而不是 `for...of`。
- 在处理大型数组时，`for...of` 循环的性能可能会稍微低于传统的 `for` 循环，特别是在性能敏感的场景中。

## 一句话总结
"of" 关键字通过 `for...of` 循环为 TypeScript 提供了一种简单且高效的方式来遍历可迭代对象。
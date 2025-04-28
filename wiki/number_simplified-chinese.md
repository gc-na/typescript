<!--
Meta Description: # TypeScript 中的 Number 数据类型详解 ## 概述 在 TypeScript 中，“number” 是一种基本数据类型，用于表示数值。它不仅支持整数和浮点数，还可以处理特殊值如 NaN 和 Infinity。 ## 文档 ### 目的 “number” 类型用于表示数值，支持数学...
Meta Keywords: number, typescript, let, nan, infinity
-->

# TypeScript 中的 Number 数据类型详解

## 概述
在 TypeScript 中，“number” 是一种基本数据类型，用于表示数值。它不仅支持整数和浮点数，还可以处理特殊值如 NaN 和 Infinity。

## 文档
### 目的
“number” 类型用于表示数值，支持数学计算和各种数值操作。TypeScript 的“number”类型与 JavaScript 的数字类型一致，提供了丰富的数值处理能力。

### 用法
在 TypeScript 中，声明一个“number”类型的变量可以使用以下语法：

```typescript
let num: number = 42;
let pi: number = 3.14;
```

您还可以使用数值字面量、数学运算、函数返回值等来赋值给“number”类型变量。以下是一些常见的使用场景：

- 算术运算
- 数学函数调用
- 数值比较

### 细节
1. **整数和浮点数**: TypeScript 中的“number”类型可以表示整数和浮点数，且无论是整数还是浮点数，底层都是以双精度浮点格式存储。
2. **特殊值**: “number” 类型还支持一些特殊值，包括：
   - `NaN`（不是一个数字）
   - `Infinity`（无穷大）
   - `-Infinity`（负无穷大）
3. **类型推断**: TypeScript 支持类型推断，可以在未显式声明类型时根据初始值自动推断出变量的类型。

## 示例
以下是一些使用“number”类型的基本示例：

```typescript
// 声明整数
let age: number = 30;

// 声明浮点数
let temperature: number = 36.6;

// 数值运算
let sum: number = age + temperature;

// 使用特殊值
let notANumber: number = NaN;
let bigNumber: number = Infinity;
```

## 解释
在使用“number”类型时，开发者需要注意以下几点：

1. **NaN 的比较**: NaN 与任何值（包括自身）进行比较时均返回 false，因此需要使用 `isNaN()` 函数来判断一个值是否为 NaN。
2. **精度问题**: 浮点数的表示可能导致精度问题，例如 `0.1 + 0.2 !== 0.3`，因此在处理货币等需要高精度的数值时，建议使用整数或专门的库。
3. **溢出**: JavaScript 的“number”类型使用 IEEE 754 双精度浮点格式，可能在处理极大或极小的数值时出现溢出或下溢的情况。

## 一句话总结
在 TypeScript 中，“number” 是一种用于表示整数和浮点数的基本数据类型，支持多种数学运算和特殊值。
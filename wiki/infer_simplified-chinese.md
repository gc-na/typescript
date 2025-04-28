<!--
Meta Description: # TypeScript 中的 infer 关键字详解 ## 概述 `infer` 是 TypeScript 中一个强大的关键字，主要用于类型推断，尤其在条件类型中非常有用。它允许开发者从已知类型中推导出新的类型，增强了类型的灵活性和可重用性。 ## 文档 在 TypeScript 中，`infer...
Meta Keywords: infer, type, typescript, extends, number
-->

# TypeScript 中的 infer 关键字详解

## 概述
`infer` 是 TypeScript 中一个强大的关键字，主要用于类型推断，尤其在条件类型中非常有用。它允许开发者从已知类型中推导出新的类型，增强了类型的灵活性和可重用性。

## 文档
在 TypeScript 中，`infer` 关键字通常出现在条件类型的上下文中。它使开发者能够在条件类型中声明一个类型变量，并在条件成立时对该类型进行推断。`infer` 的主要目的是简化类型定义，避免冗长的类型声明。

### 用法
使用 `infer` 的基本语法如下：
```typescript
type MyType<T> = T extends SomeType<infer U> ? U : DefaultType;
```
在这个例子中，`U` 是一个类型变量，如果 `T` 是 `SomeType` 的实例，TypeScript 将推断出 `U` 的类型，否则返回 `DefaultType`。

### 详细说明
- `infer` 只能在条件类型中使用。
- 一旦在条件中使用了 `infer`，就可以在条件的结果中使用推断出的类型。
- `infer` 关键字并不改变类型的结构，而是提供了一种方式来从现有类型中提取信息。

## 示例
以下是一些使用 `infer` 的基本示例：

### 示例 1：推断函数参数类型
```typescript
type ParametersType<T> = T extends (...args: infer P) => any ? P : never;

type Func = (a: number, b: string) => void;
type Params = ParametersType<Func>; // Params 的类型为 [number, string]
```

### 示例 2：提取数组元素类型
```typescript
type ElementType<T> = T extends (infer E)[] ? E : never;

type Numbers = number[];
type NumType = ElementType<Numbers>; // NumType 的类型为 number
```

### 示例 3：提取 Promise 的解析类型
```typescript
type ResolveType<T> = T extends Promise<infer R> ? R : never;

type MyPromise = Promise<string>;
type Resolved = ResolveType<MyPromise>; // Resolved 的类型为 string
```

## 说明
- 常见问题：`infer` 只能在条件类型中使用，不能在其他上下文中使用。
- 注意事项：使用 `infer` 时要确保条件类型的逻辑是正确的，否则可能导致类型推导失败。
- 陷阱：过于复杂的推导可能会让类型变得难以理解，建议保持类型推导的简单性。

## 一句话总结
`infer` 关键字在 TypeScript 中用于从条件类型中推断类型变量，增强了类型的灵活性和可重用性。
<!--
Meta Description: # TypeScript 中的枚举（enum）详解 ## 概述 在 TypeScript 中，枚举（enum）是一种特殊的类型，用于定义一组命名的常数。它使得代码更加清晰和可维护，能够提高代码的可读性。 ## 文档 ### 目的 枚举用于定义一组相关的常量，可以是数字或字符串类型。使用枚举可以避免在...
Meta Keywords: enum, typescript, yes, active, color
-->

# TypeScript 中的枚举（enum）详解

## 概述
在 TypeScript 中，枚举（enum）是一种特殊的类型，用于定义一组命名的常数。它使得代码更加清晰和可维护，能够提高代码的可读性。

## 文档
### 目的
枚举用于定义一组相关的常量，可以是数字或字符串类型。使用枚举可以避免在代码中使用魔法字符串或数字，从而提高代码的可读性和可维护性。

### 用法
在 TypeScript 中，可以通过 `enum` 关键字来定义枚举。枚举可以是数字枚举、字符串枚举或异构枚举。

#### 数字枚举
```typescript
enum Direction {
    Up = 1,
    Down,
    Left,
    Right
}
```
在上述示例中，`Direction` 枚举的值从 1 开始，`Down` 将自动赋值为 2，`Left` 为 3，`Right` 为 4。

#### 字符串枚举
```typescript
enum Response {
    No = "NO",
    Yes = "YES"
}
```
在这个例子中，`Response` 枚举的每个成员都被赋予了一个字符串值。

#### 异构枚举
```typescript
enum Mixed {
    No = 0,
    Yes = "YES"
}
```
异构枚举可以同时包含数字和字符串类型的值。

### 详细信息
- **默认值**：如果不指定初始值，数字枚举会从 0 开始自动递增。
- **常量枚举**：使用 `const enum` 关键字定义的枚举在编译时会被内联，适合性能敏感的场景。
- **计算值**：枚举成员的值可以是常量表达式或其他枚举成员的值。

## 示例
### 基本用法
```typescript
enum Color {
    Red,
    Green,
    Blue
}

let myColor: Color = Color.Green;
console.log(myColor); // 输出: 1
```

### 字符串枚举示例
```typescript
enum Status {
    Active = "ACTIVE",
    Inactive = "INACTIVE"
}

let userStatus: Status = Status.Active;
console.log(userStatus); // 输出: "ACTIVE"
```

## 说明
- **常见问题**：使用枚举时要注意，若在枚举中使用字符串和数字混合，可能导致类型不一致。
- **类型安全**：枚举提供了更强的类型安全性，避免了使用简单的字符串或数字可能导致的错误。
- **调试信息**：枚举在调试时提供更友好的输出，有助于快速识别值的含义。

## 一句话总结
TypeScript 中的枚举（enum）是一种用于定义一组命名常量的强类型结构，提升了代码的可读性和可维护性。
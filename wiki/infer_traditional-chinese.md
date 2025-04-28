<!--
Meta Description: # TypeScript 中的推斷（infer）關鍵字 ## 簡介 在 TypeScript 中，`infer` 是一個用於條件類型中的關鍵字，允許開發者在類型推斷中捕獲和使用上下文類型。這使得類型系統更加靈活和強大，能夠根據傳入的類型自動推斷出新的類型。 ## 文檔 `infer` 的主要目的是在...
Meta Keywords: infer, type, typescript, extends, result
-->

# TypeScript 中的推斷（infer）關鍵字

## 簡介
在 TypeScript 中，`infer` 是一個用於條件類型中的關鍵字，允許開發者在類型推斷中捕獲和使用上下文類型。這使得類型系統更加靈活和強大，能夠根據傳入的類型自動推斷出新的類型。

## 文檔
`infer` 的主要目的是在條件類型中創建一個新的類型，該類型基於某個未知類型的特定屬性或結構。這通常用於從函數或對象中提取類型信息，從而在類型系統中進行更複雜的操作。

### 使用方法
`infer` 主要用於條件類型中，語法如下：

```typescript
type ResultType<T> = T extends SomeType<infer U> ? U : DefaultType;
```

在這個語法中，`T` 是一個待檢查的類型，`SomeType<infer U>` 是一個條件，當 `T` 符合該條件時，`U` 將被推斷為 `SomeType` 中的類型。如果不符合條件，則返回 `DefaultType`。

## 示例
以下是幾個使用 `infer` 的基本示例：

### 示例 1: 提取函數返回類型
```typescript
type ReturnType<T> = T extends (...args: any[]) => infer R ? R : never;

function exampleFunction() {
    return 42;
}

type Result = ReturnType<typeof exampleFunction>; // Result 為 number
```

### 示例 2: 提取陣列元素類型
```typescript
type ElementType<T> = T extends (infer U)[] ? U : never;

type MyArray = number[];
type Element = ElementType<MyArray>; // Element 為 number
```

### 示例 3: 提取 Promise 的結果類型
```typescript
type UnwrapPromise<T> = T extends Promise<infer U> ? U : T;

type MyPromise = Promise<string>;
type Result = UnwrapPromise<MyPromise>; // Result 為 string
```

## 解釋
在使用 `infer` 時，有幾個常見的注意事項：

1. **僅限條件類型**：`infer` 只能用於條件類型內，不能單獨使用。
2. **上下文限制**：`infer` 推斷的類型只能在其作用域內使用，不能在外部引用。
3. **類型安全**：使用 `infer` 時，需注意確保類型的正確性，避免在不符合條件的情況下使用推斷的類型。

## 一句總結
`infer` 是 TypeScript 中一個強大的關鍵字，允許開發者在條件類型中推斷並捕獲類型信息，增強類型系統的靈活性。
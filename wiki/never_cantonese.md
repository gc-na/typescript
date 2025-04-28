<!--
Meta Description: # TypeScript 中的 "never" 類型：完整指南 ## 概要 在 TypeScript 中，`never` 類型代表一個不會發生的值，通常用於表示無法到達的代碼區域或永遠不會返回的函數。這對於增強類型安全性和編譯時錯誤檢查非常有幫助。 ## 文檔 `never` 類型的主要用途是表示以...
Meta Keywords: never, shape, typescript, function, message
-->

# TypeScript 中的 "never" 類型：完整指南

## 概要
在 TypeScript 中，`never` 類型代表一個不會發生的值，通常用於表示無法到達的代碼區域或永遠不會返回的函數。這對於增強類型安全性和編譯時錯誤檢查非常有幫助。

## 文檔
`never` 類型的主要用途是表示以下幾種情況：
1. 一個函數不會返回值，例如拋出錯誤的函數。
2. 一個函數的執行永遠不會完成，例如無限循環的函數。
3. 在使用類型保護時，當一個分支不會被執行時。

### 使用方式
在 TypeScript 中，可以通過將函數的返回類型設置為 `never` 來聲明一個不會返回的函數。例如：

```typescript
function throwError(message: string): never {
    throw new Error(message);
}
```

在這個例子中，`throwError` 函數會拋出一個錯誤，導致函數不會正常返回。

## 示例
以下是一些 `never` 類型的基本用法示例：

### 示例 1：拋出錯誤的函數
```typescript
function throwError(message: string): never {
    throw new Error(message);
}
```

### 示例 2：無限循環的函數
```typescript
function infiniteLoop(): never {
    while (true) {
        console.log("這是一個無限循環");
    }
}
```

### 示例 3：使用 `never` 作為類型守護
```typescript
type Shape = { kind: "circle"; radius: number } | { kind: "square"; side: number };

function handleShape(shape: Shape) {
    switch (shape.kind) {
        case "circle":
            console.log(`圓的半徑是 ${shape.radius}`);
            break;
        case "square":
            console.log(`正方形的邊長是 ${shape.side}`);
            break;
        default:
            const _exhaustiveCheck: never = shape; // 這裡的 `shape` 應該不可能到達
            throw new Error(`未知的形狀: ${shape}`);
    }
}
```

## 解釋
使用 `never` 型別時，開發者應注意以下幾個常見陷阱：
- `never` 型別不能與其他類型兼容，這意味著任何嘗試將 `never` 賦值給其他類型的行為都會引發編譯錯誤。
- 對於某些函數，可能會誤認為它們返回 `undefined`，但實際上它們返回的是 `never`。例如，拋出異常的函數或進入無限循環的函數。
- `never` 型別在錯誤處理和分支判斷中非常有用，能夠保證所有可能的情況都被涵蓋。

## 一句總結
在 TypeScript 中，`never` 類型用於表示不會發生的值，通常用於拋出錯誤或無限循環的函數。
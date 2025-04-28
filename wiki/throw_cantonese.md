<!--
Meta Description: # TypeScript 中的 throw：錯誤處理的關鍵字 ## 摘要 `throw` 是 TypeScript 中用於拋出異常的關鍵字，能夠在運行時引發錯誤，並使程序中斷執行，便於錯誤處理和調試。 ## 文檔 `throw` 關鍵字的主要目的是在程式中引發一個異常情況。當使用 `throw` 時...
Meta Keywords: throw, typescript, error, try, catch
-->

# TypeScript 中的 throw：錯誤處理的關鍵字

## 摘要
`throw` 是 TypeScript 中用於拋出異常的關鍵字，能夠在運行時引發錯誤，並使程序中斷執行，便於錯誤處理和調試。

## 文檔
`throw` 關鍵字的主要目的是在程式中引發一個異常情況。當使用 `throw` 時，程序會立即停止執行當前的上下文，並將控制權轉交給最近的異常處理器（通常是 `try...catch` 塊）。這使得開發者能夠捕獲錯誤並進行相應的處理。

### 用法
在 TypeScript 中，`throw` 的語法如下：

```typescript
throw expression;
```

其中，`expression` 可以是任何類型的值，通常是一個 `Error` 對象或其子類。

### 詳細說明
- `throw` 可以與 `try...catch` 結構配合使用，以便捕獲並處理異常。
- 當 `throw` 被調用時，會中止當前函數的執行。
- 可以自定義錯誤類別，通過擴展 `Error` 類來提供更多的錯誤上下文。

## 範例
以下是一些使用 `throw` 的基本範例：

### 範例 1：拋出標準錯誤
```typescript
function divide(a: number, b: number): number {
    if (b === 0) {
        throw new Error("不能除以零");
    }
    return a / b;
}

try {
    console.log(divide(10, 0));
} catch (e) {
    console.error(e.message); // 輸出：不能除以零
}
```

### 範例 2：自定義錯誤類別
```typescript
class CustomError extends Error {
    constructor(message: string) {
        super(message);
        this.name = "CustomError";
    }
}

function checkValue(value: number) {
    if (value < 0) {
        throw new CustomError("值必須大於 0");
    }
}

try {
    checkValue(-1);
} catch (e) {
    console.error(e.name + ": " + e.message); // 輸出：CustomError: 值必須大於 0
}
```

## 解釋
使用 `throw` 時，開發者需注意以下幾點：
- 確保在 `throw` 之後存在適當的 `try...catch` 塊來捕獲錯誤，否則程序將會因未處理的異常而崩潰。
- 拋出的錯誤應該提供清晰的訊息，以便於調試。
- 不應在不必要的情況下隨意使用 `throw`，因為過多的異常拋出會使代碼難以維護和理解。

## 一句總結
`throw` 是 TypeScript 中用於拋出錯誤的重要工具，能幫助開發者有效處理異常情況。
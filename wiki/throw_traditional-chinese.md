<!--
Meta Description: # TypeScript 中的 throw 語句：異常處理的關鍵工具 ## 概述 在 TypeScript 中，`throw` 語句用於顯式拋出異常，這使得開發者能夠在程序中處理錯誤情況，並提供更好的錯誤管理和調試能力。 ## 文檔 `throw` 語句的主要目的是中止當前執行流程並拋出一個錯誤對象...
Meta Keywords: throw, error, typescript, catch, try
-->

# TypeScript 中的 throw 語句：異常處理的關鍵工具

## 概述
在 TypeScript 中，`throw` 語句用於顯式拋出異常，這使得開發者能夠在程序中處理錯誤情況，並提供更好的錯誤管理和調試能力。

## 文檔
`throw` 語句的主要目的是中止當前執行流程並拋出一個錯誤對象。當一個錯誤被拋出後，控制權會轉移到最近的錯誤處理器（通常是 try-catch 區塊），這樣可以根據具體情況對錯誤進行處理。

### 用法
`throw` 語句的基本語法如下：
```typescript
throw expression;
```
`expression` 可以是任何有效的 JavaScript 對象，通常是錯誤對象或自定義錯誤對象。

### 詳細信息
- 在 TypeScript 中，`throw` 語句後面可以跟隨任何類型的表達式，但通常使用 `Error` 類或其子類。
- 當 `throw` 被執行時，當前函數會立即停止執行，並將控制權轉移到最近的 `try-catch` 塊。
- 如果沒有合適的 `catch` 塊來處理拋出的錯誤，則該錯誤會導致程序崩潰。

## 範例
以下是一些基本用法的示例：

### 示例 1：拋出標準錯誤
```typescript
function checkPositiveNumber(num: number) {
    if (num < 0) {
        throw new Error("數字必須是正數");
    }
    return num;
}

try {
    checkPositiveNumber(-10);
} catch (error) {
    console.error(error.message); // 輸出: "數字必須是正數"
}
```

### 示例 2：拋出自定義錯誤
```typescript
class CustomError extends Error {
    constructor(message: string) {
        super(message);
        this.name = "CustomError";
    }
}

function processData(data: any) {
    if (!data) {
        throw new CustomError("資料不可為空");
    }
    return data;
}

try {
    processData(null);
} catch (error) {
    console.error(error.message); // 輸出: "資料不可為空"
}
```

## 解釋
在使用 `throw` 時，開發者需要注意以下幾點：
- 確保在適當的場景下使用 `throw`，以避免不必要的程序中斷。
- 錯誤處理應當涵蓋所有可能的錯誤情況，以提升代碼的健壯性。
- 注意 `throw` 語句後的控制流，確保有合適的 `try-catch` 块來捕獲和處理拋出的異常，否則可能導致應用崩潰。

## 一句總結
在 TypeScript 中，`throw` 語句用於顯式拋出異常，使得錯誤處理變得更加靈活和可控。
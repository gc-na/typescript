<!--
Meta Description: # TypeScript 中的 "unknown" 類型：深入解析與應用 ## 摘要 在 TypeScript 中，`unknown` 類型是一種安全的替代品，用於表示一個未知的值，提供比 `any` 更嚴格的類型檢查，促進更高的類型安全性。 ## 文檔 `unknown` 類型是 TypeScri...
Meta Keywords: unknown, typescript, any, console, log
-->

# TypeScript 中的 "unknown" 類型：深入解析與應用

## 摘要
在 TypeScript 中，`unknown` 類型是一種安全的替代品，用於表示一個未知的值，提供比 `any` 更嚴格的類型檢查，促進更高的類型安全性。

## 文檔
`unknown` 類型是 TypeScript 2.0 引入的一個新特性。它的主要目的是提供一種方式來表示我們不知道變數的具體類型。與 `any` 不同，`unknown` 在使用之前需要進行類型檢查，這樣有助於避免在運行時發生錯誤。

### 目的
- 提高類型安全性：使用 `unknown` 可以強制開發者在使用變數之前進行類型檢查。
- 避免使用 `any`：使用 `any` 可能導致程序出現難以追蹤的錯誤，而 `unknown` 促使開發者明確指定類型。

### 使用方式
當你需要一個變數的類型不明，但又希望保持類型安全時，可以將該變數定義為 `unknown` 類型。這樣，你必須在使用該變數之前進行類型檢查。

```typescript
let value: unknown;

// 不能直接使用，會報錯
// console.log(value.toString());

// 進行類型檢查後可以安全使用
if (typeof value === "string") {
    console.log(value.toString());
}
```

## 範例
以下是使用 `unknown` 的基本範例：

### 範例 1：未知類型的變數
```typescript
let data: unknown;

data = 42; // 可以是數字
data = "Hello"; // 也可以是字符串

// 使用前必須進行檢查
if (typeof data === "string") {
    console.log(data.toUpperCase()); // 安全使用
}
```

### 範例 2：函數返回未知類型
```typescript
function getValue(): unknown {
    return Math.random() > 0.5 ? "A string" : 42; // 返回未知類型
}

const result = getValue();

// 使用前進行類型檢查
if (typeof result === "string") {
    console.log(result.length); // 安全使用
} else {
    console.log(result.toFixed(2)); // 也是安全使用
}
```

## 解釋
使用 `unknown` 類型時，開發者需要注意以下幾點：

- **類型檢查是必須的**：在使用 `unknown` 類型的變數之前，必須先進行類型檢查，這是 `unknown` 的設計初衷之一。
- **不支持類型推斷**：與 `any` 不同，`unknown` 不允許直接進行操作，如調用方法或屬性，必須進行類型的判斷。
- **適用於不確定的數據**：當處理來自外部來源（如 API）的數據時，使用 `unknown` 是一個好的選擇，可以避免不必要的錯誤。

## 一句總結
`unknown` 類型在 TypeScript 中提供了一種安全的方式來處理未知類型的變數，促進了更高的類型安全性和代碼的可維護性。
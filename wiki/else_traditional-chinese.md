<!--
Meta Description: # TypeScript 中的 "else" 語句：用於控制流的關鍵字 ## 摘要 在 TypeScript 中，`else` 語句是控制流的一部分，允許根據條件的真假來執行不同的程式碼區塊。這使得程式的邏輯更加靈活和可讀。 ## 文檔 `else` 語句通常與 `if` 語句搭配使用，用來定義在 ...
Meta Keywords: else, typescript, score, console, log
-->

# TypeScript 中的 "else" 語句：用於控制流的關鍵字

## 摘要
在 TypeScript 中，`else` 語句是控制流的一部分，允許根據條件的真假來執行不同的程式碼區塊。這使得程式的邏輯更加靈活和可讀。

## 文檔
`else` 語句通常與 `if` 語句搭配使用，用來定義在 `if` 條件不成立時所執行的程式碼。它的主要目的是提供一種在多種情況下執行不同代碼的簡單方法。

### 語法
```typescript
if (condition) {
    // 當 condition 為 true 時執行的程式碼
} else {
    // 當 condition 為 false 時執行的程式碼
}
```

### 用途
`else` 的主要用途是在條件判斷中提供替代的執行路徑。這對於需要根據用戶輸入或其他條件來決定程式行為的情況特別有用。

## 範例
### 基本使用範例
以下是一個簡單的範例，演示了如何使用 `else` 語句：

```typescript
let score: number = 75;

if (score >= 60) {
    console.log("通過");
} else {
    console.log("未通過");
}
```

在這個例子中，當 `score` 大於或等於 60 時，程式會輸出 "通過"；否則，它會輸出 "未通過"。

### 多重條件範例
你也可以使用 `else if` 來處理多個條件：

```typescript
let score: number = 85;

if (score >= 90) {
    console.log("優秀");
} else if (score >= 75) {
    console.log("良好");
} else {
    console.log("需要改進");
}
```

在這裡，`else if` 允許我們檢查多個條件，並根據不同的分數範圍輸出不同的訊息。

## 說明
在使用 `else` 語句時，有一些常見的陷阱和注意事項：

1. **漏掉大括號**：在只有一行程式碼的情況下，可以省略大括號，但為了可讀性建議始終使用大括號。
   
2. **邏輯錯誤**：確保你正確理解條件的邏輯，避免因條件錯誤而導致意外的執行流。

3. **嵌套 `if`**：過度嵌套的 `if` 和 `else` 結構會導致程式碼變得難以維護，考慮使用 `switch` 語句或其他控制流結構以提高可讀性。

## 一行摘要
在 TypeScript 中，`else` 語句用於定義在 `if` 條件不成立時所執行的替代程式碼。
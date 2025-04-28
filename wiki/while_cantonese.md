<!--
Meta Description: # TypeScript 中的 "while" 循環：用法與示例 ## 簡介 "while" 循環是 TypeScript 中用於重複執行一段代碼的控制結構，直到指定的條件不再滿足。它是一個重要的流程控制工具，適用於需要根據條件不斷執行的場景。 ## 文檔 ### 目的 "while" 循環的主要目...
Meta Keywords: while, typescript, count, userinput, condition
-->

# TypeScript 中的 "while" 循環：用法與示例

## 簡介
"while" 循環是 TypeScript 中用於重複執行一段代碼的控制結構，直到指定的條件不再滿足。它是一個重要的流程控制工具，適用於需要根據條件不斷執行的場景。

## 文檔
### 目的
"while" 循環的主要目的是在條件為真時不斷執行代碼區塊，適合於動態次數的迴圈。

### 用法
"while" 循環的基本語法如下：

```typescript
while (condition) {
    // 執行的代碼
}
```

- **condition**：一個布林表達式，當其為真時，將執行循環內的代碼。
- 循環將持續執行，直到 condition 為假。

### 詳細說明
在 TypeScript 中，"while" 循環可用於各種情況，特別是當迴圈的次數未知時。它與 "for" 循環的不同之處在於，"for" 循環通常用於已知次數的迴圈，而 "while" 循環則適合用於需要持續檢查某個條件的情況。

## 示例
以下是 "while" 循環的基本用法示例：

### 示例 1：簡單計數器
```typescript
let count = 0;

while (count < 5) {
    console.log(count);
    count++;
}
```
這段代碼將輸出 0 到 4 的數字。

### 示例 2：用戶輸入
```typescript
let userInput: string;
while (userInput !== "exit") {
    userInput = prompt("請輸入一個字串（輸入 'exit' 以結束）：");
    console.log(`你輸入的字串是：${userInput}`);
}
```
這段代碼會持續要求用戶輸入字串，直到輸入 "exit" 為止。

## 解釋
在使用 "while" 循環時，開發者需要注意以下幾點：

1. **無限循環**：如果條件永遠為真，將導致無限循環，程序將無法終止。必須確保在循環內有能改變條件的邏輯。
  
2. **性能問題**：不當使用 "while" 循環可能會影響程序性能，尤其是在循環內有阻塞性的代碼時。

3. **變量作用域**：在循環內定義的變量，其作用域僅限於循環內部，需注意變量的聲明位置。

## 一句總結
TypeScript 中的 "while" 循環允許根據條件持續執行代碼，適合於動態次數的迴圈操作。
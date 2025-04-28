<!--
Meta Description: # TypeScript 中的 switch 語句使用指南 ## 概述 `switch` 語句是 TypeScript 中一種條件控制結構，主要用於根據不同的表達式值執行不同的代碼塊。它提供了一種清晰、簡潔的方式來處理多條分支的邏輯，特別是在需要對多個可能的情況進行判斷時。 ## 文檔 ### 目的...
Meta Keywords: case, switch, break, console, log
-->

# TypeScript 中的 switch 語句使用指南

## 概述
`switch` 語句是 TypeScript 中一種條件控制結構，主要用於根據不同的表達式值執行不同的代碼塊。它提供了一種清晰、簡潔的方式來處理多條分支的邏輯，特別是在需要對多個可能的情況進行判斷時。

## 文檔
### 目的
`switch` 語句的目的是基於一個表達式的值來選擇執行的代碼分支。這使得在多個選項中進行分支選擇變得更加直觀，並且比一系列的 `if...else` 語句更加易於閱讀和維護。

### 語法
```typescript
switch (表達式) {
    case 值1:
        // 當表達式等於值1時執行的代碼
        break;
    case 值2:
        // 當表達式等於值2時執行的代碼
        break;
    // 可選的 default 分支
    default:
        // 當以上所有值都不匹配時執行的代碼
}
```

### 使用
1. **表達式**：`switch` 語句的表達式可以是任何有效的 TypeScript 表達式。
2. **case**：每一個 `case` 後面跟著一個值，如果表達式跟該值匹配，則執行其下的代碼。
3. **break**：用於終止當前 `switch` 的執行，防止代碼“穿透”到下一個 `case` 中。
4. **default**：可選的分支，當表達式不匹配任何 `case` 時執行。

## 範例
### 基本用法
```typescript
let fruit: string = "apple";

switch (fruit) {
    case "banana":
        console.log("這是一根香蕉。");
        break;
    case "apple":
        console.log("這是一個蘋果。");
        break;
    case "orange":
        console.log("這是一個橙子。");
        break;
    default:
        console.log("這不是我認識的水果。");
}
```

### 數字範例
```typescript
let score: number = 85;

switch (true) {
    case score >= 90:
        console.log("優秀");
        break;
    case score >= 75:
        console.log("良好");
        break;
    case score >= 60:
        console.log("及格");
        break;
    default:
        console.log("不及格");
}
```

## 解釋
- **常見陷阱**：未使用 `break` 可能導致代碼“穿透”，結果執行了多個 `case`。這在開發中可能會造成意外的行為。
- **類型匹配**：`switch` 語句在比較時是嚴格的，這意味著不同類型的值不會匹配（例如，字符串和數字）。
- **性能**：在處理大量選項時，`switch` 語句的性能通常優於多個 `if...else` 語句，但具體情況需視應用場景而定。

## 總結
`switch` 語句是一種有效的條件控制結構，適合於多重選擇的場景，使 TypeScript 代碼更加簡潔明了。
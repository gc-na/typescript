<!--
Meta Description: # TypeScript 中的 "if" 條件語句使用指南 ## Synopsis 在 TypeScript 中，"if" 條件語句是用來根據特定條件執行不同的代碼塊的基本控制結構。 ## Documentation ### 目的 "if" 條件語句允許開發者根據布爾表達式的結果來決定是否執行某段代...
Meta Keywords: typescript, else, console, log, condition
-->

# TypeScript 中的 "if" 條件語句使用指南

## Synopsis
在 TypeScript 中，"if" 條件語句是用來根據特定條件執行不同的代碼塊的基本控制結構。

## Documentation
### 目的
"if" 條件語句允許開發者根據布爾表達式的結果來決定是否執行某段代碼。這使得程式能夠根據不同情況做出相應反應，增強了程式的靈活性和功能。

### 使用方式
基本的 "if" 語法如下：

```typescript
if (condition) {
    // 當 condition 為 true 時執行的代碼
}
```

你也可以使用 "else" 和 "else if" 來處理多個條件：

```typescript
if (condition1) {
    // 當 condition1 為 true 時執行的代碼
} else if (condition2) {
    // 當 condition2 為 true 時執行的代碼
} else {
    // 當所有條件都不成立時執行的代碼
}
```

### 詳細說明
- `condition` 必須是一個返回布爾值（true 或 false）的表達式。
- 代碼塊可以是單行語句或多行語句，建議使用大括號 `{}` 來明確包裹代碼塊，即使只有一行代碼。
- TypeScript 提供類型檢查，確保 `condition` 是有效的布爾表達式。

## Examples
### 基本範例
```typescript
const age: number = 18;

if (age >= 18) {
    console.log("你已滿18歲，可以投票。");
} else {
    console.log("你未滿18歲，不能投票。");
}
```

### 多條件範例
```typescript
const score: number = 85;

if (score >= 90) {
    console.log("成績優秀！");
} else if (score >= 75) {
    console.log("成績良好！");
} else {
    console.log("需要加油！");
}
```

## Explanation
- **常見陷阱**：在 `if` 條件中，布爾值的比較必須正確，避免使用簡單的賦值運算符（`=`）而非比較運算符（`==` 或 `===`）。
- **注意事項**：在 TypeScript 中，使用 `else if` 可以使多重條件的判斷更加清晰；同時，對於複雜條件的判斷，可以考慮將條件單獨封裝為變數以提高可讀性。
- **型別安全**：TypeScript 的靜態類型檢查可以幫助你捕獲類型錯誤，確保條件的正確性。

## One Line Summary
在 TypeScript 中，"if" 條件語句用於根據布爾表達式的結果執行不同的代碼塊。
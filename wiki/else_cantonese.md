<!--
Meta Description: # TypeScript 中的 "else" 語句使用指南 ## 簡介 在 TypeScript 中，`else` 語句是用於控制流程的關鍵字，通常與 `if` 語句搭配使用。它允許開發者根據條件執行不同的代碼塊，增強了應用程式的邏輯能力。 ## 文檔 `else` 語句的主要目的是在 `if` 條...
Meta Keywords: else, typescript, score, console, log
-->

# TypeScript 中的 "else" 語句使用指南

## 簡介
在 TypeScript 中，`else` 語句是用於控制流程的關鍵字，通常與 `if` 語句搭配使用。它允許開發者根據條件執行不同的代碼塊，增強了應用程式的邏輯能力。

## 文檔
`else` 語句的主要目的是在 `if` 條件不成立的情況下執行替代的代碼塊。這使得開發者能夠在多重條件判斷中創造更複雜的邏輯。

### 使用方式
`else` 語句通常與 `if` 語句連用。其基本語法如下：

```typescript
if (condition) {
    // 當條件成立時執行的代碼
} else {
    // 當條件不成立時執行的代碼
}
```

### 詳細說明
- `condition` 是一個布爾表達式，如果為 `true`，則執行 `if` 內的代碼；如果為 `false`，則執行 `else` 內的代碼。
- `else` 語句是可選的，並不一定需要出現在每個 `if` 語句後面。
- 可以在 `else` 語句後面添加 `if` 語句，形成嵌套的 `if-else` 結構，稱為 `else if` 鏈接。

## 範例
以下是 `else` 語句的基本用法範例：

```typescript
let score: number = 75;

if (score >= 80) {
    console.log("你通過了考試！");
} else {
    console.log("抱歉，你未能通過考試。");
}
```

嵌套的 `if-else` 範例：

```typescript
let score: number = 55;

if (score >= 80) {
    console.log("你通過了考試！");
} else if (score >= 60) {
    console.log("你只差一點！");
} else {
    console.log("抱歉，你未能通過考試。");
}
```

## 解釋
在使用 `else` 語句時，有幾點需要注意：
- 確保條件表達式正確，否則可能導致錯誤的邏輯判斷。
- 嵌套的 `if-else` 結構容易導致邏輯錯亂，建議保持代碼簡潔，必要時使用註解。
- 在 TypeScript 中，`else` 語句後面不需要加分號，這可能會導致語法錯誤。

## 一句總結
`else` 語句在 TypeScript 中用於在條件不成立時執行替代代碼，幫助開發者實現更複雜的邏輯流程。
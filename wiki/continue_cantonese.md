<!--
Meta Description: # TypeScript 中的 "continue" 语句：用於控制流程的關鍵字 ## 概述 在 TypeScript 中，`continue` 是一個控制流程的關鍵字，主要用於循環結構中。當 `continue` 被執行時，當前迴圈的其餘部分將被跳過，並且程序將繼續執行下一次迴圈。 ## 文檔 `...
Meta Keywords: continue, typescript, while, console, log
-->

# TypeScript 中的 "continue" 语句：用於控制流程的關鍵字

## 概述
在 TypeScript 中，`continue` 是一個控制流程的關鍵字，主要用於循環結構中。當 `continue` 被執行時，當前迴圈的其餘部分將被跳過，並且程序將繼續執行下一次迴圈。

## 文檔
`continue` 語句的主要目的是跳過當前迴圈的剩餘代碼，並直接進入下一次迴圈的執行。這通常用於需要在特定條件下忽略某些迭代的情況。`continue` 可以與 `for`、`while` 和 `do...while` 循環結合使用。

### 用法
以下是 `continue` 的基本用法：

```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 跳過偶數
    }
    console.log(i); // 只會打印出奇數
}
```

在這個例子中，當 `i` 是偶數時，`continue` 語句會使程式跳過 `console.log(i)` 語句，因此只會輸出奇數。

## 範例
下面是一些使用 `continue` 的基本範例：

### 範例 1：在 `for` 循環中使用 `continue`
```typescript
for (let j = 1; j <= 5; j++) {
    if (j === 3) {
        continue; // 當 j 為 3 時跳過
    }
    console.log(j); // 將打印 1, 2, 4, 5
}
```

### 範例 2：在 `while` 循環中使用 `continue`
```typescript
let k = 0;
while (k < 5) {
    k++;
    if (k === 2) {
        continue; // 當 k 為 2 時跳過
    }
    console.log(k); // 將打印 1, 3, 4, 5
}
```

## 解釋
在使用 `continue` 時，有幾個常見的陷阱和注意事項：

1. **循環結構**：`continue` 只能在循環結構內使用，否則會引發錯誤。
2. **代碼可讀性**：過度使用 `continue` 可能會導致代碼可讀性下降。應謹慎使用，尤其是在複雜的循環邏輯中。
3. **無限循環**：確保使用 `continue` 後，循環條件能夠在某個時刻終止，以防止無限循環的情況發生。

## 一句總結
`continue` 語句讓 TypeScript 程序能夠在循環中跳過當前迭代，直接進入下一次的執行。
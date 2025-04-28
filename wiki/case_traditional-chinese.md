<!--
Meta Description: # TypeScript 中的「case」用法詳解 ## 簡介 在 TypeScript 中，「case」關鍵字主要用於 `switch` 陳述式中，允許根據不同的條件執行相應的代碼區塊。這使得根據變量的值來控制程式流程變得簡單而直觀。 ## 文檔 ### 目的 「case」用於定義 `switch...
Meta Keywords: case, switch, break, typescript, console
-->

# TypeScript 中的「case」用法詳解

## 簡介
在 TypeScript 中，「case」關鍵字主要用於 `switch` 陳述式中，允許根據不同的條件執行相應的代碼區塊。這使得根據變量的值來控制程式流程變得簡單而直觀。

## 文檔
### 目的
「case」用於定義 `switch` 陳述式中的每一個分支，幫助開發者根據不同的情況執行不同的代碼。

### 使用方法
`case` 關鍵字通常與 `switch` 陳述式一起使用，語法如下：

```typescript
switch (expression) {
    case value1:
        // 當 expression 等於 value1 時執行的代碼
        break;
    case value2:
        // 當 expression 等於 value2 時執行的代碼
        break;
    default:
        // 當 expression 不符合任何 case 時執行的代碼
}
```

### 詳細說明
1. **表達式**：`switch` 陳述式的表達式會被計算出來，並與每個 `case` 的值進行比較。
2. **匹配**：一旦找到匹配的 `case`，從該 `case` 開始的代碼會被執行，直到遇到 `break` 陳述式或 `switch` 結束。
3. **default**：可選的 `default` 分支會在沒有任何匹配時執行，類似於 `else` 的功能。

## 示例
### 基本用法示例
```typescript
const fruit = "apple";

switch (fruit) {
    case "banana":
        console.log("這是一根香蕉");
        break;
    case "apple":
        console.log("這是一顆蘋果");
        break;
    default:
        console.log("這不是我們的水果");
}
```
輸出: `這是一顆蘋果`

### 多重匹配示例
```typescript
const grade = "B";

switch (grade) {
    case "A":
    case "B":
        console.log("優秀");
        break;
    case "C":
        console.log("良好");
        break;
    default:
        console.log("需要改進");
}
```
輸出: `優秀`

## 解釋
### 常見問題
- **遺漏 `break`**：如果在 `case` 塊中遺漏 `break`，代碼將會繼續執行下一個 `case`，這可能會導致意外的行為。
- **類型匹配**：在 TypeScript 中，`switch` 陳述式進行的是嚴格匹配，確保變量類型與 `case` 值相符。

### 附加說明
使用 `switch` 和 `case` 可以使代碼更具可讀性，特別是當有多個條件需要處理時。然而，對於簡單的條件判斷，`if...else` 可能更為直觀。

## 一句總結
「case」關鍵字在 TypeScript 中用於 `switch` 陳述式，以根據不同的條件執行相應的代碼區塊。
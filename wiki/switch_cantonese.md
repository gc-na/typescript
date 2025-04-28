<!--
Meta Description: # TypeScript 中的 switch 語句：全面指南 ## 概述 `switch` 語句是 TypeScript 中用於多重條件判斷的控制結構，能夠根據變量的值選擇執行不同的代碼塊。 ## 文檔 `switch` 語句的主要目的是提供一種方便的方式來檢查多個可能的情況，特別是在需要根據某個變...
Meta Keywords: case, switch, break, console, log
-->

# TypeScript 中的 switch 語句：全面指南

## 概述
`switch` 語句是 TypeScript 中用於多重條件判斷的控制結構，能夠根據變量的值選擇執行不同的代碼塊。

## 文檔
`switch` 語句的主要目的是提供一種方便的方式來檢查多個可能的情況，特別是在需要根據某個變數的值進行多次比較時。相比於多層的 `if...else` 結構，`switch` 提供了一種更清晰的語法結構。

### 語法
```typescript
switch (表達式) {
    case 值1:
        // 執行代碼塊1
        break;
    case 值2:
        // 執行代碼塊2
        break;
    // 可以有任意數量的 case
    default:
        // 執行默認代碼塊
}
```

### 用法
- **表達式**：這是要比較的變量，通常是字符串、數字或任何可以比較的類型。
- **case**：每個 `case` 用於匹配表達式的值。如果匹配成功，則執行相應的代碼塊。
- **break**：用於結束 `switch` 語句的執行，防止執行到下一個 case。
- **default**：可選的，當所有的 case 都不匹配時執行。

## 示例
### 基本用法
```typescript
let fruit: string = "apple";

switch (fruit) {
    case "banana":
        console.log("這是一根香蕉");
        break;
    case "apple":
        console.log("這是一個蘋果");
        break;
    default:
        console.log("未知水果");
}
```
這段代碼將輸出 "這是一個蘋果"。

### 數字用法
```typescript
let day: number = 3;

switch (day) {
    case 1:
        console.log("星期一");
        break;
    case 2:
        console.log("星期二");
        break;
    case 3:
        console.log("星期三");
        break;
    default:
        console.log("未知的日子");
}
```
這段代碼將輸出 "星期三"。

## 解釋
在使用 `switch` 語句時，開發者應注意以下幾點常見問題：

1. **缺少 break 語句**：如果忘記在 case 的末尾添加 `break`，則會導致“fall-through”行為，意即後面的 case 也會被執行，這可能會導致意想不到的結果。
  
2. **比較類型**：`switch` 語句在比較時使用的是嚴格相等 (`===`)，因此如果表達式和 case 的類型不一致，則不會匹配。

3. **使用 default**：雖然 `default` 是可選的，但建議在 `switch` 語句中使用它，以處理所有未預期的情況。

## 一行總結
TypeScript 的 `switch` 語句提供了一種簡潔有效的方法來根據變數的值執行多條不同的代碼路徑。
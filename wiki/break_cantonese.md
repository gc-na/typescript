<!--
Meta Description: # TypeScript 中的 "break" 語句 ## 簡介 在 TypeScript 中，`break` 语句用于终止循环、switch 语句或标签语句的执行。它是控制程序流程的重要工具，能够有效地管理代码逻辑。 ## 文檔 ### 目的 `break` 語句的主要目的是立即退出當前的循環或 ...
Meta Keywords: break, switch, case, typescript, console
-->

# TypeScript 中的 "break" 語句

## 簡介
在 TypeScript 中，`break` 语句用于终止循环、switch 语句或标签语句的执行。它是控制程序流程的重要工具，能够有效地管理代码逻辑。

## 文檔
### 目的
`break` 語句的主要目的是立即退出當前的循環或 switch 語句，並跳到該結構之後的代碼執行。這在處理需要滿足特定條件才能結束循環的情況下特別有用。

### 使用方法
在 TypeScript 中，`break` 語句的典型使用場景包括：
- 在 `for`、`while` 或 `do...while` 循環中結束迭代。
- 在 `switch` 語句中結束某個 case 的執行。

### 詳細說明
- 在循環中使用 `break` 會中斷當前的循環，然後控制流將跳轉到循環結束後的第一行代碼。
- 在 `switch` 語句中，`break` 用於防止執行到後續的 case。如果缺少 `break` 語句，程序會繼續執行下一個 case，這種現象稱為“fall-through”。

## 範例
### 基本用法範例
```typescript
// 在 for 循環中使用 break
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break; // 當 i 等於 5 時退出循環
    }
    console.log(i); // 輸出 0, 1, 2, 3, 4
}

// 在 switch 語句中使用 break
const fruit = 'apple';
switch (fruit) {
    case 'banana':
        console.log('This is a banana.');
        break;
    case 'apple':
        console.log('This is an apple.'); // 輸出 'This is an apple.'
        break;
    default:
        console.log('Unknown fruit.');
}
```

## 解釋
- **常見陷阱**：在 switch 語句中，如果忘了加入 `break`，可能會導致錯誤的輸出，因為程序會繼續執行下一個 case 的代碼。
- **代碼可讀性**：過度使用 `break` 可能會導致代碼邏輯變得複雜，建議適度使用，並考慮使用其他控制結構（如 `return`）來提高可讀性。

## 一句總結
`break` 語句在 TypeScript 中用於立即終止循環或 switch 語句的執行，從而控制程序的流程。
<!--
Meta Description: # TypeScript 中的 `try` 語句：錯誤處理的利器 ## 簡介 在 TypeScript 中，`try` 語句用於捕獲和處理異常（錯誤），使得開發者能夠控制程序在遇到錯誤時的行為，從而提高代碼的穩定性和可維護性。 ## 文檔 `try` 語句的主要目的是在執行可能會拋出異常的代碼塊時，...
Meta Keywords: try, catch, error, typescript, finally
-->

# TypeScript 中的 `try` 語句：錯誤處理的利器

## 簡介
在 TypeScript 中，`try` 語句用於捕獲和處理異常（錯誤），使得開發者能夠控制程序在遇到錯誤時的行為，從而提高代碼的穩定性和可維護性。

## 文檔
`try` 語句的主要目的是在執行可能會拋出異常的代碼塊時，提供一種容錯的機制。當代碼塊內的代碼發生錯誤時，可以使用 `catch` 子句來捕獲這些異常，並進行相應的處理。這樣，程序不會因為一個錯誤而完全崩潰。

### 使用方法
`try` 語句的基本語法如下：

```typescript
try {
    // 可能會拋出異常的代碼
} catch (error) {
    // 處理異常的代碼
} finally {
    // 可選的，無論有無異常都會執行的代碼
}
```

- **try**：這部分包含可能會拋出異常的代碼。
- **catch**：當 `try` 塊中的代碼拋出異常時，會跳到這部分執行。`error` 參數包含了捕獲的錯誤信息。
- **finally**：這部分的代碼無論是否發生異常都會執行，通常用於資源的清理工作。

## 示例
以下是 `try` 語句的基本用法示例：

```typescript
function divide(a: number, b: number): number {
    try {
        if (b === 0) {
            throw new Error("Cannot divide by zero.");
        }
        return a / b;
    } catch (error) {
        console.error(error.message);
        return 0; // 返回0作為默認值
    } finally {
        console.log("Division operation completed.");
    }
}

console.log(divide(10, 2)); // 輸出：5
console.log(divide(10, 0)); // 輸出：Cannot divide by zero. 和 0
```

## 解釋
使用 `try` 語句時，開發者需要注意以下幾點：

1. **性能影響**：過多的異常處理可能會影響性能，因此只應在必要時使用 `try-catch`。
2. **捕獲特定錯誤**：在 `catch` 區塊中，可以根據錯誤類型進行特定的處理，這樣可以更精確地控制錯誤邏輯。
3. **使用 `finally`**：如果需要執行清理操作，建議使用 `finally` 來確保代碼的執行。

## 一句總結
`try` 語句在 TypeScript 中是錯誤處理的重要工具，幫助開發者安全地處理異常並保證程序的穩定性。
<!--
Meta Description: # TypeScript 中的 "if" 條件語句：用法與範例 ## 概述 在 TypeScript 中，`if` 條件語句是控制流程的基本工具，允許開發者根據特定條件執行不同的程式碼區塊。這使得程式能夠根據邏輯判斷改變其行為，從而提高靈活性和可讀性。 ## 文件說明 `if` 語句的主要目的是檢查...
Meta Keywords: typescript, else, console, log, let
-->

# TypeScript 中的 "if" 條件語句：用法與範例

## 概述
在 TypeScript 中，`if` 條件語句是控制流程的基本工具，允許開發者根據特定條件執行不同的程式碼區塊。這使得程式能夠根據邏輯判斷改變其行為，從而提高靈活性和可讀性。

## 文件說明
`if` 語句的主要目的是檢查一個條件是否為真，並根據該條件執行相應的程式碼。基本語法如下：

```typescript
if (condition) {
    // 當 condition 為 true 時執行的程式碼
}
```

### 使用方法
1. **基本語法**:
   - 使用 `if` 來驗證條件。
   - 可以選擇性地添加 `else` 或 `else if` 來處理不同的條件。

2. **範例語法**:
   ```typescript
   if (x > 10) {
       console.log("x 大於 10");
   } else {
       console.log("x 小於或等於 10");
   }
   ```

3. **多重條件**:
   - 可以使用邏輯運算符（如 `&&` 和 `||`）來檢查多個條件。

### 範例
以下是一些 `if` 語句的基本使用範例：

1. **單一條件**:
   ```typescript
   let age: number = 20;
   if (age >= 18) {
       console.log("你是成年人。");
   }
   ```

2. **使用 else**:
   ```typescript
   let score: number = 75;
   if (score >= 60) {
       console.log("你及格了！");
   } else {
       console.log("你未及格。");
   }
   ```

3. **多重條件**:
   ```typescript
   let temperature: number = 30;
   if (temperature > 30) {
       console.log("天氣很熱。");
   } else if (temperature >= 20) {
       console.log("天氣適中。");
   } else {
       console.log("天氣寒冷。");
   }
   ```

## 解釋
在使用 `if` 語句時，開發者可能會遇到一些常見的陷阱，包括：

- **布林值的誤解**：在 TypeScript 中，條件表達式必須返回布林值（true 或 false）。如果使用了其他類型，可能會導致意外的行為。
- **括號的使用**：在多重條件語句中，正確的使用括號是非常重要的，以避免邏輯錯誤。
- **未涵蓋的條件**：如果沒有適當處理 `else` 情況，可能會導致程式無法正確反應所有可能的狀態。

## 總結
`if` 條件語句是 TypeScript 中處理邏輯判斷的基礎，讓開發者能根據條件執行不同的程式碼區塊，從而增強程式的靈活性。
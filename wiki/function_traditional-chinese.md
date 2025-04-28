<!--
Meta Description: # TypeScript 函數：完整指南與範例 ## 摘要 TypeScript 中的函數是組織和重用代碼的基本單位。它們可以接受參數、返回值，並支持多種功能，包括類型註解和可選參數。 ## 文檔 函數是 TypeScript 和 JavaScript 中的核心概念。它們允許開發者封裝可重用的邏輯，...
Meta Keywords: typescript, number, function, return, console
-->

# TypeScript 函數：完整指南與範例

## 摘要
TypeScript 中的函數是組織和重用代碼的基本單位。它們可以接受參數、返回值，並支持多種功能，包括類型註解和可選參數。

## 文檔
函數是 TypeScript 和 JavaScript 中的核心概念。它們允許開發者封裝可重用的邏輯，使得代碼更加模組化和可讀。TypeScript 對函數提供了強大的類型系統，這使得函數的使用更加安全和可靠。

### 基本語法
```typescript
function 函數名稱(參數: 類型): 返回類型 {
    // 函數主體
    return 返回值;
}
```

### 使用方式
1. **定義函數**：使用 `function` 關鍵字來定義函數，後接函數名稱、參數列表及返回類型。
2. **呼叫函數**：通過函數名稱加上括號來執行函數，並根據需求傳遞參數。
3. **可選參數**：可以使用 `?` 來標註可選參數，這樣呼叫函數時可以選擇性地省略這些參數。
4. **默認參數**：可以為參數設定默認值，當呼叫函數時若未提供該參數，將使用默認值。

### 返回值
函數的返回類型可以是任意類型，甚至可以是 `void`，表示該函數不返回任何值。

## 範例
### 基本函數範例
```typescript
function 加法(a: number, b: number): number {
    return a + b;
}

let 結果 = 加法(5, 3); // 結果為 8
```

### 可選參數範例
```typescript
function 打招呼(name: string, greeting?: string): string {
    return greeting ? `${greeting}, ${name}!` : `你好, ${name}!`;
}

console.log(打招呼("小明")); // 輸出：你好, 小明!
console.log(打招呼("小明", "早安")); // 輸出：早安, 小明!
```

### 默認參數範例
```typescript
function 計算利息(本金: number, 利率: number = 0.05): number {
    return 本金 * 利率;
}

console.log(計算利息(1000)); // 輸出：50
console.log(計算利息(1000, 0.1)); // 輸出：100
```

## 解釋
使用函數時需注意以下幾點：
- **類型不匹配**：確認傳遞的參數類型與定義的類型一致，否則會導致編譯錯誤。
- **可選參數的順序**：可選參數必須放在必需參數的後面，否則 TypeScript 會報錯。
- **返回類型的推斷**：若未明確指定返回類型，TypeScript 會根據函數的實現自動推斷，這在大多數情況下是安全的，但明確指定會更好。

## 一句總結
TypeScript 函數是結構化代碼的重要工具，支持類型註解和參數的靈活性，使開發者能夠編寫更安全和可維護的代碼。
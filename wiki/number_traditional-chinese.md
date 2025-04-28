<!--
Meta Description: # TypeScript 數字型別 (number) 完全指南 ## 概述 TypeScript 的 `number` 型別用於表示所有數字，包括整數和浮點數。它是 TypeScript 中的一個基本型別，無論是數學計算還是處理數據時，`number` 型別都扮演著重要的角色。 ## 文檔 在 Ty...
Meta Keywords: number, typescript, let, nan, math
-->

# TypeScript 數字型別 (number) 完全指南

## 概述
TypeScript 的 `number` 型別用於表示所有數字，包括整數和浮點數。它是 TypeScript 中的一個基本型別，無論是數學計算還是處理數據時，`number` 型別都扮演著重要的角色。

## 文檔
在 TypeScript 中，`number` 型別用於表示數字，無論是整數、負數還是浮點數。它遵循 JavaScript 的數字表示方式，這意味著所有的數字都以 IEEE 754 雙精度浮點格式儲存，範圍從 -2^53 + 1 到 2^53 - 1 之間的整數。

### 用法
使用 `number` 型別非常簡單。可以直接在變數宣告中指定型別，或在函數參數和返回值中使用。以下是一些基本用法：

```typescript
let age: number = 25;
let price: number = 19.99;
let temperature: number = -5;
```

TypeScript 會對數字進行靜態類型檢查，確保變數只接受數字類型的值。

### 詳細說明
- **操作**: TypeScript 中的 `number` 可以進行各種數學運算，包括加法、減法、乘法和除法。
- **數學函數**: TypeScript 也支援 JavaScript 的數學函數，如 `Math.sqrt()`, `Math.random()`, 等等。
- **特殊數字**: `number` 型別也包括特殊數字，如 `NaN` (非數字) 和 `Infinity` (無限)。

## 範例
以下是一些使用 `number` 型別的基本範例：

```typescript
let x: number = 10;
let y: number = 20;

let sum: number = x + y; // 30
let difference: number = x - y; // -10
let product: number = x * y; // 200
let quotient: number = y / x; // 2
let squareRoot: number = Math.sqrt(x); // 3.1622776601683795
```

## 解釋
在使用 `number` 型別時，有一些常見的陷阱和注意事項：

1. **浮點數精度**: 由於浮點數的表示方式，某些數學計算可能會產生精度問題，例如 `0.1 + 0.2` 可能不等於 `0.3`。
2. **NaN 檢查**: 使用 `isNaN()` 函數來檢查數字是否為 `NaN`，因為 `NaN` 與任何值都不相等，包括它自己。
3. **類型強制**: 在某些情況下，數字可能被隱式轉換為字符串，特別是在與字符串進行拼接時，需要小心類型強制。

## 一句話總結
TypeScript 的 `number` 型別用於表示所有數字，並允許進行各種數學運算。
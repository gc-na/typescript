<!--
Meta Description: # TypeScript 數字類型（number）完全指南 ## 概述 在 TypeScript 中，`number` 是一種基本數據類型，用於表示所有數值，包括整數、浮點數和特殊值如 `NaN` 和 `Infinity`。 ## 文檔 TypeScript 的 `number` 類型旨在提供一個統...
Meta Keywords: number, let, typescript, nan, infinity
-->

# TypeScript 數字類型（number）完全指南

## 概述
在 TypeScript 中，`number` 是一種基本數據類型，用於表示所有數值，包括整數、浮點數和特殊值如 `NaN` 和 `Infinity`。

## 文檔
TypeScript 的 `number` 類型旨在提供一個統一的數值表示，無論是整數還是浮點數，均可通過 `number` 類型來處理。`number` 類型遵循 JavaScript 的數字表示規則，這意味著所有的數字都是以 IEEE 754 雙精度浮點格式存儲。

### 目的
`number` 類型的主要目的是在 TypeScript 中安全、有效地處理數值，並且提供靜態類型檢查的優勢。

### 用法
在 TypeScript 中，您可以通過以下方式聲明 `number` 類型的變量：

```typescript
let age: number = 30;
let price: number = 19.99;
let temperature: number = -10.5;
```

您還可以進行數學運算和其他數值操作，TypeScript 會自動檢查類型的一致性。

## 示例
以下是一些基本用法的示例：

```typescript
let x: number = 5;
let y: number = 10;

// 數學運算
let sum: number = x + y;       // 15
let product: number = x * y;   // 50

// 浮點數
let pi: number = 3.14;

// 特殊值
let notANumber: number = NaN;   // 非數字
let infinity: number = Infinity; // 無限大
```

## 解釋
在使用 `number` 類型時，一些常見的陷阱包括：

- **浮點數精度問題**：由於使用了雙精度浮點格式，某些浮點數運算可能會產生意外的結果，例如 `0.1 + 0.2` 可能不等於 `0.3`。
- **NaN 處理**：`NaN` 代表“不是一個數字”，任何與 `NaN` 進行的比較都會返回 `false`，包括 `NaN === NaN`。
- **無限大**：`Infinity` 代表一個超過最大可表示數字的值，這在數學運算中可能導致意外行為。

## 一句總結
TypeScript 中的 `number` 類型是用於表示所有數值的基本數據類型，支持整數、浮點數及特殊數值。
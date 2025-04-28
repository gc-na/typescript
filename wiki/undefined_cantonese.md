<!--
Meta Description: # TypeScript 中的 undefined：用法與注意事項 ## 簡介 在 TypeScript 中，`undefined` 是一個基本數據類型，代表一個變數尚未被賦值的狀態。了解 `undefined` 的特性有助於提高 TypeScript 編程的安全性和可讀性。 ## 文檔 ### 目...
Meta Keywords: undefined, typescript, number, null, console
-->

# TypeScript 中的 undefined：用法與注意事項

## 簡介
在 TypeScript 中，`undefined` 是一個基本數據類型，代表一個變數尚未被賦值的狀態。了解 `undefined` 的特性有助於提高 TypeScript 編程的安全性和可讀性。

## 文檔
### 目的
`undefined` 用於表示變數的缺失值或未定義狀態。當一個變數被聲明但未賦值時，預設值為 `undefined`。

### 用法
在 TypeScript 中，可以直接使用 `undefined` 來檢查變數是否已被賦值。以下是一些使用 `undefined` 的情況：

1. **變數聲明**：當變數被聲明但沒有初始化時，其值為 `undefined`。
2. **函數返回值**：若函數不返回任何值，則預設返回 `undefined`。
3. **物件屬性**：如果物件的某個屬性不存在，訪問該屬性會返回 `undefined`。

### 詳細信息
- `undefined` 與 `null` 不同，`null` 是一個有意義的空值，而 `undefined` 則表示缺少值。
- 在 `strictNullChecks` 模式下，`undefined` 需要明確處理，否則會導致編譯錯誤。

## 示例
```typescript
let a: number; // a 是未初始化的變數，默認為 undefined
console.log(a); // 輸出：undefined

function doNothing(): void {
    // 什麼都不做
}
console.log(doNothing()); // 輸出：undefined

let obj: { prop?: number } = {};
console.log(obj.prop); // 輸出：undefined，因為 prop 不存在
```

## 解釋
- **常見陷阱**：在使用 `undefined` 時，有時會將其與 `null` 混淆。需要注意兩者的區別。
- **注意事項**：在 `strictNullChecks` 模式下，必須明確指定變數是否可以為 `undefined`。例如，使用 `number | undefined` 來表示變數可以是 `number` 或 `undefined`。

## 一句總結
`undefined` 在 TypeScript 中表示變數未賦值的狀態，是理解變數生命週期的關鍵。
<!--
Meta Description: # TypeScript 中的 "export" 指令：模組與可重用性的關鍵 ## 簡介 在 TypeScript 中，`export` 指令是用於將變數、函數、類別或介面從一個模組導出，使其能夠在其他模組中被導入和使用。這一機制是模組化程式設計的核心，能夠提高代碼的可維護性和重用性。 ## 文檔 ...
Meta Keywords: export, typescript, number, circle, radius
-->

# TypeScript 中的 "export" 指令：模組與可重用性的關鍵

## 簡介
在 TypeScript 中，`export` 指令是用於將變數、函數、類別或介面從一個模組導出，使其能夠在其他模組中被導入和使用。這一機制是模組化程式設計的核心，能夠提高代碼的可維護性和重用性。

## 文檔
`export` 指令的主要目的是允許開發者在不同的 TypeScript 檔案之間共享代碼。這樣可以將程式碼組織得更有條理，並促進團隊協作。TypeScript 支持兩種導出方式：命名導出（named exports）和預設導出（default exports）。

### 使用方式
1. **命名導出**：可以導出多個成員，使用 `export` 關鍵字直接在聲明前。
   ```typescript
   export const PI = 3.14;
   export function add(a: number, b: number): number {
       return a + b;
   }
   ```

2. **預設導出**：每個模組只能有一個預設導出，使用 `export default`。
   ```typescript
   export default class Circle {
       constructor(public radius: number) {}
       area(): number {
           return PI * this.radius * this.radius;
       }
   }
   ```

### 導入方式
導入導出的成員時，使用 `import` 指令：
```typescript
import { PI, add } from './math';
import Circle from './Circle';
```

## 範例
### 命名導出範例
```typescript
// math.ts
export const PI = 3.14;
export function multiply(x: number, y: number): number {
    return x * y;
}

// app.ts
import { PI, multiply } from './math';
console.log(PI); // 3.14
console.log(multiply(2, 3)); // 6
```

### 預設導出範例
```typescript
// Circle.ts
export default class Circle {
    constructor(public radius: number) {}
    area(): number {
        return Math.PI * this.radius * this.radius;
    }
}

// app.ts
import Circle from './Circle';
const myCircle = new Circle(5);
console.log(myCircle.area()); // 78.53981633974483
```

## 解釋
在使用 `export` 時，開發者需要注意以下幾點：

1. **命名衝突**：在導入多個模組時，可能會遇到成員名稱重複的情況。這時可以使用 `as` 重新命名導入的成員。
   ```typescript
   import { add as sum } from './math';
   ```

2. **循環依賴**：如果兩個模組互相導入，可能產生循環依賴問題，導致無法獲取正確的值。

3. **未導出成員的可見性**：在模組內部未使用 `export` 的成員將無法在其他模組中訪問。

## 一句總結
`export` 指令是 TypeScript 中實現模組化和代碼重用的基礎，允許開發者輕鬆共享和管理代碼。
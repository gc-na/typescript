<!--
Meta Description: # TypeScript 中的 "export" 關鍵字：一個全面的指南 ## 概述 在 TypeScript 中，`export` 關鍵字用於從一個模塊導出變量、函數、類或接口，以便在其他模塊中使用。這使得代碼更加模組化和可重用。 ## 文檔 `export` 關鍵字的主要目的是讓開發者能夠將模塊...
Meta Keywords: export, typescript, number, file, add
-->

# TypeScript 中的 "export" 關鍵字：一個全面的指南

## 概述
在 TypeScript 中，`export` 關鍵字用於從一個模塊導出變量、函數、類或接口，以便在其他模塊中使用。這使得代碼更加模組化和可重用。

## 文檔
`export` 關鍵字的主要目的是讓開發者能夠將模塊中的特定成員公開給其他模塊。這有助於組織和管理大型應用程式的代碼結構。TypeScript 支持兩種導出方式：命名導出和默認導出。

### 用法
1. **命名導出**：
   使用 `export` 關鍵字將變量、函數或類導出。
   ```typescript
   // file: math.ts
   export const PI = 3.14;
   
   export function add(x: number, y: number): number {
       return x + y;
   }
   ```

2. **默認導出**：
   使用 `export default` 將某個成員設為默認導出。
   ```typescript
   // file: calculator.ts
   export default class Calculator {
       add(x: number, y: number): number {
           return x + y;
       }
   }
   ```

### 導入
導入導出的成員時，使用 `import` 關鍵字。
```typescript
// file: app.ts
import { PI, add } from './math';
import Calculator from './calculator';

console.log(PI); // 3.14
console.log(add(2, 3)); // 5
const calc = new Calculator();
console.log(calc.add(5, 7)); // 12
```

## 例子
### 基本用法
```typescript
// file: shapes.ts
export class Circle {
    constructor(public radius: number) {}
    area() {
        return Math.PI * this.radius ** 2;
    }
}

// file: app.ts
import { Circle } from './shapes';

const myCircle = new Circle(5);
console.log(myCircle.area()); // 78.53981633974483
```

## 解釋
在使用 `export` 時，開發者應注意以下幾點：
- **命名衝突**：在導入多個模塊時，可能會發生命名衝突。這時可以使用別名來解決。
- **循環依賴**：若模塊 A 導入模塊 B 而模塊 B 又導入模塊 A，可能會導致循環依賴的問題。
- **默認導出 vs 命名導出**：默認導出只能有一個，而命名導出可以有多個，選擇時需要根據需要進行判斷。

## 總結
`export` 使得 TypeScript 的模塊化開發變得更加高效，促進了代碼的重用和組織。
<!--
Meta Description: # TypeScript 中的 import 語法詳解 ## 簡介 在 TypeScript 中，`import` 語法是用來引入模組、函式、類別或變數等，便於代碼的重用與組織。透過 `import`，開發者可以將不同文件中的代碼整合，提升開發效率。 ## 文檔 `import` 語法的主要目的是讓...
Meta Keywords: import, typescript, log, from, module
-->

# TypeScript 中的 import 語法詳解

## 簡介
在 TypeScript 中，`import` 語法是用來引入模組、函式、類別或變數等，便於代碼的重用與組織。透過 `import`，開發者可以將不同文件中的代碼整合，提升開發效率。

## 文檔
`import` 語法的主要目的是讓 TypeScript 支持模組化編程，這樣能夠更好地管理大型應用程式的結構。使用 `import` 可以從其他檔案引入函數、類別或變數，並且可以指定引入的名稱。

### 語法
```typescript
import { Feature } from './module'; // 從 module.ts 引入 Feature
import Feature from './module'; // 默認導出
import * as Module from './module'; // 將所有導出作為一個命名空間引入
```

### 使用方式
1. **引入單個導出**:
   - 使用大括號 `{}` 引入指定的導出。
2. **默認導出**:
   - 如果模組使用 `export default`，則可以直接使用導入的名稱。
3. **命名空間導入**:
   - 使用 `import * as` 將所有導出引入到一個命名空間中，便於訪問。

## 範例
以下是 `import` 語法的基本使用範例：

### 引入單個導出
```typescript
// math.ts
export const add = (a: number, b: number) => a + b;

// app.ts
import { add } from './math';
console.log(add(2, 3)); // 輸出: 5
```

### 默認導出
```typescript
// logger.ts
const log = (message: string) => console.log(message);
export default log;

// app.ts
import log from './logger';
log('Hello, TypeScript!'); // 輸出: Hello, TypeScript!
```

### 命名空間導入
```typescript
// shapes.ts
export const circle = { radius: 5 };
export const square = { side: 10 };

// app.ts
import * as Shapes from './shapes';
console.log(Shapes.circle.radius); // 輸出: 5
```

## 解說
- **常見陷阱**:
  - 確保導入的路徑正確，否則會導致編譯錯誤。
  - 若模組未正確導出，將無法正常引入。
- **注意事項**:
  - 在使用相對路徑時，應該使用 `./` 或 `../` 來指定位置。
  - TypeScript 支持 ES6 模組語法，因此可以與現有的 JavaScript 代碼無縫整合。

## 總結
`import` 語法是 TypeScript 中模組化編程的核心，能夠有效地組織和管理代碼。
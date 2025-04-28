<!--
Meta Description: # TypeScript 中的 default 關鍵字 ## 簡介 在 TypeScript 中，`default` 關鍵字主要用於模塊導出，允許開發者定義一個默認導出，方便其他模塊進行引用。 ## 文檔 `default` 關鍵字在 TypeScript 中的主要用途是標識模塊的默認導出。當一個模...
Meta Keywords: default, typescript, person, export, from
-->

# TypeScript 中的 default 關鍵字

## 簡介
在 TypeScript 中，`default` 關鍵字主要用於模塊導出，允許開發者定義一個默認導出，方便其他模塊進行引用。

## 文檔
`default` 關鍵字在 TypeScript 中的主要用途是標識模塊的默認導出。當一個模塊使用 `export default` 導出一個值時，該值在導入時可以使用任何名稱進行引用，這樣提升了代碼的靈活性和可讀性。

### 用法
在 TypeScript 模塊中，使用 `default` 進行導出和導入的基本格式如下：

#### 導出範例：
```typescript
// myModule.ts
const myFunction = () => {
    console.log("Hello from myFunction!");
};

export default myFunction;
```

#### 導入範例：
```typescript
// anotherFile.ts
import anyName from './myModule';

anyName(); // 輸出: Hello from myFunction!
```

## 範例
以下是使用 `default` 的一些基本範例：

### 範例 1: 導出一個函數
```typescript
// greeting.ts
const greet = (name: string) => `Hello, ${name}!`;
export default greet;
```
導入方式：
```typescript
// app.ts
import greet from './greeting';
console.log(greet("World")); // 輸出: Hello, World!
```

### 範例 2: 導出一個類
```typescript
// Person.ts
class Person {
    constructor(public name: string) {}
}
export default Person;
```
導入方式：
```typescript
// app.ts
import Person from './Person';
const person = new Person("Alice");
console.log(person.name); // 輸出: Alice
```

## 解釋
使用 `default` 關鍵字時，開發者應注意以下幾點：

1. **單一默認導出**：每個模塊只能有一個 `export default`。如果嘗試多次使用 `export default` 將導致編譯錯誤。
   
2. **命名靈活性**：在導入時，可以使用任何名稱來引用默認導出，這樣有助於避免命名衝突。

3. **與命名導出區分**：默認導出與命名導出（如 `export const`）不同，命名導出可以有多個，而默認導出只有一個。

4. **與 CommonJS 的兼容性**：在使用 TypeScript 與 CommonJS 模塊系統時，默認導出可以簡化導入過程，特別是在使用 `require` 時。

## 一句話總結
在 TypeScript 中，`default` 關鍵字用於定義模塊的默認導出，使得導入時更加靈活和方便。
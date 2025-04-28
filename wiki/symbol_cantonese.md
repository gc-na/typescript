<!--
Meta Description: # TypeScript 中的 Symbol：深度解析及實用指南 ## 簡介 在 TypeScript 中，`Symbol` 是一種原始數據類型，用於創建獨一無二的標識符，主要用於解決命名衝突及提升對象屬性的隱私性。 ## 文檔 ### 目的 `Symbol` 的主要目的是生成一個唯一的標識符，這些...
Meta Keywords: symbol, const, typescript, secret, mysymbol
-->

# TypeScript 中的 Symbol：深度解析及實用指南

## 簡介
在 TypeScript 中，`Symbol` 是一種原始數據類型，用於創建獨一無二的標識符，主要用於解決命名衝突及提升對象屬性的隱私性。

## 文檔
### 目的
`Symbol` 的主要目的是生成一個唯一的標識符，這些標識符可以作為對象的屬性鍵，並且不會與其他 `Symbol` 衝突，這使得它們非常適合於需要隱藏屬性或避免命名衝突的場景。

### 用法
在 TypeScript 中，使用 `Symbol` 需要通過 `Symbol()` 函數來創建。這個函數可以接受一個可選的描述參數，用於識別這個 `Symbol`（但這個描述不會影響其唯一性）。

```typescript
const sym1 = Symbol('description1');
const sym2 = Symbol('description2');
const sym3 = Symbol('description1'); // sym1 與 sym3 是不相等的
```

### 詳細說明
- `Symbol` 是 ECMAScript 2015（ES6）引入的數據類型。
- 每個 `Symbol` 值都是唯一的，即使它們的描述相同。
- `Symbol` 可以用作對象屬性鍵，這樣可以避免因名稱相同而引起的衝突。

## 範例
以下是一些使用 `Symbol` 的基本範例：

```typescript
// 創建 Symbol
const mySymbol = Symbol('mySymbol');

// 使用 Symbol 作為對象的屬性
const obj = {
  [mySymbol]: 'Hello, Symbol!',
};

console.log(obj[mySymbol]); // 輸出: Hello, Symbol!

// 使用 Symbol 來定義私有屬性
const secret = Symbol('secret');

class MyClass {
  [secret]() {
    return 'This is a secret method';
  }
}

const instance = new MyClass();
console.log(instance[secret]()); // 輸出: This is a secret method
```

## 解釋
### 常見陷阱
1. **描述不影響唯一性**：即使兩個 `Symbol` 擁有相同的描述，它們仍然是不同的。例如，`Symbol('foo')` 和 `Symbol('foo')` 是兩個不同的 `Symbol`。
2. **無法轉為字符串**：直接將 `Symbol` 轉換為字符串會導致錯誤。必須使用 `String(sym)` 來進行轉換。

### 附加注意事項
- `Symbol` 不支持 JSON 序列化，因此在使用 `JSON.stringify` 時，屬於 `Symbol` 的屬性會被忽略。
- `Symbol.for(key)` 方法可以創建全局 `Symbol`，這樣相同的鍵將返回相同的 `Symbol`，這對於需要跨文件共享的 `Symbol` 特別有用。

## 一句總結
`Symbol` 是 TypeScript 中一種獨一無二的原始數據類型，主要用於創建不會衝突的對象屬性鍵。
<!--
Meta Description: # TypeScript 中的 instanceof：類型檢查的利器 ## 簡介 `instanceof` 是 JavaScript 和 TypeScript 中一個強大的運算符，用於檢查一個對象是否為某個特定類別的實例。它在類型檢查和程式邏輯中扮演重要角色，特別是在面對多態性時。 ## 文檔 ##...
Meta Keywords: instanceof, typescript, true, object, mydog
-->

# TypeScript 中的 instanceof：類型檢查的利器

## 簡介
`instanceof` 是 JavaScript 和 TypeScript 中一個強大的運算符，用於檢查一個對象是否為某個特定類別的實例。它在類型檢查和程式邏輯中扮演重要角色，特別是在面對多態性時。

## 文檔
### 目的
`instanceof` 運算符的主要目的是確定一個對象是否是某個構造函數的實例，這對於確保對象的類型正確性至關重要。這對於類別型別的使用和代碼的健壯性都很有幫助。

### 用法
`instanceof` 的基本語法為：
```typescript
object instanceof constructor
```
- `object` 是要檢查的對象。
- `constructor` 是可能的類別或構造函數。

如果 `object` 是 `constructor` 的實例，則會返回 `true`，否則返回 `false`。

### 詳細信息
在 TypeScript 中，`instanceof` 不僅可以用於檢查類別的實例，還可以用來檢查接口的執行類型。在使用 `instanceof` 時，TypeScript 會根據對象的原型鏈進行檢查。

## 示例
以下是一些基本的使用範例：

### 範例 1：檢查基本類別
```typescript
class Animal {}
class Dog extends Animal {}

const myDog = new Dog();

console.log(myDog instanceof Dog); // 輸出: true
console.log(myDog instanceof Animal); // 輸出: true
console.log(myDog instanceof Object); // 輸出: true
```

### 範例 2：檢查原始數據類型
```typescript
const myString: string = "Hello, TypeScript!";
console.log(myString instanceof String); // 輸出: false
```
注意：原始數據類型不會被視為它們的包裝器類的實例。

## 解釋
在使用 `instanceof` 時，有幾個常見的陷阱需要注意：
- **原始類型**：如字符串、數字和布爾值是原始類型，不會返回 `true` 當使用 `instanceof` 檢查它們的包裝類型。
- **原型鏈**：`instanceof` 檢查對象的原型鏈，因此如果對象是從某個類別繼承而來，檢查將成功。
- **跨框架檢查**：如果對象來自不同的執行上下文（例如 iframe），`instanceof` 檢查可能會失敗，因為每個上下文都有自己的全局對象和原型鏈。

## 一句總結
`instanceof` 是 TypeScript 中用於檢查對象類型的運算符，提供了靈活而強大的類型驗證手段。
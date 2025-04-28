<!--
Meta Description: # TypeScript 中的 "new" 關鍵字：使用說明與實例 ## 簡介 在 TypeScript 中，`new` 關鍵字用於創建類的實例，這是面向對象編程的一個重要特性。通過 `new`，開發者可以生成物件，並呼叫其構造函數以初始化屬性。 ## 文件說明 ### 目的 `new` 關鍵字的主...
Meta Keywords: new, typescript, name, age, person
-->

# TypeScript 中的 "new" 關鍵字：使用說明與實例

## 簡介
在 TypeScript 中，`new` 關鍵字用於創建類的實例，這是面向對象編程的一個重要特性。通過 `new`，開發者可以生成物件，並呼叫其構造函數以初始化屬性。

## 文件說明
### 目的
`new` 關鍵字的主要目的是創建一個類的實例，並執行該類的構造函數，這樣可以為新物件分配內存並初始化其狀態。

### 用法
在 TypeScript 中，`new` 用法如下：

```typescript
const instance = new ClassName(parameters);
```

這裡，`ClassName` 是你要實例化的類，`parameters` 是傳遞給構造函數的參數。

### 詳細資訊
- `new` 關鍵字會創建一個新的物件，並將其原型鏈設置為類的原型。
- 如果類的構造函數沒有返回值，則 `new` 表達式返回這個新創建的物件。
- 如果構造函數返回一個物件，則 `new` 表達式將返回該物件，而不是新創建的物件。
- TypeScript 支持類型檢查，確保傳遞給構造函數的參數符合定義的類型。

## 示例
以下是 `new` 關鍵字的基本使用範例：

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`你好，我是 ${this.name}，我 ${this.age} 歲。`);
    }
}

const person1 = new Person("小明", 25);
person1.greet(); // 輸出：你好，我是 小明，我 25 歲。
```

在這個例子中，我們創建了一個 `Person` 類，然後使用 `new` 關鍵字創建了一個 `person1` 實例。

## 解釋
- **常見陷阱**：若未正確設置構造函數的參數類型，TypeScript 將在編譯時報錯，這可能導致運行時錯誤。
- **注意事項**：確保在使用 `new` 創建實例時，類的構造函數中有正確的初始化邏輯。若構造函數內部使用了 `this`，需確保上下文正確。
- 當實例化一個類時，必須使用 `new` 關鍵字，否則將會拋出錯誤。

## 一句總結
`new` 關鍵字在 TypeScript 中用於創建類的實例並初始化其屬性。
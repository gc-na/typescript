<!--
Meta Description: # TypeScript 中的 "super" 關鍵字 ## 概述 在 TypeScript 中，"super" 是一個關鍵字，用於訪問父類的屬性和方法，尤其是在類的繼承結構中。它使得子類能夠調用父類的功能，實現代碼的重用和擴展。 ## 文檔 在 TypeScript 中，"super" 關鍵字的主...
Meta Keywords: super, typescript, name, speak, dog
-->

# TypeScript 中的 "super" 關鍵字

## 概述
在 TypeScript 中，"super" 是一個關鍵字，用於訪問父類的屬性和方法，尤其是在類的繼承結構中。它使得子類能夠調用父類的功能，實現代碼的重用和擴展。

## 文檔
在 TypeScript 中，"super" 關鍵字的主要目的是在子類中訪問和調用父類的方法或屬性。當一個類繼承自另一個類時，子類可以使用 "super" 來引用父類的內容。

### 使用方法
- 使用 "super" 可以呼叫父類的構造函數，這在子類的構造函數中非常有用。
- 可以使用 "super" 來調用父類的方法，這樣可以在子類中擴展或改寫父類的方法的行為。

### 詳細說明
在 TypeScript 中，當你定義一個子類時，通常會使用 `extends` 關鍵字來繼承父類。在子類的構造函數中，必須先調用 `super()`，然後才能使用 `this` 關鍵字。此外，任何對父類方法的調用都需要使用 "super" 關鍵字。

## 範例
```typescript
class Animal {
    constructor(public name: string) {}

    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name); // 調用父類的構造函數
    }

    speak() {
        super.speak(); // 調用父類的方法
        console.log(`${this.name} barks.`);
    }
}

const dog = new Dog("Rex");
dog.speak();
// 輸出:
// Rex makes a noise.
// Rex barks.
```

## 解釋
使用 "super" 時，需要注意以下幾點：
- 在子類的構造函數中，必須在使用 `this` 之前調用 `super()`。
- 嘗試在子類中調用未在父類中定義的方法會導致錯誤。
- "super" 只能在子類中使用，不能在獨立的函數或方法中使用。

## 一句總結
"super" 是 TypeScript 中用於訪問和調用父類屬性和方法的關鍵字，方便實現類的繼承和功能擴展。
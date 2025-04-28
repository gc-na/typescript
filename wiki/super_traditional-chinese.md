<!--
Meta Description: # TypeScript 中的 "super" 關鍵字詳細介紹 ## 概要 在 TypeScript 中，`super` 關鍵字用於訪問和調用父類別的屬性和方法，特別是在繼承結構中，它是實現對父類功能擴展的重要工具。 ## 文檔 `super` 是一個特殊的關鍵字，主要用於類別繼承中的子類別。當子類...
Meta Keywords: super, name, typescript, makesound, class
-->

# TypeScript 中的 "super" 關鍵字詳細介紹

## 概要
在 TypeScript 中，`super` 關鍵字用於訪問和調用父類別的屬性和方法，特別是在繼承結構中，它是實現對父類功能擴展的重要工具。

## 文檔
`super` 是一個特殊的關鍵字，主要用於類別繼承中的子類別。當子類別需要訪問其父類別的屬性或方法時，可以使用 `super` 來實現。

### 用途
- 訪問父類別的屬性：當子類別的屬性名稱和父類別相同時，可以使用 `super` 來訪問父類別的屬性。
- 調用父類別的方法：在子類別中可以使用 `super.methodName()` 調用父類別的方法。

### 使用方式
在 TypeScript 中，`super` 只能在類別的構造函數中和方法中使用。使用 `super` 前必須在子類別構造函數中調用 `super()`，這樣才能正確初始化父類別。

```typescript
class Parent {
    constructor(public name: string) {}

    greet() {
        console.log(`Hello, ${this.name}!`);
    }
}

class Child extends Parent {
    constructor(name: string) {
        super(name); // 調用父類的構造函數
    }

    greet() {
        super.greet(); // 調用父類的 greet 方法
        console.log('Welcome to the TypeScript world!');
    }
}
```

## 範例
以下是使用 `super` 的基本範例：

```typescript
class Animal {
    constructor(public name: string) {}

    makeSound() {
        console.log(`${this.name} makes a sound.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name); // 調用 Animal 的構造函數
    }

    makeSound() {
        super.makeSound(); // 調用 Animal 的 makeSound 方法
        console.log(`${this.name} barks.`);
    }
}

const myDog = new Dog('Buddy');
myDog.makeSound(); // 輸出: Buddy makes a sound. Buddy barks.
```

## 解釋
### 常見陷阱
- `super` 只能在子類別中使用，無法在普通方法或函數中使用。
- 在調用父類的構造函數 `super()` 時，必須在使用 `this` 之前調用，否則會拋出錯誤。

### 注意事項
- 當多重繼承時，`super` 的行為會受到影響。TypeScript 目前不支持多重繼承，但可以透過混合模式達到類似效果。
- 確保在使用 `super` 之前，父類別已經正確定義並且可訪問。

## 一句總結
`super` 關鍵字在 TypeScript 中用於訪問和調用父類別的屬性和方法，是實現類別繼承的重要工具。
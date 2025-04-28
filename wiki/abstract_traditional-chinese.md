<!--
Meta Description: # TypeScript 的抽象（Abstract）類別與介面 ## 概述 在 TypeScript 中，抽象類別（Abstract Class）是一種不能被實例化的類別，旨在提供一個基礎，供其他類別繼承並實現其方法。這種結構有助於強制實現特定的功能或屬性，增強程式碼的可重用性與可讀性。 ## 文件...
Meta Keywords: abstract, typescript, class, dog, circle
-->

# TypeScript 的抽象（Abstract）類別與介面

## 概述
在 TypeScript 中，抽象類別（Abstract Class）是一種不能被實例化的類別，旨在提供一個基礎，供其他類別繼承並實現其方法。這種結構有助於強制實現特定的功能或屬性，增強程式碼的可重用性與可讀性。

## 文件說明
抽象類別允許開發者定義一些方法或屬性，但無需提供具體實現。子類別必須覆寫這些抽象方法，從而提供具體的實作。這在設計大型應用程式時特別有用，因為它能夠有效地管理和組織代碼。

### 用途
- 定義一個基本的類別結構，供其他類別繼承。
- 強制子類別實現特定的方法，確保一致性。
- 提供共用的屬性和方法，減少代碼重複。

### 語法與使用
在 TypeScript 中，您可以使用 `abstract` 關鍵字來定義抽象類別和抽象方法。

```typescript
abstract class Animal {
    abstract makeSound(): void; // 抽象方法

    move(): void {
        console.log("移動中...");
    }
}

class Dog extends Animal {
    makeSound(): void {
        console.log("汪汪!");
    }
}

const dog = new Dog();
dog.makeSound(); // 輸出: 汪汪!
dog.move();      // 輸出: 移動中...
```

## 範例
以下是使用抽象類別的基本範例：

```typescript
abstract class Shape {
    abstract area(): number; // 抽象方法

    toString(): string {
        return `面積: ${this.area()}`;
    }
}

class Circle extends Shape {
    constructor(private radius: number) {
        super();
    }

    area(): number {
        return Math.PI * this.radius * this.radius;
    }
}

const circle = new Circle(5);
console.log(circle.toString()); // 輸出: 面積: 78.53981633974483
```

## 解釋
在使用抽象類別時，開發者應注意以下幾點：

1. **無法實例化**：抽象類別不能被直接實例化，因此必須透過其子類別來使用。
2. **子類別覆寫**：所有子類別必須實現抽象方法，否則會導致編譯錯誤。
3. **混合使用**：抽象類別可以與介面結合使用，以便創建更靈活的程式設計。

### 常見錯誤
- 忘記在子類別中實現抽象方法會導致編譯器報錯。
- 嘗試直接實例化抽象類別也會報錯。

## 一句話總結
TypeScript 中的抽象類別提供了一種設計模式，允許開發者定義基礎類別結構，並強制子類別實現特定的功能。
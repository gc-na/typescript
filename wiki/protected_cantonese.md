<!--
Meta Description: # TypeScript 中的 "protected" 訪問修飾符 ## 概要 在 TypeScript 中，`protected` 是一種訪問修飾符，用於控制類成員的可訪問性，允許子類別訪問父類別的成員，但不允許外部程式碼直接訪問。 ## 文檔 `protected` 訪問修飾符的主要目的是為了實...
Meta Keywords: protected, typescript, string, child, sound
-->

# TypeScript 中的 "protected" 訪問修飾符

## 概要
在 TypeScript 中，`protected` 是一種訪問修飾符，用於控制類成員的可訪問性，允許子類別訪問父類別的成員，但不允許外部程式碼直接訪問。

## 文檔
`protected` 訪問修飾符的主要目的是為了實現封裝性。在 TypeScript 中，當你將類的屬性或方法標記為 `protected` 時，這些成員只能在該類及其子類中訪問，外部類別無法直接訪問這些成員。這有助於保護類的內部實現，並提供更好的代碼組織和結構。

### 用法
使用 `protected` 修飾符的方法如下：

```typescript
class Parent {
    protected message: string;

    constructor(msg: string) {
        this.message = msg;
    }

    protected showMessage(): void {
        console.log(this.message);
    }
}

class Child extends Parent {
    constructor(msg: string) {
        super(msg);
    }

    public displayMessage(): void {
        this.showMessage(); // 可以訪問父類的 protected 方法
    }
}

const child = new Child("Hello, World!");
child.displayMessage(); // 輸出: Hello, World!
// child.showMessage(); // 錯誤: 'showMessage' 是 'protected'，無法從外部訪問
```

## 示例
以下是使用 `protected` 的基本範例：

```typescript
class Animal {
    protected sound: string;

    constructor(sound: string) {
        this.sound = sound;
    }

    protected makeSound(): void {
        console.log(this.sound);
    }
}

class Dog extends Animal {
    constructor() {
        super("Woof");
    }

    public bark(): void {
        this.makeSound(); // 正確：可以訪問父類的 protected 方法
    }
}

const myDog = new Dog();
myDog.bark(); // 輸出: Woof
// myDog.makeSound(); // 錯誤: 'makeSound' 是 'protected'，無法從外部訪問
```

## 解釋
使用 `protected` 訪問修飾符時要注意以下幾點：

1. **子類訪問**: 只有子類可以訪問標記為 `protected` 的成員，這樣可以促進類之間的繼承關係。
2. **外部訪問**: 外部對象無法訪問 `protected` 成員，這有助於保護類的內部狀態和行為。
3. **可讀性**: 合理使用 `protected` 可以提高代碼的可讀性和可維護性，因為其他開發者會清楚哪些成員是可以被繼承和重用的。
4. **無法用於實例**: 嘗試從類的實例直接訪問 `protected` 成員會導致編譯錯誤，這是 `protected` 的一個重要特徵。

## 一句話總結
在 TypeScript 中，`protected` 訪問修飾符允許子類訪問父類的成員，從而實現更好的封裝和繼承。
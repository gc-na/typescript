<!--
Meta Description: # TypeScript 中的「private」關鍵字：私有屬性及方法的概念 ## 簡介 在 TypeScript 中，「private」關鍵字用於定義私有屬性和方法，這些屬性和方法只能在類內部使用，從而提高封裝性和數據保護。 ## 文檔 ### 目的 「private」關鍵字的主要目的是限制對類屬...
Meta Keywords: private, typescript, name, balance, myaccount
-->

# TypeScript 中的「private」關鍵字：私有屬性及方法的概念

## 簡介
在 TypeScript 中，「private」關鍵字用於定義私有屬性和方法，這些屬性和方法只能在類內部使用，從而提高封裝性和數據保護。

## 文檔
### 目的
「private」關鍵字的主要目的是限制對類屬性或方法的訪問，確保它們只能在類的上下文中被使用。這有助於防止外部代碼意外地改變類的內部狀態。

### 使用方法
在 TypeScript 中，您可以在類的屬性或方法前加上「private」關鍵字，這樣就將其設置為私有。例如：

```typescript
class Person {
    private name: string;

    constructor(name: string) {
        this.name = name;
    }

    private greet() {
        return `Hello, my name is ${this.name}`;
    }

    public introduce() {
        return this.greet();
    }
}
```

在上述代碼中，`name` 和 `greet` 方法是私有的，只能在 `Person` 類內部訪問。

## 示例
以下是使用「private」關鍵字的基本範例：

```typescript
class Account {
    private balance: number;

    constructor(initialBalance: number) {
        this.balance = initialBalance;
    }

    public deposit(amount: number) {
        this.balance += amount;
    }

    public getBalance() {
        return this.balance;
    }
}

const myAccount = new Account(100);
myAccount.deposit(50);
console.log(myAccount.getBalance());  // 輸出：150
// console.log(myAccount.balance);  // 錯誤：屬性 'balance' 是私有的
```

在這個例子中，`balance` 是私有的，無法直接從 `myAccount` 實例訪問。

## 解釋
使用「private」關鍵字時，有幾個常見的注意事項：
1. **訪問限制**：私有屬性和方法只能在其聲明的類內部訪問，無法在類的外部或子類中使用。
2. **潛在的錯誤**：如果嘗試在類外部訪問私有屬性，TypeScript 編譯器會報錯，這有助於及早發現錯誤。
3. **設計考量**：使用私有成員可以促進良好的面向對象設計，使類的內部實現細節對外部代碼隱藏。

## 一句總結
在 TypeScript 中，「private」關鍵字用於聲明只能在類內部訪問的私有屬性和方法，從而增強封裝性和數據保護。
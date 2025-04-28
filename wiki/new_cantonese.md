<!--
Meta Description: # TypeScript 中的 "new" 關鍵字：創建物件的利器 ## 概要 在 TypeScript 中，`new` 關鍵字用於創建類的實例，並啟動其構造函數。這是一個基本但關鍵的功能，使開發者能夠利用類的定義來創建物件。 ## 文檔 `new` 關鍵字的主要目的是為了創建一個指定類型的物件實例...
Meta Keywords: new, typescript, model, year, classname
-->

# TypeScript 中的 "new" 關鍵字：創建物件的利器

## 概要
在 TypeScript 中，`new` 關鍵字用於創建類的實例，並啟動其構造函數。這是一個基本但關鍵的功能，使開發者能夠利用類的定義來創建物件。

## 文檔
`new` 關鍵字的主要目的是為了創建一個指定類型的物件實例。當使用 `new` 關鍵字時，會執行該類的構造函數，並返回一個新的物件。這使得開發者可以利用物件導向的特性，進行數據封裝和重用。

### 使用方法
- 語法：
  ```typescript
  let instance = new ClassName(parameters);
  ```
- 其中 `ClassName` 是你定義的類，`parameters` 是可選的，取決於構造函數的定義。

### 詳細說明
- 當調用 `new ClassName()` 時，TypeScript 會自動創建一個新物件，並將其原型鏈指向該類的原型。
- 構造函數內部可以接受參數，並可用來初始化物件的屬性。
- 如果構造函數沒有返回值，則返回創建的物件；如果返回的是其他物件，則返回該物件。

## 範例
以下是使用 `new` 關鍵字的基本範例：

```typescript
class Car {
    model: string;
    year: number;

    constructor(model: string, year: number) {
        this.model = model;
        this.year = year;
    }
}

let myCar = new Car("Toyota", 2021);
console.log(myCar.model); // 輸出: Toyota
console.log(myCar.year);  // 輸出: 2021
```

## 解釋
- **常見陷阱**：如果你忘記在類的構造函數中使用 `this` 來設置屬性，則新創建的物件將不會有預期的屬性。
- **注意事項**：使用 `new` 關鍵字時，一定要確認你所調用的確實是類，而不是普通函數，否則會導致運行時錯誤。
- **附加提示**：可以使用 TypeScript 的可選參數和默認參數特性來簡化構造函數的定義。

## 一句總結
在 TypeScript 中，`new` 關鍵字用於實例化類並調用其構造函數，從而創建新的物件實例。
<!--
Meta Description: # TypeScript 中的 extends 關鍵字：類型擴展的強大工具 ## 簡介 在 TypeScript 中，`extends` 關鍵字是一個關鍵的語法元素，用於實現類型的擴展，幫助開發者創建更加靈活和可重用的代碼。它主要用於類的繼承及泛型約束。 ## 文件說明 `extends` 關鍵字在...
Meta Keywords: extends, typescript, loglength, animal, makesound
-->

# TypeScript 中的 extends 關鍵字：類型擴展的強大工具

## 簡介
在 TypeScript 中，`extends` 關鍵字是一個關鍵的語法元素，用於實現類型的擴展，幫助開發者創建更加靈活和可重用的代碼。它主要用於類的繼承及泛型約束。

## 文件說明
`extends` 關鍵字在 TypeScript 中有兩個主要用途：

1. **類的繼承**：當一個類需要繼承另一個類的屬性和方法時，可以使用 `extends` 來實現。這使得代碼更具可讀性和可維護性，並促進代碼重用。

2. **泛型約束**：在定義泛型時，`extends` 可以用來約束泛型的類型，確保傳遞的類型滿足特定的條件。這有助於提高類型安全性，減少運行時錯誤。

### 類的繼承
在 TypeScript 中，當一個類繼承另一個類時，可以使用 `extends` 關鍵字定義父類和子類之間的關係。

### 泛型約束
在定義泛型時，使用 `extends` 可以限制泛型類型的範圍，這樣可以確保只有符合特定條件的類型才能被使用。

## 範例
### 類的繼承範例
```typescript
class Animal {
    makeSound() {
        console.log("Animal sound");
    }
}

class Dog extends Animal {
    makeSound() {
        console.log("Bark");
    }
}

const myDog = new Dog();
myDog.makeSound(); // 輸出: Bark
```

### 泛型約束範例
```typescript
function logLength<T extends { length: number }>(item: T): void {
    console.log(item.length);
}

logLength("Hello"); // 輸出: 5
logLength([1, 2, 3]); // 輸出: 3
// logLength(123); // 錯誤: 123 沒有 length 屬性
```

## 解釋
使用 `extends` 時，開發者需要注意以下幾點：

- **多重繼承**：TypeScript 不支持多重繼承，當一個類繼承另一個類時，只能有一個父類。如果需要多個父類的功能，可以考慮使用接口。
  
- **泛型約束的靈活性**：在使用泛型時，`extends` 可以限定類型，但也可能限制了函數的靈活性。因此，在設計時應謹慎選擇約束的範圍。

- **類型推斷**：TypeScript 會根據上下文自動推斷類型，但當使用 `extends` 時，類型推斷可能受到影響，開發者需要留意。

## 一句總結
`extends` 關鍵字在 TypeScript 中用於類型擴展，支持類的繼承和泛型約束，提升代碼的靈活性和可維護性。
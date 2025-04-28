<!--
Meta Description: # TypeScript中的async：非同步程式設計的核心 ## 概述 `async` 是 TypeScript 中用於定義非同步函式的關鍵字，使得撰寫異步程式碼更加簡潔和易於理解。配合 `await` 使用，`async` 允許開發者在處理 Promise 時以同步的方式來撰寫程式碼。 ## 文...
Meta Keywords: async, await, promise, typescript, data
-->

# TypeScript中的async：非同步程式設計的核心

## 概述
`async` 是 TypeScript 中用於定義非同步函式的關鍵字，使得撰寫異步程式碼更加簡潔和易於理解。配合 `await` 使用，`async` 允許開發者在處理 Promise 時以同步的方式來撰寫程式碼。

## 文件說明
### 目的
`async` 的主要目的是簡化非同步程式碼的撰寫，使得開發者可以使用類似同步程式碼的結構來處理非同步操作，從而提高代碼的可讀性和可維護性。

### 使用方式
在 TypeScript 中，任何函式前加上 `async` 關鍵字即可將其定義為非同步函式。這意味著該函式會返回一個 Promise，並且可以在函式內部使用 `await` 關鍵字來等待 Promise 的結果。

#### 語法範例：
```typescript
async function myAsyncFunction(): Promise<number> {
    // 這裡可以使用 await
    let result = await someAsyncOperation();
    return result;
}
```

### 詳細說明
1. **返回值**：任何標記為 `async` 的函式都會返回一個 Promise。如果函式內部有返回值，該值將會被包裝成 Promise 返回。
2. **使用 await**：在 `async` 函式內部可以使用 `await` 關鍵字來等待 Promise 的解決，這樣可以避免使用繁瑣的 `.then()` 鏈式調用。
3. **錯誤處理**：可以使用 `try-catch` 塊來捕獲在 `await` 期間可能發生的錯誤，這使得錯誤處理更為直觀。

## 範例
### 基本用法
以下是使用 `async` 和 `await` 的簡單範例：

```typescript
async function fetchData(url: string): Promise<any> {
    try {
        let response = await fetch(url);
        let data = await response.json();
        return data;
    } catch (error) {
        console.error("獲取資料時發生錯誤:", error);
    }
}

fetchData("https://api.example.com/data")
    .then(data => console.log(data));
```

### 另一個範例
```typescript
async function addAsync(a: number, b: number): Promise<number> {
    return a + b; // 返回的值會被包裝成 Promise
}

addAsync(5, 10).then(result => console.log(result)); // 輸出 15
```

## 說明
### 常見陷阱和注意事項
1. **未捕獲的異常**：如果在 `async` 函式中使用 `await` 時發生錯誤，必須使用 `try-catch` 來捕獲這些錯誤，否則會返回未捕獲的 Promise 拒絕。
2. **不必要的 async**：如果函式沒有使用 `await`，則沒有必要將其標記為 `async`，這會造成不必要的性能開銷。
3. **Promise.all()**：如果需要同時執行多個非同步操作，可以考慮使用 `Promise.all()`，這樣可以提高效率。

## 一句話總結
`async` 是 TypeScript 中用於簡化非同步程式碼編寫的重要關鍵字，配合 `await` 使用可以有效提升程式碼的可讀性和結構性。
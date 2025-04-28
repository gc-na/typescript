<!--
Meta Description: # TypeScript 中的 async：非同步編程的利器 ## 概要 在 TypeScript 中，`async` 關鍵字使得撰寫非同步程式碼變得更加簡單和可讀。它可以與 `await` 搭配使用，讓開發者以更接近同步的方式來處理非同步操作。 ## 文檔 ### 目的 `async` 使函數返回...
Meta Keywords: async, await, data, promise, error
-->

# TypeScript 中的 async：非同步編程的利器

## 概要
在 TypeScript 中，`async` 關鍵字使得撰寫非同步程式碼變得更加簡單和可讀。它可以與 `await` 搭配使用，讓開發者以更接近同步的方式來處理非同步操作。

## 文檔
### 目的
`async` 使函數返回一個 Promise，並且可以使用 `await` 等待 Promise 的完成。這樣的設計提升了程式碼的可讀性，減少了回調地獄的問題。

### 使用方法
1. **聲明 async 函數**：在函數前加上 `async` 關鍵字。
2. **使用 await**：在 `async` 函數內，可以使用 `await` 來等待 Promise 的解決。`await` 只能在 `async` 函數內使用。

### 詳細信息
- `async` 函數自動返回一個 Promise，即使你沒有顯式返回。
- 當函數內部發生錯誤時，會返回一個 rejected 的 Promise，因此可以使用 `try...catch` 來捕獲錯誤。

## 範例
### 基本用法
```typescript
async function fetchData(url: string): Promise<any> {
    const response = await fetch(url);
    const data = await response.json();
    return data;
}

fetchData('https://api.example.com/data')
    .then(data => console.log(data))
    .catch(error => console.error('Error fetching data:', error));
```

### 使用 try...catch 捕獲錯誤
```typescript
async function getUserData(userId: number): Promise<void> {
    try {
        const user = await fetch(`https://api.example.com/users/${userId}`);
        const data = await user.json();
        console.log(data);
    } catch (error) {
        console.error('Error fetching user data:', error);
    }
}

getUserData(1);
```

## 解釋
- **常見問題**：`async` 函數只能在 `async` 環境下使用 `await`，否則會引發語法錯誤。
- **注意事項**：`await` 會阻塞後續代碼的執行，直到 Promise 被解決，因此需謹慎使用在性能敏感的區域。

## 一句總結
`async` 關鍵字在 TypeScript 中使非同步編程更加簡單和可讀，並提高了錯誤處理的效率。
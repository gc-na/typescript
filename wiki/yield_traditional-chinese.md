<!--
Meta Description: # TypeScript 中的 yield 關鍵字詳解 ## 簡介 在 TypeScript 中，`yield` 是一個用於生成器函數的關鍵字。它使得函數可以暫停執行，並在之後的某個時刻恢復，從而實現迭代生成值的功能。 ## 文檔 ### 目的 `yield` 允許開發者在生成器函數中逐步生成一系列...
Meta Keywords: yield, next, generator, value, console
-->

# TypeScript 中的 yield 關鍵字詳解

## 簡介
在 TypeScript 中，`yield` 是一個用於生成器函數的關鍵字。它使得函數可以暫停執行，並在之後的某個時刻恢復，從而實現迭代生成值的功能。

## 文檔
### 目的
`yield` 允許開發者在生成器函數中逐步生成一系列值，這對於處理大量數據或異步操作特別有用。生成器函數通過使用 `function*` 定義，並使用 `yield` 來返回值。

### 用法
生成器函數的基本語法如下：
```typescript
function* generatorFunction() {
    yield value1;
    yield value2;
    // ...
}
```
在這個函數中，每次調用 `next()` 方法時，函數的執行會在 `yield` 關鍵字處暫停，並返回相應的值。

### 詳細說明
1. **創建生成器**: 使用 `function*` 定義生成器函數，並在函數內部使用 `yield` 關鍵字生成值。
2. **調用生成器**: 生成器函數不會立即執行，而是返回一個生成器對象。可以使用 `next()` 方法來獲取生成的值。
3. **狀態保持**: 每次調用 `next()` 都會從上次暫停的地方繼續執行，這使得生成器能夠保持狀態。

## 範例
### 基本用法範例
以下範例展示了如何使用 `yield` 來生成一系列的數字：
```typescript
function* numberGenerator() {
    let index = 0;
    while (index < 5) {
        yield index++;
    }
}

const generator = numberGenerator();

console.log(generator.next().value); // 0
console.log(generator.next().value); // 1
console.log(generator.next().value); // 2
console.log(generator.next().value); // 3
console.log(generator.next().value); // 4
console.log(generator.next().value); // undefined
```

## 解釋
### 常見陷阱與注意事項
1. **生成器的結束**: 當生成器函數執行完畢後，再次調用 `next()` 會返回 `{ value: undefined, done: true }`，這表示生成器已經耗盡。
2. **多次調用**: 如果在生成器函數內部有多個 `yield`，每次調用 `next()` 都會依次返回下一個 `yield` 的值。
3. **非同步操作**: 雖然 `yield` 可以與 Promise 結合使用，但需要使用 `async`/`await` 結構來處理異步行為。

## 一句總結
`yield` 是 TypeScript 中生成器函數的重要組成部分，允許函數暫停執行並逐步生成值。
<!--
Meta Description: # TypeScript 中的 await：异步编程的核心 ## 概述 `await` 是 TypeScript 中用于处理异步操作的重要关键字。它使得异步代码的编写更为直观，允许开发者像编写同步代码一样处理异步任务。 ## 文档 ### 目的 `await` 关键字用于等待一个返回 Promise...
Meta Keywords: await, promise, typescript, async, data
-->

# TypeScript 中的 await：异步编程的核心

## 概述
`await` 是 TypeScript 中用于处理异步操作的重要关键字。它使得异步代码的编写更为直观，允许开发者像编写同步代码一样处理异步任务。

## 文档
### 目的
`await` 关键字用于等待一个返回 Promise 的异步函数的结果。它只能在 `async` 函数内部使用，能够简化异步代码的结构并提高可读性。

### 用法
在 TypeScript 中，使用 `await` 的基本语法如下：

```typescript
async function example() {
    const result = await someAsyncFunction();
    console.log(result);
}
```

- `async` 关键字用于定义一个异步函数。
- `await` 关键字用于等待 Promise 解析后的值。

### 细节
1. **Promise 对象**：`await` 后面必须是一个 Promise 对象。如果不是，`await` 将会抛出错误。
2. **错误处理**：使用 `try...catch` 语句来捕获在 `await` 过程中可能发生的错误。
3. **并行执行**：如果需要并行执行多个异步操作，推荐使用 `Promise.all()` 而不是多个 `await` 语句。

## 示例
### 基本用法
```typescript
async function fetchData() {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
}

fetchData();
```

### 错误处理
```typescript
async function fetchDataWithErrorHandling() {
    try {
        const response = await fetch('https://api.example.com/data');
        if (!response.ok) {
            throw new Error('网络响应错误');
        }
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('获取数据时出错:', error);
    }
}

fetchDataWithErrorHandling();
```

## 说明
1. **常见陷阱**：在 `async` 函数外使用 `await` 会导致语法错误。
2. **性能注意**：如果在循环中使用 `await`，会导致每个 Promise 按顺序执行，可能影响性能。考虑使用 `Promise.all()` 进行并行处理。
3. **返回值**：`async` 函数总是返回一个 Promise，即使函数中没有使用 `await`。

## 一句话总结
`await` 关键字在 TypeScript 中用于简化异步编程，使得开发者可以以同步的方式处理异步操作。
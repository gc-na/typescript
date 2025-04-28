<!--
Meta Description: # Understanding `async` in TypeScript: A Complete Guide ## Synopsis The `async` keyword in TypeScript is used to define functions that return a promis...
Meta Keywords: async, promise, function, await, error
-->

# Understanding `async` in TypeScript: A Complete Guide

## Synopsis
The `async` keyword in TypeScript is used to define functions that return a promise, enabling the use of asynchronous programming with a cleaner, more readable syntax using `await`.

## Documentation
In TypeScript, the `async` keyword is a crucial part of working with asynchronous operations. When a function is declared with the `async` keyword, it automatically returns a promise, regardless of whether the function explicitly returns a value. This feature allows developers to write asynchronous code that looks synchronous, making it easier to read and maintain.

### Purpose
The primary purpose of `async` is to simplify the handling of asynchronous operations, such as API calls, file reads, or database queries. By using `async` in conjunction with `await`, developers can write code that flows more naturally, avoiding the complexity of traditional promise chaining.

### Usage
To declare an asynchronous function, simply prefix the function definition with `async`. Inside this function, you can use the `await` keyword to pause the execution until the promise is resolved.

### Syntax
```typescript
async function functionName(parameters): Promise<ReturnType> {
    // function body
}
```

## Examples
### Basic Usage
Here is a straightforward example of an async function that fetches data from an API:

```typescript
async function fetchData(url: string): Promise<any> {
    const response = await fetch(url);
    const data = await response.json();
    return data;
}

// Usage
fetchData('https://api.example.com/data')
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

### Using Async with Error Handling
You can also use `try...catch` to handle errors in async functions:

```typescript
async function getUserData(userId: string): Promise<any> {
    try {
        const response = await fetch(`https://api.example.com/users/${userId}`);
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        const userData = await response.json();
        return userData;
    } catch (error) {
        console.error('Failed to fetch user data:', error);
    }
}
```

## Explanation
### Common Pitfalls
1. **Forgetting to Use `await`:** If you forget to use `await` in an `async` function, the function will return a promise instead of the resolved value.
2. **Returning Non-Promise Values:** Even if you return a non-promise value in an `async` function, it will still be wrapped in a promise. This can lead to confusion if not properly understood.
3. **Unhandled Promise Rejections:** If a promise is rejected and not handled, it may lead to unhandled promise rejection warnings. Always ensure to handle errors using `try...catch` or `.catch()`.

### Gotchas
- **Async Functions and the Event Loop:** Async functions do not block the event loop, allowing other operations to continue while awaiting a promise.
- **Execution Order:** The order of execution can sometimes be non-intuitive, especially when mixing synchronous and asynchronous code.

## One Line Summary
The `async` keyword in TypeScript simplifies asynchronous programming by allowing functions to return promises and enabling the use of `await` for cleaner code flow.
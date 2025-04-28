<!--
Meta Description: # TypeScript 中的 var 关键字详解 ## 简介 `var` 是 JavaScript 和 TypeScript 中用于声明变量的关键字。尽管在现代 JavaScript 中，`let` 和 `const` 已经成为更推荐的选择，但理解 `var` 的特性仍然对 TypeScript ...
Meta Keywords: var, typescript, let, const, javascript
-->

# TypeScript 中的 var 关键字详解

## 简介
`var` 是 JavaScript 和 TypeScript 中用于声明变量的关键字。尽管在现代 JavaScript 中，`let` 和 `const` 已经成为更推荐的选择，但理解 `var` 的特性仍然对 TypeScript 开发者非常重要。

## 文档
`var` 用于声明一个变量，可以在函数作用域或全局作用域中使用。与 `let` 和 `const` 不同，`var` 声明的变量不受块级作用域限制，而是以函数或全局为作用域。

### 目的
使用 `var` 声明变量的主要目的是为了在代码中定义一个可以被重写和访问的标识符。

### 用法
- **声明变量**：使用 `var` 来声明一个变量。
- **作用域**：`var` 声明的变量是函数作用域的，如果在函数外使用 `var` 声明，它将成为全局变量。

### 细节
- **变量提升**：`var` 声明的变量会被提升到函数或全局作用域的顶部，因此在声明之前可以访问这些变量，但值为 `undefined`。
- **重复声明**：在同一作用域内，可以多次使用 `var` 来声明同一个变量。

## 示例
```typescript
// 示例 1: 在函数内使用 var
function exampleFunction() {
    var x = 10;
    if (true) {
        var x = 20; // 同一变量
        console.log(x); // 输出 20
    }
    console.log(x); // 输出 20
}

exampleFunction();

// 示例 2: 在全局作用域中使用 var
var globalVar = "我是全局变量";
function globalFunction() {
    console.log(globalVar); // 输出 "我是全局变量"
}

globalFunction();
```

## 解释
使用 `var` 时，需要注意以下几点：
- **变量提升可能导致意外行为**：由于变量提升，代码可能在变量声明之前就被调用，导致初始值为 `undefined`。
- **块级作用域的缺失**：在循环或条件语句中使用 `var` 时，所有的声明都共享同一个作用域，可能导致逻辑错误。
- **不推荐在现代开发中使用**：由于 `let` 和 `const` 提供了更好的块级作用域控制，现代 JavaScript 和 TypeScript 开发中推荐使用它们。

## 一句总结
`var` 是 TypeScript 中用于声明变量的关键字，但由于其作用域和提升特性，现代开发中更推荐使用 `let` 和 `const`。
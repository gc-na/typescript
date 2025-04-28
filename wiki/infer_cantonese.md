<!--
Meta Description: # TypeScript 中的 infer：類型推斷的強大工具 ## 概述 在 TypeScript 中，`infer` 是一個用於類型推斷的關鍵字，通常與條件類型一起使用，幫助開發者在類型系統中靈活地提取和推斷類型信息。 ## 文件說明 `infer` 的主要目的是在定義條件類型時，從給定的類型中...
Meta Keywords: infer, typescript, type, unwrappromise, number
-->

# TypeScript 中的 infer：類型推斷的強大工具

## 概述
在 TypeScript 中，`infer` 是一個用於類型推斷的關鍵字，通常與條件類型一起使用，幫助開發者在類型系統中靈活地提取和推斷類型信息。

## 文件說明
`infer` 的主要目的是在定義條件類型時，從給定的類型中提取一個子類型，這對於創建更通用的類型或處理複雜類型非常有用。當使用 `infer` 時，開發者可以在條件類型的上下文中捕獲類型並在其他地方使用它。

### 使用方法
`infer` 主要在條件類型中使用，語法如下：

```typescript
type ExtractType<T> = T extends SomeType<infer U> ? U : never;
```

在這個例子中，如果 `T` 是一個符合 `SomeType` 的類型，那麼 `U` 將被推斷為 `SomeType` 的泛型參數。

## 例子
以下是一個簡單的 `infer` 使用示例：

```typescript
type UnwrapPromise<T> = T extends Promise<infer U> ? U : T;

type Result = UnwrapPromise<Promise<number>>; // Result 將是 number
type Direct = UnwrapPromise<number>; // Direct 將是 number
```

在這個例子中，`UnwrapPromise` 類型會根據 `T` 是否為 `Promise` 類型來推斷其內部類型。

## 解釋
使用 `infer` 的常見問題包括：

1. **上下文限制**：`infer` 只能在條件類型的上下文中使用，無法單獨使用。
2. **類型不匹配**：如果 `T` 不符合 `extends` 的條件，`infer` 將無法工作，並返回 `never`。
3. **可讀性問題**：過度使用 `infer` 可能會使類型定義變得難以理解，適當使用是關鍵。

## 總結
`infer` 是 TypeScript 中一個強大且靈活的工具，能夠輕鬆地從複雜類型中推斷和提取類型信息。
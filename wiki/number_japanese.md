<!--
Meta Description: # TypeScriptにおける「number」型の完全ガイド ## 概要 TypeScriptの「number」型は、整数や浮動小数点数を含む全ての数値を表現するための基本的なデータ型です。本記事では、「number」型の使用方法、特徴、注意点について詳しく解説します。 ## ドキュメント Typ...
Meta Keywords: number, let, typescriptの, typescript, nan
-->

# TypeScriptにおける「number」型の完全ガイド

## 概要
TypeScriptの「number」型は、整数や浮動小数点数を含む全ての数値を表現するための基本的なデータ型です。本記事では、「number」型の使用方法、特徴、注意点について詳しく解説します。

## ドキュメント
TypeScriptの「number」型は、JavaScriptの数値型を基にしており、整数、浮動小数点数、NaN（Not-a-Number）、およびInfinity（無限大）をサポートしています。「number」型は、数値演算や比較に使用され、型安全性を提供します。

### 使用方法
TypeScriptでは、変数を「number」型に指定することができます。型注釈を使用することで、変数に数値のみを割り当てることを強制します。

```typescript
let age: number = 25;
let price: number = 19.99;
```

TypeScriptは、数値演算を行う際に自動的に型を推論するため、明示的に型を指定しなくても「number」として扱われます。

```typescript
let result = age + price; // resultはnumber型
```

## 例
以下は、「number」型の基本的な使用例です。

```typescript
// 整数の例
let integer: number = 100;

// 浮動小数点数の例
let decimal: number = 3.14;

// NaNの例
let invalidNumber: number = NaN;

// Infinityの例
let infinite: number = Infinity;

// 数値演算
let total: number = integer + decimal; // totalは103.14
```

## 説明
「number」型を使用する際の注意点や一般的な落とし穴について説明します。

1. **NaNの扱い**: NaNは数値型ですが、数値ではありません。NaNと他の数値を比較すると、常にfalseが返されます。これは、計算エラーを示すため、意図しない結果を招くことがあります。

2. **浮動小数点数の精度**: JavaScript（およびTypeScript）では浮動小数点数の精度に制限があるため、計算結果が期待通りにならないことがあります。特に、金額の計算などでは注意が必要です。

3. **型の推論**: 明示的に型を指定しなくても、TypeScriptは数値を自動的に「number」として扱いますが、コードの可読性を高めるために型注釈を追加することが推奨されます。

## 一文の要約
TypeScriptの「number」型は、整数や浮動小数点数を扱うための基本的なデータ型であり、型安全性を提供します。
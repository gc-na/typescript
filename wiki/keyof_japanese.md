<!--
Meta Description: # TypeScriptの「keyof」演算子：型のキーを取得する方法 ## 概要 TypeScriptの「keyof」演算子は、オブジェクト型の全てのキーを取得し、ユニオン型として返す機能を提供します。これにより、型安全性を保ちながら、オブジェクトのプロパティに対する操作を行うことが可能になります...
Meta Keywords: keyof, type, string, make, typescriptの
-->

# TypeScriptの「keyof」演算子：型のキーを取得する方法

## 概要
TypeScriptの「keyof」演算子は、オブジェクト型の全てのキーを取得し、ユニオン型として返す機能を提供します。これにより、型安全性を保ちながら、オブジェクトのプロパティに対する操作を行うことが可能になります。

## ドキュメンテーション
「keyof」演算子は、オブジェクト型からそのプロパティ名の型を抽出するために使用されます。これにより、開発者は特定のオブジェクト型のキーを使った型安全な操作を行うことができ、コードの可読性と保守性が向上します。

### 使い方
以下のように、オブジェクト型を定義し、その型に対して「keyof」を使用します。

```typescript
type Person = {
    name: string;
    age: number;
};

type PersonKeys = keyof Person; // 'name' | 'age'
```

この例では、`Person`型のプロパティ名である`name`と`age`がユニオン型として`PersonKeys`に格納されます。

## 例
以下に「keyof」の基本的な使用例を示します。

```typescript
type Car = {
    make: string;
    model: string;
    year: number;
};

type CarKeys = keyof Car; // 'make' | 'model' | 'year'

// 使用例
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
    return obj[key];
}

const myCar: Car = {
    make: 'Toyota',
    model: 'Corolla',
    year: 2021,
};

const carMake = getProperty(myCar, 'make'); // 'Toyota'
```

この例では、`getProperty`関数が`keyof`を利用して、オブジェクトの特定のプロパティを安全に取得しています。

## 説明
「keyof」を使用する際の一般的な落とし穴や注意点について説明します。

- **非オブジェクト型に対する使用**: `keyof`はオブジェクト型に対してのみ有効です。プリミティブ型（例えば、`string`や`number`）に対して使用すると、エラーが発生します。
  
- **インデックス型の注意**: `keyof`は、インデックスシグネチャを持つ型に対しても機能しますが、その場合は文字列や数値のユニオン型が返されます。

- **型安全性**: 「keyof」を使用することで、存在しないプロパティ名を指定した場合にコンパイルエラーが発生し、型安全性が向上します。

## 一文での要約
TypeScriptの「keyof」演算子は、オブジェクト型のプロパティ名をユニオン型として取得し、型安全な操作を可能にします。
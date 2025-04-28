<!--
Meta Description: # TypeScriptの「of」: 型と演算子についての徹底解説 ## 概要 TypeScriptにおける「of」は、特に`keyof`や`typeof`といった型操作に関連する重要な構文です。これらの構文は、型の安全性を保ちながら、柔軟なプログラミングを可能にします。 ## ドキュメンテーション...
Meta Keywords: keyof, typeof, name, age, typescript
-->

# TypeScriptの「of」: 型と演算子についての徹底解説

## 概要
TypeScriptにおける「of」は、特に`keyof`や`typeof`といった型操作に関連する重要な構文です。これらの構文は、型の安全性を保ちながら、柔軟なプログラミングを可能にします。

## ドキュメンテーション
### 目的
TypeScriptはJavaScriptのスーパーセットであり、型安全性を提供します。「of」は型関連の演算子として、オブジェクトや配列の型情報を扱う際に非常に有用です。

### 使用法
- **`keyof`演算子**: オブジェクトのキーのユニオン型を取得します。
- **`typeof`演算子**: 変数やオブジェクトの型を取得します。

### 詳細
- **`keyof`の使い方**:
    ```typescript
    interface Person {
        name: string;
        age: number;
    }

    type PersonKeys = keyof Person; // "name" | "age"
    ```
    上記の例では、`Person`インターフェースのキーである`name`と`age`がユニオン型として返されます。

- **`typeof`の使い方**:
    ```typescript
    const user = {
        name: "Alice",
        age: 25
    };

    type UserType = typeof user; // { name: string; age: number; }
    ```
    ここでは、`user`オブジェクトの型を取得し、`UserType`として定義しています。

## 例
### `keyof`の例
```typescript
interface Car {
    make: string;
    model: string;
    year: number;
}

type CarKeys = keyof Car; // "make" | "model" | "year"
```

### `typeof`の例
```typescript
let score = 100;
type ScoreType = typeof score; // number
```

## 説明
- `keyof`は、オブジェクトのプロパティ名を型として扱うため、誤ったプロパティ名を使った場合にコンパイルエラーを返します。
- `typeof`は、変数の型を動的に取得するため、リファクタリング時に型を手動で変更する必要がなくなります。

### 一般的な落とし穴
- `keyof`を使用する際に、オブジェクトが未定義またはnullの場合、エラーが発生する可能性があります。
- `typeof`を使って型を取得する際、複雑なオブジェクトの型を取得すると、期待通りの型が得られない場合があります。

## まとめ
TypeScriptの「of」関連の演算子は、型の安全性を確保し、より柔軟なコードを実現するための強力なツールです。
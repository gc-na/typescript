<!--
Meta Description: # TypeScriptにおける「return」文の使い方 ## 概要 TypeScriptにおける「return」文は、関数から値を返すために使用されるキーワードです。これにより、関数の実行が終了し、呼び出し元に制御が戻ります。 ## ドキュメンテーション 「return」文は、関数の戻り値を指定...
Meta Keywords: return, typescriptにおける, これにより, typescript, function
-->

# TypeScriptにおける「return」文の使い方

## 概要
TypeScriptにおける「return」文は、関数から値を返すために使用されるキーワードです。これにより、関数の実行が終了し、呼び出し元に制御が戻ります。

## ドキュメンテーション
「return」文は、関数の戻り値を指定するために使用されます。TypeScriptは静的型付けのプログラミング言語であり、関数が返す値の型を明示的に定義することができます。この機能は、コードの可読性と保守性を向上させ、バグを減少させるのに役立ちます。

### 使用方法
```typescript
function 関数名(引数1: 型1, 引数2: 型2): 戻り値の型 {
    // 処理
    return 戻り値; // 戻り値を返す
}
```

## 例
以下は、「return」文を使用した基本的な関数の例です。

```typescript
function add(a: number, b: number): number {
    return a + b; // aとbの合計を返す
}

const result = add(5, 10);
console.log(result); // 出力: 15
```

別の例として、文字列を返す関数を示します。

```typescript
function greet(name: string): string {
    return `こんにちは、${name}さん！`; // 挨拶文を返す
}

const greeting = greet("太郎");
console.log(greeting); // 出力: こんにちは、太郎さん！
```

## 説明
「return」文にはいくつかの注意点があります。以下に一般的な落とし穴や注意点を示します。

1. **戻り値がない場合**: TypeScriptでは、戻り値がない関数は`void`型を持つため、`return`文を省略することができます。ただし、戻り値を持つ関数では必ず型を指定する必要があります。

2. **複数のreturn文**: 関数内に複数の`return`文がある場合、最初に実行される`return`文が呼び出し元に返されるため、後続の`return`文は実行されません。これにより、意図しない動作を引き起こす可能性があります。

3. **非同期関数**: 非同期関数（`async`関数）では、`return`文は`Promise`オブジェクトを返します。これにより、非同期処理の結果を扱いやすくなります。

## 一文要約
TypeScriptにおける「return」文は、関数から値を返すための基本的な手段であり、関数の型を明示的に定義することで、コードの品質を向上させます。
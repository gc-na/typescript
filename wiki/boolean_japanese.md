<!--
Meta Description: # TypeScriptにおけるBoolean型の完全ガイド ## 概要 TypeScriptにおけるBoolean型は、真（true）または偽（false）の2つの値を持つデータ型です。プログラミングにおいて条件判断やフロー制御に広く使用されます。 ## ドキュメンテーション TypeScript...
Meta Keywords: true, false, boolean, log, isenabled
-->

# TypeScriptにおけるBoolean型の完全ガイド

## 概要
TypeScriptにおけるBoolean型は、真（true）または偽（false）の2つの値を持つデータ型です。プログラミングにおいて条件判断やフロー制御に広く使用されます。

## ドキュメンテーション
TypeScriptは、JavaScriptのスーパーセットとして、型安全性を強化するためにBoolean型を提供しています。Boolean型は、条件式や論理演算において重要な役割を果たします。TypeScriptでは、`boolean`というキーワードを使ってこの型を宣言します。

### 用途
- **条件分岐**: if文やswitch文などで、条件を評価する際に使用されます。
- **フラグ管理**: 特定の状態を管理するためのフラグとして利用されます。
- **論理演算**: AND（&&）、OR（||）、NOT（!）などの論理演算を行うために使用されます。

### 詳細
TypeScriptでは、Boolean型は次のように宣言します。

```typescript
let isActive: boolean = true;
```

この例では、`isActive`という変数をBoolean型として宣言し、初期値を`true`に設定しています。Boolean型の変数には、`true`または`false`のみが代入可能です。

## 例
以下にTypeScriptにおけるBoolean型の基本的な使用例を示します。

### 例1: 簡単な条件分岐
```typescript
let isLoggedIn: boolean = false;

if (isLoggedIn) {
    console.log("Welcome back!");
} else {
    console.log("Please log in.");
}
```

### 例2: フラグの使用
```typescript
let isEnabled: boolean = true;

function toggleFeature() {
    isEnabled = !isEnabled;
    console.log(`Feature enabled: ${isEnabled}`);
}
toggleFeature(); // Feature enabled: false
```

## 説明
Boolean型を使用する際の一般的な注意点や落とし穴について説明します。

- **初期化の重要性**: Boolean型の変数は明示的に初期化することが重要です。未初期化の変数は`undefined`となり、意図しない挙動を引き起こす可能性があります。
- **非Boolean値の使用**: TypeScriptでは、Boolean型に`number`や`string`などの非Boolean値を直接代入することはできません。これにより、型安全性が確保されます。
- **論理演算子の注意**: 複雑な論理演算を使用する場合、優先順位に注意が必要です。特に、真偽値の評価に影響を与える可能性があります。

## 一文要約
TypeScriptのBoolean型は、真偽値（trueまたはfalse）を扱うための型であり、条件判断やフロー制御に不可欠です。
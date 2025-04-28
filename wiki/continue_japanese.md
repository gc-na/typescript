<!--
Meta Description: # TypeScriptにおける「continue」文の使い方と特性 ## 概要 TypeScriptの「continue」文は、ループ内での処理をスキップし、次のイテレーションに移行するために使用されます。この機能は、特定の条件を満たさない場合にループの残りの処理を行わずに次の回に進むことができま...
Meta Keywords: continue, while, typescript, let, console
-->

# TypeScriptにおける「continue」文の使い方と特性

## 概要
TypeScriptの「continue」文は、ループ内での処理をスキップし、次のイテレーションに移行するために使用されます。この機能は、特定の条件を満たさない場合にループの残りの処理を行わずに次の回に進むことができます。

## ドキュメンテーション
「continue」文は、主に`for`、`while`、および`do...while`ループ内で利用されます。使用する際は、条件を設定し、その条件が真である場合に「continue」を使うことで、現在のイテレーションを終了し、次のイテレーションに移行します。

### 使用法
```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 偶数の場合は次のイテレーションに移る
    }
    console.log(i); // 奇数のみが出力される
}
```

## 例
以下は「continue」文の基本的な使用例です。

### 例1: 偶数をスキップする
```typescript
for (let i = 0; i < 10; i++) {
    if (i % 2 === 0) {
        continue; // 偶数をスキップ
    }
    console.log(i); // 1, 3, 5, 7, 9が出力される
}
```

### 例2: 配列の特定の値をスキップする
```typescript
const numbers = [1, 2, 3, 4, 5];
for (let num of numbers) {
    if (num === 3) {
        continue; // 3をスキップ
    }
    console.log(num); // 1, 2, 4, 5が出力される
}
```

## 説明
「continue」文を使用する際には、以下の点に注意が必要です。

- **ループの種類:** 「continue」は`for`、`while`、`do...while`ループでのみ機能します。`forEach`や`map`などの配列メソッドには適用できません。
- **無限ループの可能性:** 条件を間違えると無限ループに陥ることがあります。特に、ループ内で条件が変更されない場合は注意が必要です。
- **可読性:** 過度の「continue」使用はコードの可読性を低下させる可能性があります。適切な条件文を用いることで、より明確なロジックを保つことが大切です。

## 一文でのまとめ
TypeScriptの「continue」文は、ループ内で特定の条件を満たす場合に処理をスキップし、次のイテレーションに進むために使用されます。
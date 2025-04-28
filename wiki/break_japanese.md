<!--
Meta Description: # TypeScriptにおける「break」文の完全ガイド ## 概要 TypeScriptの「break」文は、ループやswitch文の実行を中断し、次のコードに制御を移すために使用される重要な制御フロー機能です。この機能を理解することで、より効率的にプログラムを制御できます。 ## ドキュメン...
Meta Keywords: break, console, log, value, while
-->

# TypeScriptにおける「break」文の完全ガイド

## 概要
TypeScriptの「break」文は、ループやswitch文の実行を中断し、次のコードに制御を移すために使用される重要な制御フロー機能です。この機能を理解することで、より効率的にプログラムを制御できます。

## ドキュメント
### 目的
「break」文は主に、for、while、do...while ループや switch 文からの早期脱出を可能にします。これにより、特定の条件が満たされたときにループを抜け出したり、switch ケースを終了することができます。

### 使用法
「break」文は以下のように使用します：

```typescript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break; // iが5に達したらループを終了
    }
    console.log(i);
}
```

この例では、iが5になるとループが終了し、0から4までの数字が表示されます。

### 詳細
- **適用範囲**: 「break」文は、ループ（for、while、do...while）やswitch文内で使用できます。
- **ネストされたループ**: 複数のネストされたループがある場合、「break」を使うと、最も内側のループのみが終了します。外側のループを終了するには、ラベルを使用する必要があります。

```typescript
outerLoop: for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 3; j++) {
        if (j === 1) {
            break outerLoop; // outerLoopを終了
        }
        console.log(`i: ${i}, j: ${j}`);
    }
}
```

## 例
### 基本的な使用例
1. **ループ内での使用**:
```typescript
for (let i = 0; i < 10; i++) {
    if (i === 3) {
        break; // 3でループを終了
    }
    console.log(i); // 0, 1, 2
}
```

2. **switch文内での使用**:
```typescript
const value = 2;
switch (value) {
    case 1:
        console.log("Value is 1");
        break; // この行でswitchを終了
    case 2:
        console.log("Value is 2");
        break;
    default:
        console.log("Value is unknown");
}
```

## 説明
- **一般的な落とし穴**: 「break」を意図的に使う場合、条件を正しく設定しないと、予期せぬ場所でループが終了してしまうことがあります。特に、ネストされたループでは、どのループが終了するのかを混乱することがあります。
- **利用シナリオ**: 大量のデータを処理する際に、特定の条件が満たされた場合に効率よく処理を中断するために使用します。

## 一文の要約
TypeScriptにおける「break」文は、ループやswitch文からの早期脱出を可能にする制御フローの重要な要素です。
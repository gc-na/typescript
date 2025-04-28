<!--
Meta Description: # TypeScriptにおける「catch」: エラーハンドリングの基本 ## 概要 TypeScriptにおける「catch」は、Promiseやtry-catch構文を使用して発生したエラーを捕捉し、適切に処理するための機能です。この機能を用いることで、プログラムのクラッシュを防ぎ、エラーハン...
Meta Keywords: error, catch, new, console, try
-->

# TypeScriptにおける「catch」: エラーハンドリングの基本

## 概要
TypeScriptにおける「catch」は、Promiseやtry-catch構文を使用して発生したエラーを捕捉し、適切に処理するための機能です。この機能を用いることで、プログラムのクラッシュを防ぎ、エラーハンドリングのロジックを簡潔に記述できます。

## ドキュメント
### 目的
「catch」は、非同期処理や同期処理で発生するエラーを処理するために使用されます。エラーが発生した場合、プログラムの流れを制御し、適切な処理を行うことができます。

### 使用法
1. **Promiseのエラーハンドリング**  
   Promiseチェーンの最後に「catch」を追加することで、前のすべてのthenブロックで発生したエラーを捕捉できます。

   ```typescript
   const promise = new Promise((resolve, reject) => {
       // 処理
       reject(new Error("エラーが発生しました"));
   });

   promise
       .then(result => {
           console.log(result);
       })
       .catch(error => {
           console.error("エラー:", error);
       });
   ```

2. **try-catch構文**  
   同期処理においてエラーハンドリングを行う場合、try-catch構文を使用します。

   ```typescript
   try {
       // 処理
       throw new Error("エラーが発生しました");
   } catch (error) {
       console.error("エラー:", error);
   }
   ```

## 例
### Promiseでの例
```typescript
async function fetchData() {
   return new Promise((resolve, reject) => {
       setTimeout(() => {
           reject(new Error("データの取得に失敗しました"));
       }, 1000);
   });
}

fetchData()
   .then(data => console.log(data))
   .catch(error => console.error("エラー:", error.message));
```

### try-catchでの例
```typescript
function riskyFunction() {
   throw new Error("リスキーな処理でエラーが発生");
}

try {
   riskyFunction();
} catch (error) {
   console.error("エラー:", error.message);
}
```

## 説明
「catch」を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **Promiseチェーンの位置**: `catch`はPromiseチェーンの最後に置かなければ、エラーを正しく捕捉できない場合があります。前のthenブロックで発生したエラーは、後のcatchブロックで処理されます。
  
- **エラーオブジェクトの型**: TypeScriptでは、エラーオブジェクトは通常`any`型として扱われます。エラーオブジェクトの型を明示的に指定することで、より安全なコードを書くことができます。

- **非同期関数内のエラー**: 非同期関数の中でエラーが発生した場合、通常のtry-catchでは捕捉できません。この場合は、async/awaitを使用して、try-catchを使うことが推奨されます。

## 一文要約
TypeScriptにおける「catch」は、Promiseやtry-catch構文を使用して発生したエラーを捕捉し、適切に処理するための機能です。
<!--
Meta Description: # TypeScript 中的 "unique" 類型 ## 概述 在 TypeScript 中，"unique" 類型是一種用於創建唯一識別符的工具，這使得開發者可以定義不會與其他類型重複的值。這對於需要嚴格類型安全的情況特別有用，例如在大型應用程序中管理狀態或識別物件。 ## 文件說明 "uni...
Meta Keywords: unique, uniqueid, typescript, createuniqueid, string
-->

# TypeScript 中的 "unique" 類型

## 概述
在 TypeScript 中，"unique" 類型是一種用於創建唯一識別符的工具，這使得開發者可以定義不會與其他類型重複的值。這對於需要嚴格類型安全的情況特別有用，例如在大型應用程序中管理狀態或識別物件。

## 文件說明
"unique" 類型在 TypeScript 中並不是一個內建的關鍵字，但可以通過使用字面量類型和交叉類型來實現。這種技術允許開發者定義一種獨特的類型，以防止相同的類型被錯誤地重用。

### 目的
- 確保每個值的唯一性，避免類型衝突。
- 增加代碼的可讀性和可維護性。

### 使用方法
要創建一個 "unique" 類型，可以使用字面量類型結合交叉類型，示例如下：

```typescript
type UniqueString = string & { readonly unique: unique symbol };
```

這樣的定義使得 `UniqueString` 成為一個唯一的字符串類型，並且不能與普通的字符串混淆。

## 範例
以下是如何使用 "unique" 類型的基本範例：

```typescript
type UniqueID = string & { readonly unique: unique symbol };

function createUniqueID(): UniqueID {
    return "ID-" + Math.random().toString(36).substr(2, 9) as UniqueID;
}

const id1: UniqueID = createUniqueID();
const id2: UniqueID = createUniqueID();

console.log(id1); // 例如: ID-abc123xyz
console.log(id2); // 例如: ID-def456uvw
```

在這個範例中，`createUniqueID` 函數生成了獨特的識別符，並使用 `UniqueID` 類型來確保這些值的唯一性。

## 解釋
使用 "unique" 類型時，開發者需要注意以下幾點：
- **類型不匹配**：由於 `UniqueID` 是一個獨特的類型，將其賦值給普通的字符串會導致編譯錯誤。
- **隱式轉換**：雖然可以將 `UniqueID` 轉換為 `string`，但應避免這樣做，因為這會破壞類型的唯一性。

## 總結
"unique" 類型在 TypeScript 中提供了一種定義唯一值的機制，增強了代碼的安全性和可讀性。
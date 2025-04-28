<!--
Meta Description: # TypeScript: Der "never" Typ – Bedeutung und Verwendung ## Synopsis Der `never` Typ in TypeScript wird verwendet, um Werte darzustellen, die niemals ...
Meta Keywords: never, die, typ, ist, typescript
-->

# TypeScript: Der "never" Typ – Bedeutung und Verwendung

## Synopsis
Der `never` Typ in TypeScript wird verwendet, um Werte darzustellen, die niemals auftreten können. Er ist besonders nützlich in Funktionen, die nie erfolgreich zurückkehren, wie bei Ausnahmen oder unendlichen Schleifen.

## Dokumentation
### Zweck
Der `never` Typ ist ein spezieller Typ in TypeScript, der angibt, dass eine Funktion oder ein Ausdruck niemals einen Wert zurückgeben wird. Dies ist häufig der Fall bei Funktionen, die eine Ausnahme auslösen oder eine unendliche Schleife enthalten. Die Verwendung von `never` hilft Entwicklern, sicherzustellen, dass bestimmte Codepfade nicht erreicht werden können, wodurch die Typensicherheit erhöht wird.

### Verwendung
Um den `never` Typ zu deklarieren, verwenden Sie einfach das Schlüsselwort `never`. Der `never` Typ kann in verschiedenen Szenarien eingesetzt werden, darunter:

1. **Ausnahmebehandlung**: Funktionen, die eine Ausnahme werfen.
2. **Unendliche Schleifen**: Funktionen, die nie zu einem Rückgabewert gelangen.
3. **Typen, die nicht möglich sind**: Typen, die niemals zugewiesen werden können.

### Details
Im TypeScript-Ökosystem ist `never` ein Untertyp von allen anderen Typen und wird häufig in Kombination mit dem `void` Typ verwendet. Wenn eine Funktion als `never` deklariert ist, bedeutet dies, dass sie nie einen Wert zurückgibt, was zur Erkennung von logischen Fehlern führen kann.

## Beispiele
Hier sind einige grundlegende Beispiele, die die Verwendung von `never` demonstrieren:

### Beispiel 1: Ausnahme werfen
```typescript
function throwError(message: string): never {
    throw new Error(message);
}
```

### Beispiel 2: Unendliche Schleife
```typescript
function infiniteLoop(): never {
    while (true) {
        console.log("Ich laufe für immer!");
    }
}
```

### Beispiel 3: Typen, die nicht existieren
```typescript
function checkValue(value: string | number): never {
    if (typeof value === "string") {
        console.log("Es ist ein String.");
    } else if (typeof value === "number") {
        console.log("Es ist eine Zahl.");
    } else {
        // Dieser Fall sollte nie eintreten
        const _exhaustiveCheck: never = value; // Fehler, wenn ein neuer Typ hinzugefügt wird
        throw new Error("Unbekannter Typ!");
    }
}
```

## Erklärung
Ein häufiger Fallstrick beim Arbeiten mit dem `never` Typ ist, dass er nicht mit anderen Typen kombiniert werden kann, da er nicht zugewiesen werden kann. Wenn Sie beispielsweise versuchen, einen Wert vom Typ `never` einer Variablen zuzuweisen, wird ein Fehler generiert. Dies kann zu Verwirrung führen, insbesondere für Entwickler, die neu in TypeScript sind.

Ein weiteres wichtiges Detail ist, dass der `never` Typ nicht dasselbe wie `void` ist. Während `void` angibt, dass eine Funktion keinen Wert zurückgibt, bedeutet `never`, dass die Funktion niemals zurückkehrt. Dies ist ein wichtiger Unterschied in der Typisierung.

## Eine Zeilen Zusammenfassung
Der `never` Typ in TypeScript wird verwendet, um Werte darzustellen, die niemals auftreten können, und ist besonders nützlich in Funktionen, die eine Ausnahme werfen oder unendliche Schleifen enthalten.
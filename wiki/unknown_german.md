<!--
Meta Description: # TypeScript "unknown": Typensicherheit und Flexibilität kombinieren ## Synopsis Der Typ `unknown` in TypeScript ist ein sicherer Typ, der verwendet w...
Meta Keywords: unknown, typ, ist, sie, value
-->

# TypeScript "unknown": Typensicherheit und Flexibilität kombinieren

## Synopsis
Der Typ `unknown` in TypeScript ist ein sicherer Typ, der verwendet wird, um Werte zu repräsentieren, deren Typ nicht bekannt ist. Er ähnelt dem Typ `any`, bietet jedoch eine höhere Typensicherheit, da Operationen auf `unknown`-Werten explizit typisiert werden müssen.

## Documentation
Der Typ `unknown` wurde in TypeScript 3.0 eingeführt und dient dazu, eine striktere Typprüfung zu ermöglichen. Während der Typ `any` es erlaubt, mit Werten beliebiger Art zu arbeiten, ohne Typfehler zu verursachen, fordert `unknown` den Entwickler auf, den Typ des Wertes zu überprüfen, bevor er darauf zugreift.

### Zweck
`unknown` ist nützlich in Situationen, in denen Sie mit externen Daten oder API-Antworten arbeiten, deren Struktur nicht sicher ist. Dieser Typ schützt vor unerwarteten Fehlern, da Sie sicherstellen müssen, dass Sie den Wert vor seiner Verwendung überprüfen.

### Nutzung
Um den Typ `unknown` zu verwenden, deklarieren Sie eine Variable oder einen Parameter mit diesem Typ. Hier ist ein einfaches Beispiel:

```typescript
let value: unknown;

value = 42;          // gültig
value = "Hallo";    // gültig
value = true;       // gültig
```

Bevor Sie mit `value` arbeiten, müssen Sie sicherstellen, dass Sie den Typ überprüfen:

```typescript
if (typeof value === "string") {
    console.log(value.toUpperCase()); // gültig, da wir sicher sind, dass es ein string ist
}
```

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung des Typs `unknown`:

### Beispiel 1: Typüberprüfung
```typescript
function processValue(value: unknown) {
    if (typeof value === "number") {
        console.log(value * 2); // gültig, da wir sicher sind, dass es ein number ist
    } else {
        console.log("Kein gültiger Wert");
    }
}

processValue(10); // Ausgabe: 20
processValue("Text"); // Ausgabe: Kein gültiger Wert
```

### Beispiel 2: Verwendung in Funktionen
```typescript
function handleData(data: unknown) {
    if (Array.isArray(data)) {
        console.log(data.length); // Zugriff auf die Länge eines Arrays
    } else {
        console.log("Das gegebene Datenformat ist nicht ein Array.");
    }
}

handleData([1, 2, 3]); // Ausgabe: 3
handleData("Text"); // Ausgabe: Das gegebene Datenformat ist nicht ein Array.
```

## Explanation
Ein häufiger Fehler beim Arbeiten mit `unknown` ist die Annahme, dass Sie auf die Eigenschaften eines Wertes zugreifen können, ohne vorher eine Typüberprüfung durchzuführen. Dies kann zu Kompilierungsfehlern führen, da TypeScript sicherstellt, dass vor der Verwendung des Wertes eine Validierung erfolgt.

Ein weiterer Punkt ist, dass `unknown` nicht direkt in Funktionen oder Methoden verwendet werden kann, die einen spezifischen Typ erwarten. Sie müssen den Typ zuerst überprüfen oder umwandeln.

Zusätzlich sollten Sie beachten, dass der Typ `unknown` nicht in der Typausdrücken von generischen Typen verwendet werden kann, außer wenn er in einer Typüberprüfung verarbeitet wird.

## One Line Summary
Der Typ `unknown` in TypeScript bietet eine sichere Möglichkeit, mit unbekannten Werten umzugehen und erfordert explizite Typüberprüfungen vor der Verwendung.
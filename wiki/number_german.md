<!--
Meta Description: # Die Zahl (number) in TypeScript: Ein umfassender Leitfaden ## Synopsis In TypeScript ist der Datentyp `number` entscheidend für die Darstellung und ...
Meta Keywords: number, typescript, die, und, der
-->

# Die Zahl (number) in TypeScript: Ein umfassender Leitfaden

## Synopsis
In TypeScript ist der Datentyp `number` entscheidend für die Darstellung und Manipulation von numerischen Werten. Er unterstützt sowohl Ganzzahlen als auch Fließkommazahlen und bietet eine Vielzahl von mathematischen Operationen.

## Dokumentation
Der `number`-Typ in TypeScript ist ein primitiver Datentyp, der alle numerischen Werte repräsentiert. Er basiert auf dem IEEE 754 Standard für doppelt präzise Fließkommazahlen und umfasst:

- **Ganzzahlen**: Positive und negative ganze Zahlen, z.B. `42`, `-7`.
- **Fließkommazahlen**: Dezimalzahlen, z.B. `3.14`, `-0.001`.
- **Sonderwerte**: `Infinity`, `-Infinity` und `NaN` (Not a Number).

### Verwendung
Um eine Variable vom Typ `number` zu deklarieren, können Sie die folgende Syntax verwenden:

```typescript
let alter: number = 30;
let pi: number = 3.14;
```

TypeScript erkennt automatisch den Typ, wenn Sie eine Zahl zuweisen. Eine Typanmerkung ist jedoch nützlich, um die Lesbarkeit und Wartbarkeit des Codes zu verbessern.

## Beispiele
Hier sind einige einfache Anwendungsbeispiele für den `number`-Typ:

```typescript
// Ganzzahl
let ganzzahl: number = 10;

// Fließkommazahl
let dezimalzahl: number = 5.75;

// Mathematische Operationen
let summe: number = ganzzahl + dezimalzahl; // 15.75
let differenz: number = ganzzahl - 2; // 8
```

### Sonderwerte
```typescript
let unendlich: number = Infinity;
let nichtEineZahl: number = NaN;

console.log(unendlich); // Gibt 'Infinity' aus
console.log(isNaN(nichtEineZahl)); // Gibt 'true' aus
```

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit dem `number`-Typ in TypeScript ist die Verwendung von Fließkommazahlen, insbesondere bei Berechnungen, die Präzision erfordern. Zum Beispiel kann das Ergebnis von `0.1 + 0.2` nicht exakt `0.3` sein, was zu unerwarteten Ergebnissen führen kann. Hier einige wichtige Hinweise:

- **Präzision**: Seien Sie vorsichtig bei der Verwendung von Fließkommazahlen in finanziellen Berechnungen. Verwenden Sie stattdessen ganzzahlige Werte oder spezielle Bibliotheken zur Handhabung von Geldbeträgen.
- **NaN**: Der Wert `NaN` ist ein spezieller Fall in JavaScript und TypeScript, der auftritt, wenn eine mathematische Operation nicht definiert ist. Es ist wichtig, dies zu überprüfen, um unerwartete Fehler zu vermeiden.
- **Typensicherheit**: TypeScript bietet Typensicherheit, die dabei hilft, Fehler zu vermeiden, die bei der Arbeit mit Zahlen auftreten können. Nutzen Sie diese Funktionalität, um sicherzustellen, dass Sie mit den richtigen Datentypen arbeiten.

## Ein-Satz-Zusammenfassung
Der `number`-Typ in TypeScript ermöglicht die flexible Handhabung von Zahlen, einschließlich Ganzzahlen und Fließkommazahlen, und unterstützt eine Vielzahl von mathematischen Operationen.
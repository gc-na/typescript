<!--
Meta Description: # TypeScript `infer`: Typinferenz für verbesserte Typensicherheit ## Synopsis In TypeScript ermöglicht das Schlüsselwort `infer` die Typinferenz inner...
Meta Keywords: infer, type, typen, typ, ist
-->

# TypeScript `infer`: Typinferenz für verbesserte Typensicherheit

## Synopsis
In TypeScript ermöglicht das Schlüsselwort `infer` die Typinferenz innerhalb von bedingten Typen, um den Typ einer Variable basierend auf einem gegebenen Typ zu bestimmen. Dies verbessert die Typensicherheit und ermöglicht eine dynamische Typbestimmung.

## Documentation
Das Schlüsselwort `infer` wird in TypeScript verwendet, um Typen während der Definition von bedingten Typen zu extrahieren. Es erlaubt Entwicklern, innerhalb von Typen zu definieren, wie sich Typen verhalten, ohne diese explizit angeben zu müssen. `infer` wird häufig in Kombination mit dem `extends`-Schlüsselwort verwendet, um eine Bedingung zu prüfen und den Typ basierend auf dieser Bedingung abzuleiten.

### Zweck
- **Typinferenz**: Erleichtert die Ableitung von Typen aus anderen Typen.
- **Typensicherheit**: Verbessert die Sicherheit des Codes, indem es Typfehler zur Compile-Zeit erkennt.

### Verwendung
Um `infer` zu verwenden, definieren Sie zuerst einen bedingten Typ und verwenden das `infer`-Schlüsselwort, um einen Typ innerhalb der Bedingung zu deklarieren. Hier ist die allgemeine Syntax:

```typescript
type BedingterTyp<T> = T extends SomeType<infer U> ? U : FallbackType;
```

In diesem Beispiel wird `U` typisiert, basierend auf dem Typ `T`, wenn `T` den Typ `SomeType` erweitert.

## Examples
### Beispiel 1: Einfache Typinferenz
```typescript
type ElementTyp<T> = T extends (infer U)[] ? U : never;

type Zahl = ElementTyp<number[]>; // Zahl ist number
type Zeichenkette = ElementTyp<string[]>; // Zeichenkette ist string
```

### Beispiel 2: Verwendung mit Funktionen
```typescript
type Rückgabewert<T> = T extends (...args: any[]) => infer R ? R : never;

type Funktion = (input: number) => string;
type Rückgabe = Rückgabewert<Funktion>; // Rückgabe ist string
```

### Beispiel 3: Fallback-Typ
```typescript
type WertTyp<T> = T extends number ? "Zahl" : "Nicht-Zahl";

type Test1 = WertTyp<number>; // Test1 ist "Zahl"
type Test2 = WertTyp<string>; // Test2 ist "Nicht-Zahl"
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `infer` ist, dass es nur innerhalb von bedingten Typen verwendet werden kann. Wenn `infer` außerhalb eines solchen Kontexts verwendet wird, führt dies zu einem Kompilierungsfehler. Außerdem ist es wichtig, sorgfältig zu prüfen, ob der Typ tatsächlich den erwarteten Bedingungen entspricht, da falsche Annahmen zu unerwarteten Ergebnissen führen können.

Ein weiterer Punkt, den Entwickler beachten sollten, ist die Lesbarkeit des Codes. Übermäßiger Einsatz von `infer` kann den Code komplex und schwer verständlich machen. Es sollte daher sparsam verwendet werden, um die Lesbarkeit und Wartbarkeit des Codes nicht zu beeinträchtigen.

## One Line Summary
Das `infer`-Schlüsselwort in TypeScript ermöglicht die Typinferenz innerhalb bedingter Typen zur Verbesserung der Typensicherheit und dynamischen Typbestimmung.
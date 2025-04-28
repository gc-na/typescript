<!--
Meta Description: # Rückgabewert in TypeScript: Verwendung und Beispiele ## Synopsis In TypeScript wird das Schlüsselwort `return` verwendet, um einen Wert aus einer Fu...
Meta Keywords: typescript, funktion, die, return, ist
-->

# Rückgabewert in TypeScript: Verwendung und Beispiele

## Synopsis
In TypeScript wird das Schlüsselwort `return` verwendet, um einen Wert aus einer Funktion zurückzugeben. Es spielt eine zentrale Rolle in der Steuerung des Programmflusses und ermöglicht die Übergabe von Daten von einer Funktion an ihren Aufrufer.

## Dokumentation
Das `return`-Schlüsselwort in TypeScript ist ein essenzieller Bestandteil der Funktionsdefinition. Es beendet die Ausführung einer Funktion und gibt den angegebenen Wert zurück. Wenn keine Rückgabe definiert ist, gibt die Funktion `undefined` zurück. Die Verwendung von `return` ist besonders wichtig, um das Ergebnis von Berechnungen oder Operationen innerhalb einer Funktion an den Aufrufer zurückzugeben.

### Verwendung
Um das `return`-Schlüsselwort in TypeScript zu verwenden, muss es innerhalb einer Funktion platziert werden. Der Rückgabewert kann jeder Datentyp sein, einschließlich primitiver Typen wie `number`, `string`, `boolean`, oder komplexer Typen wie Objekte und Arrays.

### Details
- Die Rückgabetypen einer Funktion können durch TypeScript-Typannotationen definiert werden.
- Eine Funktion, die keinen Wert zurückgibt, kann den Rückgabetyp `void` haben.
- Mehrere Rückgabewerte können durch die Verwendung von Tupeln oder Objekten ermöglicht werden.

## Beispiele

### Einfaches Beispiel
```typescript
function addiere(a: number, b: number): number {
    return a + b;
}

const summe = addiere(3, 5);
console.log(summe); // Ausgabe: 8
```

### Beispiel mit void
```typescript
function begruessung(name: string): void {
    console.log(`Hallo, ${name}!`);
}

begruessung("Max"); // Ausgabe: Hallo, Max!
```

### Rückgabe eines Objekts
```typescript
function erstellePerson(name: string, alter: number) {
    return { name: name, alter: alter };
}

const person = erstellePerson("Anna", 25);
console.log(person); // Ausgabe: { name: "Anna", alter: 25 }
```

## Erklärung
Ein häufiges Missverständnis ist, dass eine Funktion immer einen Wert zurückgeben muss. In TypeScript ist dies nicht der Fall; Funktionen können auch ohne Rückgabewert definiert werden (Rückgabetyp `void`). Es ist wichtig, sicherzustellen, dass der Rückgabetyp der Funktion mit dem tatsächlich zurückgegebenen Wert übereinstimmt, da TypeScript dies zur Typprüfung verwendet. Ein weiterer häufiger Fehler ist die Verwendung von `return` außerhalb einer Funktion, was zu einem Syntaxfehler führt.

## Ein Satz Zusammenfassung
Das `return`-Schlüsselwort in TypeScript ermöglicht es, Werte aus Funktionen zurückzugeben und ist entscheidend für die Steuerung des Programmflusses.
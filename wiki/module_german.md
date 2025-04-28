<!--
Meta Description: # TypeScript Module: Eine umfassende Anleitung zu Modulen in TypeScript ## Synopsis In TypeScript sind Module eine wichtige Funktionalität, die es Ent...
Meta Keywords: die, modul, typescript, export, module
-->

# TypeScript Module: Eine umfassende Anleitung zu Modulen in TypeScript

## Synopsis
In TypeScript sind Module eine wichtige Funktionalität, die es Entwicklern ermöglicht, Code in separate, wiederverwendbare Einheiten zu organisieren und zu strukturieren. Sie fördern die Modularität und helfen, Namenskollisionen zu vermeiden.

## Dokumentation
Module in TypeScript sind Dateien, die Code enthalten, der in einer separaten Namespace-Umgebung ausgeführt wird. Jedes Modul hat seinen eigenen Gültigkeitsbereich, was bedeutet, dass Variablen und Funktionen, die innerhalb eines Moduls definiert sind, nicht automatisch in anderen Modulen verfügbar sind, es sei denn, sie werden explizit exportiert.

### Zweck
Der Hauptzweck von Modulen ist es, den Code zu organisieren, die Wiederverwendbarkeit zu erhöhen und die Wartbarkeit zu verbessern. Sie ermöglichen es, große Anwendungen in kleinere, handhabbare Teile zu zerlegen.

### Verwendung
Um ein Modul zu erstellen, wird einfach eine TypeScript-Datei (.ts) erstellt. Um einen Teil eines Moduls für andere Module verfügbar zu machen, wird das Schlüsselwort `export` verwendet. Um Funktionen oder Variablen aus einem Modul zu importieren, wird das Schlüsselwort `import` verwendet.

### Details
- **Export**: Mit `export` können Sie Variablen, Funktionen oder Klassen aus einem Modul verfügbar machen.
- **Import**: Mit `import` können Sie Funktionen, Variablen oder Klassen aus anderen Modulen verwenden.
- **Standardexport**: Ein Modul kann auch einen Standardexport haben, der ohne geschweifte Klammern importiert werden kann.

## Beispiele
### Beispiel 1: Einfache Module
**Modul `math.ts`:**
```typescript
export function add(a: number, b: number): number {
    return a + b;
}
```

**Modul `app.ts`:**
```typescript
import { add } from './math';

console.log(add(2, 3)); // Ausgabe: 5
```

### Beispiel 2: Standardexport
**Modul `greeter.ts`:**
```typescript
export default function greet(name: string): string {
    return `Hallo, ${name}!`;
}
```

**Modul `app.ts`:**
```typescript
import greet from './greeter';

console.log(greet('Welt')); // Ausgabe: Hallo, Welt!
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit Modulen ist das Verständnis von relativen und absoluten Importpfaden. Achten Sie darauf, die richtigen Pfade zu verwenden, um Importfehler zu vermeiden. Auch die Verwendung von `export default` kann verwirrend sein, insbesondere wenn mehrere Exporte in einem Modul vorhanden sind. 

Ein weiteres häufiges Missverständnis ist, dass alles in einem Modul automatisch exportiert wird; dies ist nicht der Fall. Nur die mit `export` oder `export default` gekennzeichneten Entitäten sind außerhalb des Moduls zugänglich.

## Ein-Satz-Zusammenfassung
TypeScript-Module ermöglichen die Organisation von Code in separate, wiederverwendbare Einheiten, wodurch die Modularität und Wartbarkeit verbessert werden.
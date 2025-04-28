<!--
Meta Description: # Import in TypeScript: Eine umfassende Anleitung ## Synopsis Der `import`-Befehl in TypeScript ermöglicht das Einfügen von Modulen und deren Inhalten...
Meta Keywords: typescript, die, import, und, von
-->

# Import in TypeScript: Eine umfassende Anleitung

## Synopsis
Der `import`-Befehl in TypeScript ermöglicht das Einfügen von Modulen und deren Inhalten in andere Dateien, was die Modularität und Wiederverwendbarkeit von Code fördert.

## Dokumentation
Der `import`-Befehl ist ein grundlegendes Feature in TypeScript (und auch in JavaScript), das es Entwicklern ermöglicht, Funktionen, Klassen, Interfaces und Variablen aus einem Modul in ein anderes zu integrieren. Dies unterstützt die Trennung von Code in logische Einheiten und verbessert die Wartbarkeit.

### Zweck
- **Modularität**: Ermöglicht es, Code in separate, wiederverwendbare Module zu organisieren.
- **Wiederverwendbarkeit**: Funktionen oder Klassen, die in einem Modul definiert sind, können in verschiedenen Teilen der Anwendung verwendet werden.
- **Kollaboration**: Erleichtert die Zusammenarbeit im Team, da verschiedene Entwickler an unterschiedlichen Modulen arbeiten können.

### Verwendung
Der `import`-Befehl wird in der Regel am Anfang einer TypeScript-Datei platziert und hat folgende Syntax:

```typescript
import { Name } from 'pfad/zum/modul';
```

Alternativ kann auch die Standard-Import-Syntax verwendet werden:

```typescript
import Name from 'pfad/zum/modul';
```

### Import von allem
Um alle Exporte aus einem Modul zu importieren, kann die folgende Syntax verwendet werden:

```typescript
import * as Name from 'pfad/zum/modul';
```

## Beispiele

### Beispiel 1: Benannte Importe
Angenommen, wir haben eine Datei `math.ts` mit folgendem Inhalt:

```typescript
// math.ts
export const add = (a: number, b: number) => a + b;
export const subtract = (a: number, b: number) => a - b;
```

Um die Funktionen `add` und `subtract` in einer anderen Datei zu verwenden, schreiben wir:

```typescript
// main.ts
import { add, subtract } from './math';

console.log(add(5, 3)); // Ausgabe: 8
console.log(subtract(5, 3)); // Ausgabe: 2
```

### Beispiel 2: Standard-Import
In einer Datei `logger.ts`:

```typescript
// logger.ts
const log = (message: string) => console.log(message);
export default log;
```

Verwendung in einer anderen Datei:

```typescript
// main.ts
import log from './logger';

log('Hello, TypeScript!'); // Ausgabe: Hello, TypeScript!
```

### Beispiel 3: Import von allem
In einer Datei `utils.ts`:

```typescript
// utils.ts
export const formatDate = (date: Date) => date.toISOString();
export const parseDate = (dateString: string) => new Date(dateString);
```

Verwendung in einer anderen Datei:

```typescript
// main.ts
import * as Utils from './utils';

console.log(Utils.formatDate(new Date())); // Ausgabe: ISO-Datum
```

## Erklärung
Ein häufiger Stolperstein beim Importieren in TypeScript ist die korrekte Angabe des Dateipfads. Wenn der Pfad nicht korrekt ist oder die Datei nicht gefunden wird, führt dies zu einem Fehler. 

Ein weiterer Punkt zu beachten ist, dass TypeScript die Modulauflösung unterstützt, was bedeutet, dass Entwickler die Art und Weise, wie Module aufgelöst werden, anpassen können, z.B. durch die Verwendung von `paths` in der `tsconfig.json`.

Zusätzlich ist es wichtig, sich darüber im Klaren zu sein, dass die Verwendung von `import` in TypeScript die Verwendung von ES6-Modulen (`import/export`) erfordert. Bei Verwendung von CommonJS-Modulen kann es notwendig sein, die `require`-Syntax zu verwenden, was jedoch nicht die empfohlene Praxis ist.

## Ein Satz Zusammenfassung
Der `import`-Befehl in TypeScript ermöglicht es, Module und deren Inhalte effizient in anderen Dateien zu verwenden und fördert somit die Modularität und Wiederverwendbarkeit von Code.
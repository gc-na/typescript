<!--
Meta Description: # Export in TypeScript: Alles, was Sie wissen müssen ## Synopsis Das `export`-Schlüsselwort in TypeScript ermöglicht es Entwicklern, Variablen, Funkti...
Meta Keywords: export, typescript, und, die, das
-->

# Export in TypeScript: Alles, was Sie wissen müssen

## Synopsis
Das `export`-Schlüsselwort in TypeScript ermöglicht es Entwicklern, Variablen, Funktionen, Klassen und Interfaces aus einem Modul zu exportieren, sodass diese in anderen Modulen importiert und verwendet werden können.

## Dokumentation
Das `export`-Schlüsselwort ist ein zentraler Bestandteil des Modul-Systems in TypeScript. Es erlaubt die Strukturierung von Code in wiederverwendbare und organisierte Einheiten. Durch das Exportieren von Elementen können diese in anderen Dateien oder Modulen importiert und genutzt werden, was die Modularität und Lesbarkeit des Codes verbessert.

### Zweck
Der Hauptzweck des `export`-Schlüsselworts besteht darin, die Sichtbarkeit von Modulinhalten zu steuern. Nur die Elemente, die mit `export` markiert sind, können außerhalb des Moduls verwendet werden.

### Verwendung
Es gibt zwei Hauptarten von Exports in TypeScript:

1. **Benannter Export**: Mehrere Elemente können aus einem Modul exportiert werden.
   ```typescript
   // myModule.ts
   export const myVariable = 42;
   export function myFunction() { return 'Hello'; }
   ```

2. **Standardexport**: Es kann nur ein Standardexport pro Modul geben, der den Hauptinhalt des Moduls darstellt.
   ```typescript
   // myModule.ts
   export default class MyClass {
       constructor() {}
   }
   ```

### Importieren von exportierten Elementen
Um die exportierten Elemente in einer anderen Datei zu verwenden, verwenden Sie das `import`-Schlüsselwort:
```typescript
// main.ts
import { myVariable, myFunction } from './myModule';
import MyClass from './myModule';
```

## Beispiele
### Benannte Exporte
```typescript
// utils.ts
export function add(a: number, b: number): number {
    return a + b;
}

export const PI = 3.14;
```
```typescript
// main.ts
import { add, PI } from './utils';

console.log(add(2, 3)); // 5
console.log(PI); // 3.14
```

### Standardexport
```typescript
// Animal.ts
export default class Animal {
    constructor(public name: string) {}
}
```
```typescript
// main.ts
import Animal from './Animal';

const myAnimal = new Animal('Dog');
console.log(myAnimal.name); // Dog
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit `export` sind Namenskonflikte. Wenn zwei Module Elemente mit denselben Namen exportieren, kann dies beim Importieren zu Verwirrungen führen. In solchen Fällen ist es ratsam, Aliase zu verwenden:
```typescript
import { myFunction as anotherFunction } from './myModule';
```

Ein weiterer Punkt ist, dass Standardexporte nur einmal pro Modul verwendet werden können, während benannte Exporte beliebig oft genutzt werden können. Es ist wichtig, die richtige Exportart entsprechend der Modulstruktur und den Anforderungen des Projekts auszuwählen.

## Ein-Satz-Zusammenfassung
Das `export`-Schlüsselwort in TypeScript ermöglicht das Exportieren von Modulinhalten, um deren Wiederverwendbarkeit und Modularität zu fördern.
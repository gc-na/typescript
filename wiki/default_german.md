<!--
Meta Description: # TypeScript: Das Schlüsselwort "default" – Eine umfassende Anleitung ## Synopsis Das Schlüsselwort "default" in TypeScript ermöglicht es Programmiere...
Meta Keywords: typescript, für, default, ein, schlüsselwort
-->

# TypeScript: Das Schlüsselwort "default" – Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort "default" in TypeScript ermöglicht es Programmierern, Standardwerte für Module, Funktionen und Parameter zu definieren, die beim Importieren oder Aufrufen verwendet werden können.

## Dokumentation
Das Schlüsselwort "default" wird hauptsächlich in zwei Kontexten verwendet: beim Export von Modulen und beim Festlegen von Standardparametern in Funktionen. 

### Modul-Export
In TypeScript können Module entweder benannte Exporte oder Standardexporte haben. Ein Standardexport erlaubt es, ein Modul mit einem bestimmten Namen zu exportieren, der beim Importieren verwendet werden kann. Dies ist besonders nützlich, wenn ein Modul eine Hauptfunktionalität oder -klasse bereitstellt.

**Syntax für den Standardexport:**
```typescript
export default <Element>;
```

### Standardparameter
Zusätzlich kann das Schlüsselwort "default" verwendet werden, um Standardwerte für Funktionsparameter zu definieren. Wenn kein Argument übergeben wird, wird der Standardwert verwendet.

**Syntax für Standardparameter:**
```typescript
function functionName(param: Type = defaultValue) {
    // Funktionskörper
}
```

## Beispiele

### Beispiel für Standardexport
```typescript
// myModule.ts
class MyClass {
    greet() {
        console.log("Hallo, Welt!");
    }
}

export default MyClass;
```

```typescript
// main.ts
import MyClass from './myModule';

const myInstance = new MyClass();
myInstance.greet(); // Ausgabe: "Hallo, Welt!"
```

### Beispiel für Standardparameter
```typescript
function add(a: number, b: number = 5): number {
    return a + b;
}

console.log(add(10)); // Ausgabe: 15
console.log(add(10, 20)); // Ausgabe: 30
```

## Erklärung
Ein häufiger Fallstrick beim Arbeiten mit dem Schlüsselwort "default" ist die Verwirrung zwischen Standardexporten und benannten Exporten. Wenn ein Modul einen Standardexport hat, kann es nur einen solchen Export haben, während mehrere benannte Exporte erlaubt sind. 

Zusätzlich sollte beachtet werden, dass beim Import eines Standardexports der Importname beliebig sein kann, was manchmal zu Verwirrung führen kann, wenn unterschiedliche Module ähnliche Standardexporte haben.

Ein weiterer Punkt ist, dass Standardparameter nicht nur für primitive Typen, sondern auch für Objekte und Arrays verwendet werden können. Dies kann die Handhabung von Funktionen, die optionale Konfigurationen benötigen, erheblich vereinfachen.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "default" in TypeScript ermöglicht es, Standardwerte für Module und Funktionsparameter festzulegen, um die Codewartung und Lesbarkeit zu verbessern.
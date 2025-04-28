<!--
Meta Description: # Uso de "default" en TypeScript: Exportaciones y Importaciones ## Sinopsis En TypeScript, la palabra clave `default` se utiliza en las exportaciones ...
Meta Keywords: default, typescript, módulo, exportación, que
-->

# Uso de "default" en TypeScript: Exportaciones y Importaciones

## Sinopsis
En TypeScript, la palabra clave `default` se utiliza en las exportaciones para designar una exportación principal de un módulo. Esto permite que otros módulos importen fácilmente esta exportación sin necesidad de utilizar llaves.

## Documentación
La declaración `default` en TypeScript permite que un módulo exporte un solo valor como la exportación principal. Cuando se utiliza `default`, el valor exportado puede ser importado con cualquier nombre en otros archivos, lo que mejora la flexibilidad del código.

### Propósito
El uso de `default` es útil para simplificar las exportaciones cuando un módulo tiene un valor que se considera el más relevante o principal. Esto es común en casos como clases, funciones o constantes que son el enfoque central del módulo.

### Uso
Para exportar un valor como `default`, se puede hacer de la siguiente manera:

```typescript
// archivo: miModulo.ts
export default class MiClase {
    constructor() {
        console.log('Instancia de MiClase creada');
    }
}
```

Para importarlo en otro archivo, se puede hacer así:

```typescript
// archivo: main.ts
import MiClase from './miModulo';

const instancia = new MiClase(); // Instancia de MiClase creada
```

## Ejemplos
### Ejemplo 1: Exportación de una función
```typescript
// archivo: suma.ts
export default function sumar(a: number, b: number): number {
    return a + b;
}

// archivo: app.ts
import sumar from './suma';

console.log(sumar(5, 3)); // 8
```

### Ejemplo 2: Exportación de una clase
```typescript
// archivo: Persona.ts
export default class Persona {
    constructor(public nombre: string) {}
}

// archivo: main.ts
import Persona from './Persona';

const persona = new Persona('Juan');
console.log(persona.nombre); // Juan
```

## Explicación
Al utilizar `export default`, hay algunas consideraciones a tener en cuenta:

- **Un solo valor por módulo**: Un módulo puede tener solo una exportación `default`. Si se intenta definir múltiples exportaciones `default`, TypeScript generará un error.
- **Importaciones sin llaves**: Al importar un valor `default`, no se utilizan llaves. Esto puede resultar confuso si el programador también está importando otras exportaciones nombradas del mismo módulo.
- **Renombrado de importaciones**: Como se puede importar con cualquier nombre, es común ver que algunos desarrolladores eligen nombres que difieren de la exportación original para adaptarse mejor a su contexto.

## Resumen en una línea
La palabra clave `default` en TypeScript permite exportar un único valor principal de un módulo, facilitando su importación en otros archivos sin necesidad de usar llaves.
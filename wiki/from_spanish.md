<!--
Meta Description: # Uso de "from" en TypeScript: Guía Completa ## Sinopsis La palabra clave "from" en TypeScript se utiliza principalmente en el contexto de módulos y l...
Meta Keywords: typescript, from, mimodulo, importar, que
-->

# Uso de "from" en TypeScript: Guía Completa

## Sinopsis
La palabra clave "from" en TypeScript se utiliza principalmente en el contexto de módulos y la importación de funcionalidades desde otros archivos o bibliotecas. Esta característica permite la modularización del código, facilitando la reutilización y organización del mismo.

## Documentación
En TypeScript, "from" se utiliza en la declaración de importaciones para indicar la fuente desde la cual se deben cargar los módulos. Esto es parte del sistema de módulos de ES6, que TypeScript soporta. La sintaxis básica para importar un módulo es:

```typescript
import { nombreExportado } from 'ruta-del-modulo';
```

### Propósito
El propósito principal de "from" es facilitar la importación de funciones, clases, interfaces y otros elementos exportados desde un archivo o paquete específico, permitiendo que el código sea más limpio y manejable.

### Uso
La declaración de importación con "from" se realiza de la siguiente manera:

1. **Importar Elementos Específicos**: Puedes importar elementos específicos de un módulo.
   ```typescript
   import { funcionUno, funcionDos } from './miModulo';
   ```

2. **Importar Todo un Módulo**: También puedes importar todo el contenido de un módulo bajo un espacio de nombres.
   ```typescript
   import * as MiModulo from './miModulo';
   ```

3. **Importaciones por Defecto**: Si un módulo exporta un valor por defecto, puedes importarlo de esta manera:
   ```typescript
   import MiFuncion from './miModulo';
   ```

## Ejemplos

### Ejemplo 1: Importación de Funciones
```typescript
// miModulo.ts
export function suma(a: number, b: number): number {
    return a + b;
}

// main.ts
import { suma } from './miModulo';

console.log(suma(5, 10)); // Output: 15
```

### Ejemplo 2: Importación de un Módulo Completo
```typescript
// miModulo.ts
export const PI = 3.14;
export function areaCirculo(radio: number): number {
    return PI * radio * radio;
}

// main.ts
import * as MiModulo from './miModulo';

console.log(MiModulo.areaCirculo(5)); // Output: 78.5
```

### Ejemplo 3: Importación por Defecto
```typescript
// miModulo.ts
const mensaje: string = "Hola, TypeScript!";
export default mensaje;

// main.ts
import mensaje from './miModulo';

console.log(mensaje); // Output: Hola, TypeScript!
```

## Explicación
Al usar "from", es importante tener en cuenta:

- **Rutas Relativas**: Asegúrate de que la ruta proporcionada sea correcta. Las rutas relativas deben comenzar con `./` o `../` dependiendo de la ubicación del archivo.
- **Exportaciones**: Solo puedes importar elementos que han sido exportados desde el módulo correspondiente. Si intentas importar algo que no existe, TypeScript generará un error.
- **Módulos de Terceros**: Cuando importas módulos de bibliotecas, asegúrate de que estén correctamente instalados y que TypeScript tenga acceso a sus definiciones de tipo.

## Resumen en una línea
La palabra clave "from" en TypeScript se utiliza para importar módulos y elementos específicos, facilitando la modularización y organización del código.
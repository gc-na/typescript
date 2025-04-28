<!--
Meta Description: # Importaciones en TypeScript: Guía Completa sobre el Comando "import" ## Sinopsis El comando `import` en TypeScript permite la inclusión de módulos y...
Meta Keywords: typescript, import, importar, number, from
-->

# Importaciones en TypeScript: Guía Completa sobre el Comando "import"

## Sinopsis
El comando `import` en TypeScript permite la inclusión de módulos y sus respectivas dependencias en un archivo, facilitando la organización y reutilización del código en aplicaciones JavaScript.

## Documentación
El comando `import` es fundamental en TypeScript y JavaScript moderno, ya que permite importar funciones, objetos o tipos de otros archivos o módulos. Esto fomenta la modularidad y el mantenimiento del código. 

### Propósito
- Facilitar la reutilización de código.
- Organizar el código en módulos más pequeños y manejables.
- Promover la separación de preocupaciones en el desarrollo de aplicaciones.

### Uso
La sintaxis básica del comando `import` es la siguiente:

```typescript
import { Elemento } from './ruta/al/modulo';
```

Existen diferentes formas de usar `import`:

1. **Importar elementos específicos**:
   ```typescript
   import { funcionUno, funcionDos } from './moduloFunciones';
   ```

2. **Importar todo un módulo**:
   ```typescript
   import * as Modulo from './moduloFunciones';
   ```

3. **Importar un módulo por defecto**:
   ```typescript
   import ModuloPorDefecto from './moduloPorDefecto';
   ```

4. **Importar tipos** (específico de TypeScript):
   ```typescript
   import type { Tipo } from './moduloTipos';
   ```

## Ejemplos
### Ejemplo 1: Importar funciones específicas
```typescript
// moduloFunciones.ts
export function sumar(a: number, b: number): number {
    return a + b;
}

export function restar(a: number, b: number): number {
    return a - b;
}

// main.ts
import { sumar, restar } from './moduloFunciones';

console.log(sumar(5, 3)); // Salida: 8
console.log(restar(5, 3)); // Salida: 2
```

### Ejemplo 2: Importar todo un módulo
```typescript
// moduloFunciones.ts
export function multiplicar(a: number, b: number): number {
    return a * b;
}

// main.ts
import * as Funciones from './moduloFunciones';

console.log(Funciones.multiplicar(4, 2)); // Salida: 8
```

### Ejemplo 3: Importar un módulo por defecto
```typescript
// moduloPorDefecto.ts
const mensaje = "Hola, TypeScript!";
export default mensaje;

// main.ts
import Mensaje from './moduloPorDefecto';

console.log(Mensaje); // Salida: Hola, TypeScript!
```

## Explicación
Al usar `import`, es crucial tener en cuenta lo siguiente:

- **Rutas relativas**: Asegúrate de que la ruta al módulo sea correcta. Las rutas relativas comienzan con `./` o `../`.
- **Exportaciones**: Solo se pueden importar elementos que han sido exportados explícitamente desde el módulo de origen.
- **Ciclo de importación**: Evita ciclos de importación, ya que pueden llevar a errores de referencia.
- **Compilación**: Asegúrate de que tu configuración de TypeScript (tsconfig.json) esté correctamente establecida para manejar módulos.

## Resumen en una línea
El comando `import` en TypeScript es esencial para incluir y gestionar módulos, facilitando la estructura y reutilización del código en aplicaciones JavaScript.
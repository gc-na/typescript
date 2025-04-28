<!--
Meta Description: # Exportar en TypeScript: Guía Completa sobre el Comando `export` ## Sinopsis El comando `export` en TypeScript es esencial para modularizar el código...
Meta Keywords: export, typescript, que, exportaciones, código
-->

# Exportar en TypeScript: Guía Completa sobre el Comando `export`

## Sinopsis
El comando `export` en TypeScript es esencial para modularizar el código y permitir que las funciones, clases o variables sean utilizadas en otros archivos. Este mecanismo de exportación es fundamental en el desarrollo de aplicaciones escalables y mantenibles.

## Documentación
El comando `export` se utiliza para exportar elementos de un módulo de TypeScript. Permite que las declaraciones, como funciones, clases o variables, sean accesibles desde otros módulos. Esto fomenta la reutilización del código y la organización de proyectos.

### Propósito
El propósito principal de `export` es hacer que partes del código sean accesibles en otros archivos, mejorando la modularidad y la claridad del código.

### Uso
Se pueden utilizar dos tipos de exportaciones en TypeScript: exportaciones nombradas y exportaciones por defecto.

1. **Exportaciones Nombradas**: Permiten exportar múltiples elementos desde un solo módulo. Se utilizan llaves al importar.
   ```typescript
   // archivo.ts
   export const PI = 3.14;
   export function sumar(a: number, b: number): number {
       return a + b;
   }
   ```

2. **Exportaciones por Defecto**: Permiten exportar un solo elemento desde un módulo. No se utilizan llaves al importar.
   ```typescript
   // clase.ts
   export default class Usuario {
       constructor(public nombre: string) {}
   }
   ```

## Ejemplos
### Exportaciones Nombradas
```typescript
// matematicas.ts
export const PI = 3.14;
export function multiplicar(a: number, b: number): number {
    return a * b;
}
```
```typescript
// app.ts
import { PI, multiplicar } from './matematicas';

console.log(PI); // 3.14
console.log(multiplicar(2, 3)); // 6
```

### Exportación por Defecto
```typescript
// producto.ts
export default class Producto {
    constructor(public nombre: string) {}
}
```
```typescript
// app.ts
import Producto from './producto';

const nuevoProducto = new Producto('Laptop');
console.log(nuevoProducto.nombre); // Laptop
```

## Explicación
Al usar `export`, es importante recordar lo siguiente:

- **Coherencia en los Nombres**: Al importar exportaciones nombradas, los nombres deben coincidir exactamente con los que se definieron en el módulo original.
- **Un Solo Default**: Solo puede haber una exportación por defecto por módulo, lo que debe ser considerado al estructurar el código.
- **Ciclos de Dependencias**: Evitar ciclos de dependencia entre módulos, ya que pueden causar errores en la ejecución.

## Resumen en Una Línea
El comando `export` en TypeScript permite la modularización del código, haciendo que funciones, clases o variables sean accesibles entre diferentes archivos.
<!--
Meta Description: # readonly en TypeScript: Uso y Ejemplos ## Sinopsis El modificador `readonly` en TypeScript permite definir propiedades de objetos que no pueden ser ...
Meta Keywords: readonly, que, una, typescript, string
-->

# readonly en TypeScript: Uso y Ejemplos

## Sinopsis
El modificador `readonly` en TypeScript permite definir propiedades de objetos que no pueden ser modificadas después de su inicialización. Esto mejora la seguridad del tipo y ayuda a prevenir errores en el código.

## Documentación
El modificador `readonly` se utiliza principalmente en las propiedades de una clase o en los elementos de una interfaz. Su uso asegura que estas propiedades no puedan ser cambiadas una vez que han sido establecidas, lo que es especialmente útil en el manejo de datos inmutables.

### Propósito
El propósito del modificador `readonly` es proporcionar una forma de declarar que ciertas propiedades de los objetos son inmutables, aumentando así la robustez del código y reduciendo la posibilidad de errores.

### Uso
Para utilizar `readonly`, simplemente se coloca antes de la declaración de la propiedad en una interfaz o clase:

```typescript
class Persona {
    readonly nombre: string;

    constructor(nombre: string) {
        this.nombre = nombre;
    }
}
```

En este ejemplo, la propiedad `nombre` es de solo lectura, lo que significa que no se puede modificar una vez que se ha asignado en el constructor.

### Detalles
1. **Efecto en Interfaces**: Al usar `readonly` en una interfaz, se garantiza que las propiedades no puedan ser cambiadas por ninguna instancia que implemente dicha interfaz.
   
   ```typescript
   interface Producto {
       readonly id: number;
       nombre: string;
   }
   ```

2. **Uso en Arrays**: Se puede aplicar `readonly` a elementos dentro de un array, indicando que el array no puede ser modificado.

   ```typescript
   const numeros: readonly number[] = [1, 2, 3];
   ```

3. **Compatibilidad**: Si bien `readonly` se usa comúnmente en clases e interfaces, no se puede utilizar en tipos primitivos directamente.

## Ejemplos
### Ejemplo 1: Clase con propiedad readonly
```typescript
class Coche {
    readonly marca: string;

    constructor(marca: string) {
        this.marca = marca;
    }
}

const miCoche = new Coche('Toyota');
// miCoche.marca = 'Honda'; // Error: Cannot assign to 'marca' because it is a read-only property.
```

### Ejemplo 2: Interfaz con propiedades readonly
```typescript
interface Usuario {
    readonly id: number;
    nombre: string;
}

const usuario: Usuario = { id: 1, nombre: 'Juan' };
// usuario.id = 2; // Error: Cannot assign to 'id' because it is a read-only property.
```

### Ejemplo 3: Array readonly
```typescript
const colores: readonly string[] = ['rojo', 'verde', 'azul'];
// colores.push('amarillo'); // Error: Property 'push' does not exist on type 'readonly string[]'.
```

## Explicación
Al utilizar `readonly`, hay algunas cosas que se deben tener en cuenta:

- **Inmutabilidad**: Aunque una propiedad es de solo lectura, si es un objeto o un array, sus propiedades internas pueden seguir siendo mutables.
  
    ```typescript
    class Grupo {
        readonly miembros: string[];

        constructor(miembros: string[]) {
            this.miembros = miembros;
        }
    }

    const grupo = new Grupo(['Ana', 'Luis']);
    grupo.miembros.push('Pedro'); // Esto es válido porque la referencia al array no ha cambiado.
    ```

- **Errores comunes**: Un error común es intentar asignar un valor a una propiedad `readonly` después de su inicialización. Esto generará un error de compilación, lo cual es una de las características de seguridad que `readonly` proporciona.

## Resumen en una línea
El modificador `readonly` en TypeScript permite declarar propiedades inmutables en objetos y clases, mejorando la seguridad y estabilidad del código.
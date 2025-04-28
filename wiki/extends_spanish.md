<!--
Meta Description: # Extends en TypeScript: Comprendiendo la Herencia y la Extensibilidad ## Sinopsis El término "extends" en TypeScript se utiliza para crear relaciones...
Meta Keywords: extends, typescript, clases, que, herencia
-->

# Extends en TypeScript: Comprendiendo la Herencia y la Extensibilidad

## Sinopsis
El término "extends" en TypeScript se utiliza para crear relaciones de herencia entre clases y para extender tipos. Esta palabra clave permite a los desarrolladores construir jerarquías de clases y reutilizar código de manera eficiente, mejorando la organización y la mantenibilidad del código.

## Documentación
En TypeScript, `extends` se utiliza en dos contextos principales: en la herencia de clases y en la extensión de tipos.

### Herencia de Clases
Cuando se define una clase en TypeScript, se puede utilizar `extends` para heredar propiedades y métodos de otra clase. La clase que extiende se denomina "subclase", mientras que la clase de la que se hereda se denomina "superclase".

**Sintaxis:**
```typescript
class SuperClase {
    // Propiedades y métodos de la superclase
}

class SubClase extends SuperClase {
    // Propiedades y métodos adicionales
}
```

### Extensión de Tipos
`extends` también se usa en la definición de tipos genéricos. Permite a un tipo genérico especificar que debe ser un subtipo de otro tipo.

**Sintaxis:**
```typescript
function funcionGenerica<T extends TipoBase>(param: T): void {
    // Implementación de la función
}
```

## Ejemplos

### Ejemplo de Herencia de Clases
```typescript
class Animal {
    hacerSonido(): void {
        console.log("El animal hace un sonido");
    }
}

class Perro extends Animal {
    hacerSonido(): void {
        console.log("El perro ladra");
    }
}

const miPerro = new Perro();
miPerro.hacerSonido(); // Salida: "El perro ladra"
```

### Ejemplo de Extensión de Tipos
```typescript
interface Vehiculo {
    ruedas: number;
}

function mostrarRuedas<T extends Vehiculo>(vehiculo: T): void {
    console.log(`El vehículo tiene ${vehiculo.ruedas} ruedas.`);
}

const coche = { ruedas: 4 };
mostrarRuedas(coche); // Salida: "El vehículo tiene 4 ruedas."
```

## Explicación
Al usar `extends`, es importante tener en cuenta algunas consideraciones:

- **Herencia Múltiple**: TypeScript no soporta la herencia múltiple de clases. Una clase solo puede extender de una superclase.
- **Interfaces**: Las interfaces pueden extender múltiples interfaces, permitiendo una mayor flexibilidad.
- **Accesibilidad**: Asegúrate de que los métodos y propiedades que deseas heredar sean accesibles (públicos o protegidos).

Un error común es olvidar llamar al constructor de la superclase desde el constructor de la subclase, lo que puede llevar a errores en tiempo de ejecución.

## Resumen en Una Línea
La palabra clave `extends` en TypeScript permite crear clases y tipos que heredan propiedades y métodos de otras clases o interfaces, facilitando la reutilización y organización del código.
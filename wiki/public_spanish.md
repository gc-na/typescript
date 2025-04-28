<!--
Meta Description: # Modificador "public" en TypeScript: Todo lo que Necesitas Saber ## Sinopsis El modificador `public` en TypeScript se utiliza para definir la accesib...
Meta Keywords: public, clase, modificador, typescript, que
-->

# Modificador "public" en TypeScript: Todo lo que Necesitas Saber

## Sinopsis
El modificador `public` en TypeScript se utiliza para definir la accesibilidad de las propiedades y métodos de una clase, permitiendo que estos sean accesibles desde cualquier parte del código.

## Documentación
El modificador `public` es uno de los tres modificadores de acceso disponibles en TypeScript, junto con `private` y `protected`. Por defecto, todas las propiedades y métodos de una clase son `public` si no se especifica otro modificador. Esto significa que cualquier componente del programa, ya sea interno o externo a la clase, puede acceder a ellos.

### Propósito
El propósito principal de `public` es proporcionar una forma de hacer que las propiedades y métodos de una clase sean accesibles globalmente, facilitando la interacción con instancias de la clase.

### Uso
Para utilizar el modificador `public`, simplemente se declara en la definición de una clase. Aquí hay un ejemplo básico:

```typescript
class Persona {
    public nombre: string;
    public edad: number;

    constructor(nombre: string, edad: number) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public saludar(): string {
        return `Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`;
    }
}
```

En este ejemplo, tanto las propiedades `nombre` y `edad` como el método `saludar` son públicos.

## Ejemplos
### Ejemplo 1: Definición de Propiedades Públicas
```typescript
class Coche {
    public marca: string;
    public modelo: string;

    constructor(marca: string, modelo: string) {
        this.marca = marca;
        this.modelo = modelo;
    }
}

const miCoche = new Coche("Toyota", "Corolla");
console.log(miCoche.marca); // Salida: Toyota
```

### Ejemplo 2: Uso de Métodos Públicos
```typescript
class Calculadora {
    public sumar(a: number, b: number): number {
        return a + b;
    }
}

const calc = new Calculadora();
console.log(calc.sumar(5, 10)); // Salida: 15
```

## Explicación
Aunque el modificador `public` es muy útil, hay ciertos aspectos a tener en cuenta:

- **Acceso Global**: Dado que las propiedades y métodos públicos son accesibles desde cualquier parte, es importante tener en cuenta la encapsulación. Si se expone demasiado, se puede comprometer la integridad de la clase.
- **No es Obligatorio**: Si no se especifica un modificador de acceso, TypeScript asume que es `public` por defecto. Esto puede llevar a confusiones si los desarrolladores no son conscientes de esta característica.
- **Mejores Prácticas**: Aunque `public` permite un acceso fácil, es recomendable utilizar `private` o `protected` para propiedades que no deberían ser accesibles fuera de la clase.

## Resumen en una Línea
El modificador `public` en TypeScript permite que las propiedades y métodos de una clase sean accesibles desde cualquier parte del código, fomentando la interactividad con las instancias de la clase.
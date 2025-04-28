<!--
Meta Description: # Interfaces en TypeScript: Definición y Uso Efectivo ## Sinopsis Las interfaces en TypeScript son estructuras que permiten definir la forma de objeto...
Meta Keywords: interfaces, que, typescript, las, objetos
-->

# Interfaces en TypeScript: Definición y Uso Efectivo

## Sinopsis
Las interfaces en TypeScript son estructuras que permiten definir la forma de objetos, especificando propiedades y métodos. Son fundamentales para la programación orientada a objetos y ayudan a garantizar que los objetos cumplan con ciertos contratos.

## Documentación
Las interfaces en TypeScript son una característica clave que permite a los desarrolladores definir la forma de un objeto. Esto incluye la especificación de propiedades y sus tipos, así como métodos que el objeto puede implementar. A diferencia de las clases, las interfaces no se pueden instanciar, pero pueden ser implementadas por clases o utilizadas para tipar objetos.

### Propósito
El uso de interfaces ayuda a:
- Mejorar la legibilidad del código.
- Proporcionar una forma clara de definir contratos para objetos.
- Facilitar la reutilización de código y la interoperabilidad entre diferentes partes de una aplicación.

### Uso
Para definir una interfaz, se utiliza la palabra clave `interface` seguida de su nombre y la definición de sus propiedades y métodos. A continuación se muestra la sintaxis básica:

```typescript
interface NombreInterfaz {
    propiedad1: tipo;
    propiedad2: tipo;
    metodo1(parametro: tipo): tipo;
}
```

## Ejemplos

### Ejemplo 1: Definición básica de una interfaz
```typescript
interface Persona {
    nombre: string;
    edad: number;
}

const usuario: Persona = {
    nombre: "Juan",
    edad: 30
};
```

### Ejemplo 2: Interfaz con métodos
```typescript
interface Vehiculo {
    marca: string;
    acelerar(): void;
}

class Coche implements Vehiculo {
    marca: string;

    constructor(marca: string) {
        this.marca = marca;
    }

    acelerar() {
        console.log(`${this.marca} está acelerando.`);
    }
}

const miCoche = new Coche("Toyota");
miCoche.acelerar(); // Toyota está acelerando.
```

## Explicación
Al utilizar interfaces, es importante recordar que:
- Una interfaz puede extenderse a otra, permitiendo la creación de jerarquías.
- Las interfaces pueden ser implementadas por múltiples clases, lo que fomenta la reutilización del código.
- No se pueden instanciar directamente, lo que significa que no puedes crear objetos de tipo interfaz.

### Errores comunes
- **No definir completamente la interfaz:** Si olvidas definir alguna propiedad obligatoria, TypeScript generará un error en tiempo de compilación.
- **Confundir interfaces con clases:** Recuerda que las interfaces no contienen implementación, solo definición.

## Resumen en una línea
Las interfaces en TypeScript son plantillas que definen la estructura de objetos, mejorando la claridad y la seguridad del código.
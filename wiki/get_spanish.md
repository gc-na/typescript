<!--
Meta Description: # Uso de "get" en TypeScript: Acceso a Propiedades de Objetos ## Sinopsis En TypeScript, "get" es un modificador que permite definir un método de acce...
Meta Keywords: que, get, typescript, lógica, valor
-->

# Uso de "get" en TypeScript: Acceso a Propiedades de Objetos

## Sinopsis
En TypeScript, "get" es un modificador que permite definir un método de acceso (getter) para una propiedad de clase. Esta característica ayuda a encapsular la lógica de acceso a los datos, permitiendo que se realicen cálculos o transformaciones antes de devolver el valor.

## Documentación
El modificador "get" se utiliza en la definición de clases en TypeScript para crear métodos que permiten obtener el valor de una propiedad de forma controlada. A diferencia de las propiedades convencionales, los getters pueden incluir lógica adicional, como validaciones o cálculos.

### Propósito
El propósito principal de "get" es proporcionar un mecanismo para acceder a propiedades de una forma más segura y controlada, mejorando la legibilidad y mantenibilidad del código.

### Uso
Para definir un getter en TypeScript, se utiliza la palabra clave "get" seguida del nombre de la propiedad que se quiere acceder. El método debe devolver un valor y puede incluir lógica que se ejecute cada vez que se accede a la propiedad.

#### Sintaxis:
```typescript
class NombreDeLaClase {
    private _propiedad: Tipo;

    constructor(valor: Tipo) {
        this._propiedad = valor;
    }

    get propiedad(): Tipo {
        // Lógica adicional (opcional)
        return this._propiedad;
    }
}
```

## Ejemplos
### Ejemplo básico de uso de "get":
```typescript
class Circulo {
    private _radio: number;

    constructor(radio: number) {
        this._radio = radio;
    }

    get area(): number {
        return Math.PI * this._radio * this._radio; // Cálculo del área
    }
}

const circulo = new Circulo(5);
console.log(circulo.area); // Imprime el área del círculo
```

### Ejemplo con lógica de validación:
```typescript
class Persona {
    private _nombre: string;

    constructor(nombre: string) {
        this._nombre = nombre;
    }

    get nombre(): string {
        return this._nombre.toUpperCase(); // Devuelve el nombre en mayúsculas
    }
}

const persona = new Persona("Juan");
console.log(persona.nombre); // Imprime "JUAN"
```

## Explicación
Al utilizar "get", es importante tener en cuenta ciertos aspectos:
- Los getters pueden ser utilizados como propiedades, lo que significa que no se deben invocar como funciones (sin paréntesis).
- Si se intenta asignar un valor a una propiedad que solo tiene un getter y no un setter, se producirá un error de compilación.
- Los getters pueden hacer que el código sea más difícil de depurar si contienen lógica compleja, ya que pueden ocultar el comportamiento real de cómo se obtiene el valor.

## Resumen en una línea
El modificador "get" en TypeScript permite definir métodos de acceso que encapsulan la lógica de obtención de propiedades, mejorando la seguridad y la legibilidad del código.
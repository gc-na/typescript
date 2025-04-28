<!--
Meta Description: # Uso de "super" en TypeScript: Herencia y Métodos de Clases ## Sinopsis El comando `super` en TypeScript se utiliza para acceder a métodos y propieda...
Meta Keywords: clase, super, padre, constructor, typescript
-->

# Uso de "super" en TypeScript: Herencia y Métodos de Clases

## Sinopsis
El comando `super` en TypeScript se utiliza para acceder a métodos y propiedades de la clase padre en una jerarquía de herencia, permitiendo así extender y modificar el comportamiento de las clases.

## Documentación
En TypeScript, `super` es una palabra clave que se emplea en el contexto de la herencia de clases. Permite invocar métodos y acceder a propiedades de la clase padre, facilitando la reutilización del código y la implementación de un comportamiento más complejo en las clases derivadas.

### Propósito
El propósito principal de `super` es permitir a los desarrolladores:
- Llamar a constructores de la clase padre.
- Acceder a métodos de la clase padre desde la clase hija.
- Proporcionar un mecanismo para extender funcionalidades sin reescribir código existente.

### Uso
Para utilizar `super`, debes estar dentro de una clase hija que extienda de una clase padre. Puedes llamar a `super` en el constructor de la clase hija para inicializar la clase padre y acceder a sus métodos en cualquier otra función de la clase hija.

## Ejemplos

### Ejemplo 1: Llamando al Constructor de la Clase Padre
```typescript
class Animal {
    constructor(public nombre: string) {}
    
    hacerSonido() {
        console.log(`${this.nombre} hace un sonido.`);
    }
}

class Perro extends Animal {
    constructor(nombre: string) {
        super(nombre); // Llama al constructor de Animal
    }

    hacerSonido() {
        super.hacerSonido(); // Llama al método de Animal
        console.log(`${this.nombre} ladra.`);
    }
}

const miPerro = new Perro("Rex");
miPerro.hacerSonido();
// Salida:
// Rex hace un sonido.
// Rex ladra.
```

### Ejemplo 2: Accediendo a Propiedades de la Clase Padre
```typescript
class Vehiculo {
    constructor(public marca: string) {}
    
    mostrarMarca() {
        console.log(`Marca: ${this.marca}`);
    }
}

class Coche extends Vehiculo {
    constructor(marca: string, public modelo: string) {
        super(marca); // Llama al constructor de Vehiculo
    }

    mostrarDetalles() {
        super.mostrarMarca(); // Llama al método de Vehiculo
        console.log(`Modelo: ${this.modelo}`);
    }
}

const miCoche = new Coche("Toyota", "Corolla");
miCoche.mostrarDetalles();
// Salida:
// Marca: Toyota
// Modelo: Corolla
```

## Explicación
Es importante tener en cuenta que:
- `super` solo puede ser utilizado dentro de métodos de clases que heredan de otra clase.
- Al llamar a `super` en el constructor de una clase hija, se debe hacer antes de usar `this`, ya que `this` no estará definido hasta que se llame al constructor de la clase padre.
- Si no se llama al constructor de la clase padre, TypeScript lanzará un error, ya que no se podrá inicializar correctamente la instancia de la clase hija.

## Resumen en una línea
La palabra clave `super` en TypeScript permite acceder y extender las propiedades y métodos de la clase padre en una jerarquía de herencia.
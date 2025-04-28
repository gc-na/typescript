<!--
Meta Description: # Uso de "protected" en TypeScript: Acceso Controlado en Clases ## Sinopsis El modificador de acceso `protected` en TypeScript permite que las propied...
Meta Keywords: protected, clase, que, acceso, una
-->

# Uso de "protected" en TypeScript: Acceso Controlado en Clases

## Sinopsis
El modificador de acceso `protected` en TypeScript permite que las propiedades y métodos de una clase sean accesibles dentro de la misma clase y en las clases que la extienden, proporcionando una forma de controlar el acceso a los miembros de la clase.

## Documentación
El modificador `protected` se utiliza en TypeScript para definir la visibilidad de las propiedades y métodos de una clase. A diferencia de `public`, que permite el acceso a todos, y `private`, que restringe el acceso solo a la propia clase, `protected` permite que las subclases accedan a sus miembros.

### Propósito
El propósito de `protected` es proporcionar un nivel intermedio de acceso, permitiendo que solo las clases derivadas puedan utilizar las propiedades y métodos marcados como `protected`.

### Uso
Para utilizar `protected`, se debe declarar una propiedad o método dentro de una clase anteponiendo la palabra clave `protected`. Esto asegura que solo la clase que lo define y sus subclases puedan acceder a él.

#### Sintaxis
```typescript
class NombreDeClase {
    protected propiedad: Tipo;

    protected metodo(): Tipo {
        // implementación
    }
}
```

## Ejemplos
### Ejemplo 1: Propiedad protegida
```typescript
class Animal {
    protected nombre: string;

    constructor(nombre: string) {
        this.nombre = nombre;
    }
}

class Perro extends Animal {
    public ladrar(): void {
        console.log(`¡${this.nombre} dice guau!`);
    }
}

const miPerro = new Perro("Rex");
miPerro.ladrar(); // ¡Rex dice guau!
```

### Ejemplo 2: Método protegido
```typescript
class Vehiculo {
    protected acelerar(): void {
        console.log("El vehículo está acelerando.");
    }
}

class Coche extends Vehiculo {
    public iniciar(): void {
        this.acelerar(); // Acceso permitido
    }
}

const miCoche = new Coche();
miCoche.iniciar(); // El vehículo está acelerando.
```

## Explicación
Algunos puntos a tener en cuenta sobre el modificador `protected`:

- **Acceso Restringido**: Los miembros `protected` no son accesibles desde fuera de la clase o de sus subclases. Intentar acceder a ellos desde una instancia de la clase resultará en un error de compilación.
- **Herencia**: Permite que las subclases accedan a los miembros `protected`, lo que es útil para la extensión de funcionalidades sin exponer los detalles internos a otras partes del código.
- **No accesible desde instancias**: A diferencia de `public`, no puedes acceder a miembros `protected` directamente desde una instancia de la clase.

### Errores Comunes
- **Intentar acceder a un miembro `protected` desde fuera de la clase**: Esto generará un error de compilación. Asegúrate de acceder a estos miembros solo desde la propia clase o clases derivadas.
- **Confundir `protected` con `private`**: Recuerda que `private` es aún más restrictivo, ya que solo permite acceso a la propia clase.

## Resumen en una línea
El modificador `protected` en TypeScript permite el acceso a propiedades y métodos solo desde la clase que los define y sus subclases.
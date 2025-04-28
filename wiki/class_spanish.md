<!--
Meta Description: # Clases en TypeScript: Guía Completa ## Sinopsis Las clases en TypeScript son una característica fundamental del lenguaje que permite la creación de ...
Meta Keywords: typescript, string, una, public, clases
-->

# Clases en TypeScript: Guía Completa

## Sinopsis
Las clases en TypeScript son una característica fundamental del lenguaje que permite la creación de objetos y la implementación de programación orientada a objetos, facilitando la organización y reutilización del código.

## Documentación
TypeScript es un superconjunto de JavaScript que añade tipado estático y otras características avanzadas, incluida la programación orientada a objetos a través de clases. Una clase en TypeScript es una plantilla para crear objetos que encapsulan datos y comportamientos relacionados.

### Propósito
El propósito principal de las clases en TypeScript es proporcionar una estructura clara y reutilizable para el desarrollo de aplicaciones, permitiendo a los desarrolladores crear objetos con propiedades y métodos específicos.

### Uso
Para definir una clase en TypeScript, se utiliza la palabra clave `class`, seguida del nombre de la clase. Dentro de la clase, se pueden definir propiedades y métodos. También se pueden utilizar modificadores de acceso como `public`, `private` y `protected` para controlar la visibilidad de las propiedades y métodos.

```typescript
class Persona {
    private nombre: string;
    private edad: number;

    constructor(nombre: string, edad: number) {
        this.nombre = nombre;
        this.edad = edad;
    }

    public saludar(): string {
        return `Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`;
    }
}
```

## Ejemplos
### Ejemplo Básico
A continuación se presenta un ejemplo básico de una clase que representa un coche:

```typescript
class Coche {
    public marca: string;
    public modelo: string;

    constructor(marca: string, modelo: string) {
        this.marca = marca;
        this.modelo = modelo;
    }

    public descripcion(): string {
        return `Este coche es un ${this.marca} modelo ${this.modelo}.`;
    }
}

const miCoche = new Coche('Toyota', 'Corolla');
console.log(miCoche.descripcion());
```

### Herencia
TypeScript también soporta la herencia de clases, permitiendo a una clase derivada heredar propiedades y métodos de una clase base:

```typescript
class Vehiculo {
    public tipo: string;

    constructor(tipo: string) {
        this.tipo = tipo;
    }

    public info(): string {
        return `Este es un vehículo de tipo ${this.tipo}.`;
    }
}

class Motocicleta extends Vehiculo {
    public cilindrada: number;

    constructor(tipo: string, cilindrada: number) {
        super(tipo);
        this.cilindrada = cilindrada;
    }

    public infoCompleta(): string {
        return `${super.info()} Tiene una cilindrada de ${this.cilindrada}cc.`;
    }
}

const miMoto = new Motocicleta('motocicleta', 150);
console.log(miMoto.infoCompleta());
```

## Explicación
### Errores Comunes
- **Acceso a propiedades privadas:** Intentar acceder a propiedades marcadas como `private` desde fuera de la clase resultará en un error de compilación.
- **Olvidar el `constructor`:** Si no se define un constructor y se intenta inicializar propiedades, el código no funcionará como se espera.
- **Confusión entre `public`, `private` y `protected`:** Es importante entender cómo estos modificadores afectan la accesibilidad de las propiedades y métodos.

### Notas Adicionales
- Las clases en TypeScript son compatibles con las características de JavaScript, lo que significa que las clases pueden incluir métodos estáticos, getters y setters.
- TypeScript ofrece soporte para la creación de interfaces que pueden ser implementadas por clases, lo que ayuda a definir contratos de programación más claros.

## Resumen en Una Línea
Las clases en TypeScript permiten la creación de objetos y la implementación de la programación orientada a objetos, mejorando la organización y reutilización del código.
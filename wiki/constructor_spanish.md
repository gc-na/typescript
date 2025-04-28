<!--
Meta Description: # Constructor en TypeScript: Definición y Uso ## Sinopsis El constructor en TypeScript es un método especial que se utiliza para inicializar un objeto...
Meta Keywords: constructor, nombre, clase, precio, typescript
-->

# Constructor en TypeScript: Definición y Uso

## Sinopsis
El constructor en TypeScript es un método especial que se utiliza para inicializar un objeto recién creado. Se invoca automáticamente al crear una instancia de una clase y permite establecer propiedades iniciales y ejecutar lógica de configuración.

## Documentación
En TypeScript, un constructor es un método que forma parte de una clase. Se define mediante la palabra clave `constructor` y puede aceptar parámetros para inicializar propiedades de la clase. La sintaxis básica de un constructor es la siguiente:

```typescript
class NombreDeLaClase {
    constructor(parametros) {
        // Inicialización
    }
}
```

### Propósito
El propósito principal de un constructor es permitir a los desarrolladores inicializar objetos con valores específicos en el momento de su creación. Esto proporciona un control más fino sobre cómo se configuran los objetos y permite establecer invariantes en el estado del objeto.

### Uso
- **Definición de Propiedades**: Se pueden definir propiedades de la clase y asignarles valores dentro del constructor.
- **Lógica de Inicialización**: Se puede incluir lógica adicional que debe ejecutarse cada vez que se crea un objeto de la clase.
  
### Detalles
- Un constructor no puede tener un tipo de retorno.
- Solo puede haber un constructor por clase, aunque se puede implementar sobrecarga de constructores utilizando parámetros opcionales.

## Ejemplos

### Ejemplo Básico
```typescript
class Persona {
    nombre: string;
    edad: number;

    constructor(nombre: string, edad: number) {
        this.nombre = nombre;
        this.edad = edad;
    }

    mostrarInfo() {
        console.log(`Nombre: ${this.nombre}, Edad: ${this.edad}`);
    }
}

const persona1 = new Persona('Juan', 30);
persona1.mostrarInfo(); // Salida: Nombre: Juan, Edad: 30
```

### Ejemplo con Parámetros Opcionales
```typescript
class Producto {
    nombre: string;
    precio: number;

    constructor(nombre: string, precio?: number) {
        this.nombre = nombre;
        this.precio = precio || 0; // Precio por defecto a 0
    }

    mostrarDetalles() {
        console.log(`Producto: ${this.nombre}, Precio: ${this.precio}`);
    }
}

const producto1 = new Producto('Laptop', 1500);
const producto2 = new Producto('Mouse');
producto1.mostrarDetalles(); // Salida: Producto: Laptop, Precio: 1500
producto2.mostrarDetalles(); // Salida: Producto: Mouse, Precio: 0
```

## Explicación
Al utilizar constructores, es importante tener en cuenta lo siguiente:
- **Inicialización de Propiedades**: Asegúrate de inicializar todas las propiedades requeridas dentro del constructor para evitar errores en tiempo de ejecución.
- **Sobrecarga de Constructores**: TypeScript no permite múltiples constructores. Para lograr un comportamiento similar, se pueden usar parámetros opcionales o sobrecarga de funciones.
- **Uso de `this`**: Recuerda que `this` hace referencia a la instancia actual de la clase, y se debe utilizar dentro del constructor para acceder a las propiedades de la clase.

## Resumen en una Línea
El constructor en TypeScript es un método que inicializa una clase y establece propiedades en el momento de crear una instancia.
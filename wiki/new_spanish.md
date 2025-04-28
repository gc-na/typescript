<!--
Meta Description: # Uso de "new" en TypeScript: Creación de Instancias de Clases ## Sinopsis El operador `new` en TypeScript se utiliza para crear instancias de clases,...
Meta Keywords: new, constructor, typescript, que, clase
-->

# Uso de "new" en TypeScript: Creación de Instancias de Clases

## Sinopsis
El operador `new` en TypeScript se utiliza para crear instancias de clases, permitiendo la instanciación de objetos y el acceso a sus métodos y propiedades.

## Documentación

### Propósito
El operador `new` es fundamental en la programación orientada a objetos en TypeScript, ya que permite crear instancias de clases definidas por el usuario. Al invocar una clase con `new`, se inicializa un nuevo objeto y se ejecuta el constructor de la clase, lo que permite establecer valores iniciales y configurar el objeto.

### Uso
La sintaxis básica para utilizar `new` es la siguiente:

```typescript
const objeto = new Clase();
```

- **Clase**: Es el nombre de la clase que deseas instanciar.
- **objeto**: Es la variable que almacenará la nueva instancia.

### Detalles
- Cuando se utiliza `new`, el constructor de la clase se ejecuta automáticamente.
- Si el constructor no está definido, TypeScript proporcionará un constructor predeterminado.
- Las instancias creadas con `new` pueden acceder a métodos y propiedades definidos en la clase.

## Ejemplos

### Ejemplo básico de uso de `new`

```typescript
class Persona {
    nombre: string;

    constructor(nombre: string) {
        this.nombre = nombre;
    }

    saludar() {
        console.log(`Hola, mi nombre es ${this.nombre}`);
    }
}

const persona1 = new Persona("Juan");
persona1.saludar(); // Salida: Hola, mi nombre es Juan
```

### Ejemplo con parámetros

```typescript
class Coche {
    marca: string;
    modelo: string;

    constructor(marca: string, modelo: string) {
        this.marca = marca;
        this.modelo = modelo;
    }

    mostrarDetalles() {
        console.log(`Coche: ${this.marca} ${this.modelo}`);
    }
}

const coche1 = new Coche("Toyota", "Corolla");
coche1.mostrarDetalles(); // Salida: Coche: Toyota Corolla
```

## Explicación
Algunos problemas comunes al usar `new` incluyen:

- **Olvidar usar `new`**: Si llamas a un constructor sin `new`, `this` no se referirá a la nueva instancia, lo que puede llevar a errores.
  
  ```typescript
  const objetoIncorrecto = Persona("Carlos"); // Error: this es undefined
  ```

- **Tipos de retorno**: Asegúrate de que el constructor retorne un objeto de la clase, ya que si se retorna un valor primitivo, se ignorará el retorno.

- **Constructor no definido**: Si no defines un constructor, TypeScript generará uno predeterminado que no requiere parámetros.

## Resumen en una línea
El operador `new` en TypeScript permite crear instancias de clases, ejecutando su constructor y habilitando el acceso a sus propiedades y métodos.
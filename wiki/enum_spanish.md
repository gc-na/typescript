<!--
Meta Description: # Enum en TypeScript: Guía Completa y Ejemplos Prácticos ## Sinopsis Los `enum` en TypeScript son una característica que permite definir un conjunto d...
Meta Keywords: enum, typescript, los, valores, que
-->

# Enum en TypeScript: Guía Completa y Ejemplos Prácticos

## Sinopsis
Los `enum` en TypeScript son una característica que permite definir un conjunto de constantes con nombres, facilitando la legibilidad y el mantenimiento del código al trabajar con conjuntos de valores relacionados.

## Documentación
### Propósito
Los `enum` son utilizados para crear un grupo de constantes con un nombre significativo, lo que ayuda a evitar el uso de valores mágicos en el código. Esto mejora la claridad y la calidad del código, además de facilitar su mantenimiento.

### Uso
En TypeScript, un `enum` se define utilizando la palabra clave `enum`, seguido del nombre del `enum` y un bloque de llaves que contiene las constantes. Puedes asignarles valores específicos o dejarlos que se autoincrementen.

#### Sintaxis básica:
```typescript
enum NombreEnum {
    Valor1,
    Valor2,
    Valor3
}
```

#### Asignación de valores:
```typescript
enum Color {
    Rojo = 1,
    Verde,
    Azul
}
```

En este ejemplo, `Rojo` se asigna a 1, `Verde` a 2 y `Azul` a 3.

### Detalles
Los `enum` pueden ser de tipo numérico o de cadena. Los `enum` numéricos son los más comunes, pero los `enum` de cadena son útiles para representar valores que no se pueden auto-incrementar.

#### Enum numérico:
```typescript
enum Direccion {
    Arriba = 1,
    Abajo,
    Izquierda,
    Derecha
}
```

#### Enum de cadena:
```typescript
enum Estado {
    Activo = "ACTIVO",
    Inactivo = "INACTIVO",
    Pendiente = "PENDIENTE"
}
```

Los `enum` también pueden ser utilizados en comparación, permitiendo que se utilicen en estructuras de control como `switch` o condicionales.

## Ejemplos
### Ejemplo 1: Enum básico
```typescript
enum Animal {
    Perro,
    Gato,
    Pajaro
}

let miMascota: Animal = Animal.Gato;
console.log(miMascota); // Salida: 1
```

### Ejemplo 2: Enum con valores personalizados
```typescript
enum Mes {
    Enero = 1,
    Febrero,
    Marzo
}

let mesActual: Mes = Mes.Febrero;
console.log(mesActual); // Salida: 2
```

### Ejemplo 3: Enum de cadena
```typescript
enum Tamano {
    Pequeno = "PEQUEÑO",
    Mediano = "MEDIANO",
    Grande = "GRANDE"
}

let miTamano: Tamano = Tamano.Mediano;
console.log(miTamano); // Salida: "MEDIANO"
```

## Explicación
Es importante tener en cuenta que los `enum` son una característica que agrega un nivel de abstracción al código. Algunos errores comunes incluyen:

- **Confusión entre enums numéricos y de cadena**: Asegúrate de usar el tipo adecuado según el contexto.
- **Cambio de valores en enums**: Modificar los valores asignados a un `enum` puede causar problemas si esos valores se utilizan en otras partes del código.
- **No utilizar enums en lugar de tipos de unión**: En algunos casos, es más adecuado utilizar tipos de unión para representar un conjunto de valores.

## Resumen en una línea
Los `enum` en TypeScript brindan una forma elegante y legible de manejar un conjunto de constantes relacionadas, mejorando la claridad y el mantenimiento del código.
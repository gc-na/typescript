<!--
Meta Description: # Abstract em TypeScript: Entenda Como Utilizar Classes Abstratas ## Sinopse O conceito de "abstract" em TypeScript permite a definição de classes e m...
Meta Keywords: classes, abstract, métodos, typescript, que
-->

# Abstract em TypeScript: Entenda Como Utilizar Classes Abstratas

## Sinopse
O conceito de "abstract" em TypeScript permite a definição de classes e métodos que não podem ser instanciados diretamente. Este recurso é essencial para a criação de uma hierarquia de classes, promovendo a reutilização de código e a definição de interfaces comuns.

## Documentação
Em TypeScript, a palavra-chave `abstract` é utilizada para declarar uma classe abstrata ou um método abstrato. Uma classe abstrata é uma classe que não pode ser instanciada diretamente, servindo como um modelo para outras classes. Métodos abstratos, por sua vez, são métodos que devem ser implementados em classes derivadas, obrigando subclasses a fornecerem sua própria implementação.

### Propósito
O uso de classes e métodos abstratos em TypeScript tem como objetivo:
- Fornecer uma estrutura base para outras classes.
- Garantir que certas funcionalidades sejam implementadas em subclasses.
- Promover a reutilização de código e a organização de projetos.

### Uso
Para declarar uma classe como abstrata, utilize a palavra-chave `abstract` antes da palavra `class`. Para métodos, a palavra-chave deve preceder a declaração do método.

```typescript
abstract class Animal {
    abstract emitirSom(): void; // Método abstrato

    mover(): void {
        console.log("O animal se move.");
    }
}

class Cachorro extends Animal {
    emitirSom(): void {
        console.log("Au Au");
    }
}

const meuCachorro = new Cachorro();
meuCachorro.emitirSom(); // Saída: Au Au
meuCachorro.mover();     // Saída: O animal se move.
```

## Exemplos
### Exemplo 1: Classe Abstrata
```typescript
abstract class Veiculo {
    abstract acelerar(): void;

    parar(): void {
        console.log("O veículo parou.");
    }
}

class Carro extends Veiculo {
    acelerar(): void {
        console.log("O carro está acelerando.");
    }
}

const meuCarro = new Carro();
meuCarro.acelerar(); // Saída: O carro está acelerando.
meuCarro.parar();    // Saída: O veículo parou.
```

### Exemplo 2: Múltiplas Subclasses
```typescript
abstract class Forma {
    abstract area(): number;
}

class Retangulo extends Forma {
    constructor(private largura: number, private altura: number) {
        super();
    }

    area(): number {
        return this.largura * this.altura;
    }
}

class Circulo extends Forma {
    constructor(private raio: number) {
        super();
    }

    area(): number {
        return Math.PI * this.raio * this.raio;
    }
}

const meuRetangulo = new Retangulo(5, 10);
const meuCirculo = new Circulo(3);
console.log(meuRetangulo.area()); // Saída: 50
console.log(meuCirculo.area());    // Saída: 28.27...
```

## Explicação
### Armadilhas Comuns
1. **Tentativa de Instanciar Classes Abstratas**: Classes marcadas como `abstract` não podem ser instanciadas diretamente. Ao tentar fazer isso, o TypeScript gerará um erro de compilação.
   
2. **Métodos Abstratos Não Implementados**: Se uma classe derivada não implementar todos os métodos abstratos da classe base, o TypeScript também gerará um erro. É importante garantir que todas as subclasses implementem os métodos exigidos.

3. **Uso de Construtores em Classes Abstratas**: Embora você possa definir construtores em classes abstratas, isso significa que as subclasses devem chamar o construtor da classe base usando `super()`.

### Notas Adicionais
- Classes abstratas podem conter tanto métodos abstratos quanto métodos concretos, permitindo que você forneça implementações padrão que podem ser sobrescritas.
- O conceito de classes abstratas se alinha bem com o conceito de interfaces, mas oferece mais flexibilidade ao permitir a definição de métodos com implementações.

## Resumo em Uma Linha
O `abstract` em TypeScript permite a criação de classes e métodos que servem como base para outras classes, garantindo a implementação de funcionalidades específicas nas subclasses.
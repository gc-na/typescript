<!--
Meta Description: # A Palavra-chave "super" no TypeScript: Entenda seu Uso e Funcionalidade ## Sinopse A palavra-chave `super` em TypeScript é utilizada dentro de class...
Meta Keywords: super, superclasse, métodos, construtor, typescript
-->

# A Palavra-chave "super" no TypeScript: Entenda seu Uso e Funcionalidade

## Sinopse
A palavra-chave `super` em TypeScript é utilizada dentro de classes para acessar métodos e propriedades da classe pai (superclasse), facilitando a herança e a reutilização de código.

## Documentação
A palavra-chave `super` é fundamental para a implementação de herança em TypeScript. Quando uma classe herda de outra, `super` permite que você chame o construtor da superclasse e acesse seus métodos e propriedades.

### Propósito
O principal propósito do uso de `super` é permitir que subclasses acessem e estendam funcionalidades de suas superclasses. Isso ajuda a manter o código modular e organizado.

### Uso
O `super` pode ser utilizado em dois contextos principais:

1. **Chamada ao Construtor da Superclasse**: Ao criar uma instância de uma subclasse, você pode chamar o construtor da superclasse utilizando `super()`.
  
2. **Acesso a Métodos e Propriedades**: Você pode chamar métodos da superclasse diretamente através de `super.nomeDoMetodo()`.

### Detalhes
- O `super` deve ser chamado antes de usar `this` em um construtor de subclasse.
- Apenas métodos e propriedades públicos ou protegidos da superclasse podem ser acessados pelo `super`.

## Exemplos

### Exemplo 1: Chamada ao Construtor da Superclasse
```typescript
class Animal {
    constructor(public nome: string) {}
    
    fazerSom() {
        console.log(`${this.nome} faz um som.`);
    }
}

class Cachorro extends Animal {
    constructor(nome: string) {
        super(nome); // Chamada ao construtor da superclasse
    }

    fazerSom() {
        super.fazerSom(); // Chama o método da superclasse
        console.log(`${this.nome} late.`);
    }
}

const meuCachorro = new Cachorro("Rex");
meuCachorro.fazerSom();
// Saída:
// Rex faz um som.
// Rex late.
```

### Exemplo 2: Acesso a Métodos
```typescript
class Veiculo {
    acelerar() {
        console.log("O veículo está acelerando.");
    }
}

class Carro extends Veiculo {
    acelerar() {
        super.acelerar(); // Chama o método da superclasse
        console.log("O carro está acelerando rapidamente.");
    }
}

const meuCarro = new Carro();
meuCarro.acelerar();
// Saída:
// O veículo está acelerando.
// O carro está acelerando rapidamente.
```

## Explicação
Ao usar `super`, é importante lembrar que a chamada ao construtor da superclasse deve ocorrer antes de qualquer referência a `this` na subclasse. Um erro comum é tentar acessar propriedades ou métodos da subclasse antes de chamar `super()`, o que resultará em um erro de referência.

Além disso, o `super` não pode ser usado fora de métodos de classe, o que significa que você não pode acessá-lo diretamente em variáveis ou fora do contexto de um método.

## Resumo em Uma Frase
A palavra-chave `super` no TypeScript é utilizada para acessar e chamar métodos e propriedades da superclasse em subclasses, facilitando a herança e a reutilização de código.
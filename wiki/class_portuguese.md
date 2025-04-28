<!--
Meta Description: # Classes em TypeScript: Compreendendo a Programação Orientada a Objetos ## Sinopse As classes em TypeScript oferecem uma maneira estruturada de criar...
Meta Keywords: typescript, tipo, classes, objetos, uma
-->

# Classes em TypeScript: Compreendendo a Programação Orientada a Objetos

## Sinopse
As classes em TypeScript oferecem uma maneira estruturada de criar objetos, permitindo a implementação da programação orientada a objetos (POO) com tipagem estática. Elas são uma extensão das classes do JavaScript, trazendo recursos adicionais, como modificadores de acesso e interfaces.

## Documentação
Classes são um dos pilares da programação orientada a objetos e em TypeScript, elas permitem que você defina novos tipos de objetos com propriedades e métodos. Uma classe é uma representação de um conceito ou objeto do mundo real e pode ser utilizada para criar instâncias.

### Propósito
O propósito das classes em TypeScript é facilitar a organização do código, promover a reutilização e fornecer uma estrutura clara. Elas ajudam os desenvolvedores a modelar dados e comportamentos de forma mais intuitiva.

### Uso
Para definir uma classe em TypeScript, você utiliza a palavra-chave `class`, seguida pelo nome da classe. Dentro da classe, você pode definir construtores, propriedades e métodos.

### Estrutura Básica
```typescript
class NomeDaClasse {
    // Propriedades
    propriedade1: tipo;
    propriedade2: tipo;

    // Construtor
    constructor(param1: tipo, param2: tipo) {
        this.propriedade1 = param1;
        this.propriedade2 = param2;
    }

    // Métodos
    metodoExemplo() {
        // lógica do método
    }
}
```

## Exemplos
### Exemplo Básico
```typescript
class Carro {
    modelo: string;
    ano: number;

    constructor(modelo: string, ano: number) {
        this.modelo = modelo;
        this.ano = ano;
    }

    mostrarDetalhes() {
        console.log(`Modelo: ${this.modelo}, Ano: ${this.ano}`);
    }
}

const meuCarro = new Carro("Fusca", 1980);
meuCarro.mostrarDetalhes(); // Saída: Modelo: Fusca, Ano: 1980
```

### Herança
```typescript
class Veiculo {
    tipo: string;

    constructor(tipo: string) {
        this.tipo = tipo;
    }
}

class Bicicleta extends Veiculo {
    cor: string;

    constructor(tipo: string, cor: string) {
        super(tipo);
        this.cor = cor;
    }

    mostrarCor() {
        console.log(`A bicicleta é de cor ${this.cor}`);
    }
}

const minhaBicicleta = new Bicicleta("Ciclismo", "vermelha");
minhaBicicleta.mostrarCor(); // Saída: A bicicleta é de cor vermelha
```

## Explicação
Ao trabalhar com classes em TypeScript, é importante estar ciente de alguns pontos:

- **Modificadores de Acesso**: Utilize `public`, `private` e `protected` para controlar o acesso às propriedades e métodos. O padrão é `public`, que permite acesso de qualquer parte do código.
  
- **Interface e Implementação**: Você pode implementar interfaces em classes, o que pode ser útil para garantir que a classe siga um contrato específico.

- **Construtores**: Os construtores são métodos especiais para inicializar objetos. Certifique-se de definir corretamente os parâmetros para evitar erros de inicialização.

- **Instâncias**: Ao criar instâncias, utilize a palavra-chave `new` para invocar o construtor da classe.

## Resumo em Uma Linha
Classes em TypeScript são uma ferramenta fundamental para implementar a programação orientada a objetos, permitindo a criação de objetos com propriedades e métodos de forma estruturada.
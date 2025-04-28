<!--
Meta Description: # Comando "get" em TypeScript: Entenda Como Usar Propriedades Acessíveis ## Sinopse O comando `get` no TypeScript é utilizado para definir um método c...
Meta Keywords: get, typescript, uma, propriedades, que
-->

# Comando "get" em TypeScript: Entenda Como Usar Propriedades Acessíveis

## Sinopse
O comando `get` no TypeScript é utilizado para definir um método como um acessador de propriedades, permitindo que você obtenha o valor de uma propriedade de maneira controlada e encapsulada.

## Documentação
O `get` é parte da sintaxe de classes em TypeScript e JavaScript, permitindo que você crie métodos que podem ser chamados como se fossem propriedades. Isso é especialmente útil em cenários onde você deseja realizar alguma lógica ou processamento antes de retornar o valor de uma propriedade.

### Propósito
O propósito do `get` é fornecer uma interface limpa e intuitiva para acessar propriedades de um objeto, facilitando o encapsulamento e a manutenção do código.

### Uso
Para usar o `get`, você deve defini-lo dentro de uma classe. A sintaxe básica é a seguinte:

```typescript
class NomeDaClasse {
    private _propriedade: string;

    constructor(valor: string) {
        this._propriedade = valor;
    }

    get propriedade(): string {
        return this._propriedade;
    }
}
```

Neste exemplo, a classe `NomeDaClasse` possui uma propriedade privada `_propriedade` e um acessador `get` que permite acesso ao seu valor.

## Exemplos

### Exemplo 1: Acessando uma Propriedade
```typescript
class Produto {
    private _preco: number;

    constructor(preco: number) {
        this._preco = preco;
    }

    get preco(): number {
        return this._preco;
    }
}

const produto = new Produto(29.99);
console.log(produto.preco); // Saída: 29.99
```

### Exemplo 2: Acessador com Lógica
```typescript
class Temperatura {
    private _celsius: number;

    constructor(celsius: number) {
        this._celsius = celsius;
    }

    get fahrenheit(): number {
        return this._celsius * 9 / 5 + 32;
    }
}

const temp = new Temperatura(0);
console.log(temp.fahrenheit); // Saída: 32
```

## Explicação
Embora o uso do `get` seja bastante intuitivo, existem alguns pontos a serem considerados:

- **Imutabilidade**: O `get` não deve ser utilizado para modificar o estado da classe. Ele deve ser usado apenas para retornar valores.
- **Performance**: Chamar um `get` pode envolver lógica adicional, o que pode impactar a performance em cenários onde o acesso é feito repetidamente.
- **Nomes de Acessadores**: O nome do acessador deve ser um nome de propriedade válida e não deve colidir com outros métodos ou propriedades da classe.

## Resumo em Uma Linha
O comando `get` em TypeScript permite definir métodos que acessam propriedades de forma controlada, promovendo encapsulamento e clareza no código.
<!--
Meta Description: # readonly em TypeScript: Entendendo a Imutabilidade de Propriedades ## Sinopse O modificador `readonly` em TypeScript é uma ferramenta poderosa que p...
Meta Keywords: readonly, propriedade, typescript, propriedades, uma
-->

# readonly em TypeScript: Entendendo a Imutabilidade de Propriedades

## Sinopse
O modificador `readonly` em TypeScript é uma ferramenta poderosa que permite definir propriedades de objetos como imutáveis, garantindo que uma vez atribuídas, não possam ser alteradas. Este recurso é útil para garantir a integridade dos dados e a segurança do tipo.

## Documentação
O `readonly` é um modificador que pode ser aplicado a propriedades de interfaces e classes em TypeScript. Ao declarar uma propriedade como `readonly`, você impede que ela seja reatribuída após a sua inicialização. Isso é especialmente útil em cenários onde você deseja garantir que certos valores não sejam alterados acidentalmente ao longo do tempo.

### Uso do `readonly`
Para usar o `readonly`, você deve declará-lo antes da propriedade em uma interface ou classe. A sintaxe é a seguinte:

```typescript
class Exemplo {
    readonly propriedade: string;

    constructor(valor: string) {
        this.propriedade = valor; // Atribuição é permitida no construtor
    }
}

const inst = new Exemplo("valor inicial");
console.log(inst.propriedade); // "valor inicial"
// inst.propriedade = "novo valor"; // Erro: Cannot assign to 'propriedade' because it is a read-only property
```

### Detalhes
- O `readonly` pode ser usado em propriedades de classes e interfaces.
- A única maneira de atribuir um valor a uma propriedade `readonly` é dentro do construtor da classe ou na declaração da propriedade.
- O `readonly` não impede a modificação de objetos aninhados. Por exemplo, se uma propriedade `readonly` for um objeto, você ainda pode alterar as propriedades desse objeto.

## Exemplos
Aqui estão alguns exemplos práticos do uso do `readonly`:

### Exemplo 1: Classe com Propriedade Readonly
```typescript
class Carro {
    readonly marca: string;

    constructor(marca: string) {
        this.marca = marca;
    }
}

const meuCarro = new Carro("Toyota");
console.log(meuCarro.marca); // "Toyota"
// meuCarro.marca = "Honda"; // Erro: Cannot assign to 'marca' because it is a read-only property
```

### Exemplo 2: Interface com Propriedade Readonly
```typescript
interface Usuario {
    readonly id: number;
    nome: string;
}

const usuario: Usuario = { id: 1, nome: "João" };
console.log(usuario.id); // 1
// usuario.id = 2; // Erro: Cannot assign to 'id' because it is a read-only property
```

### Exemplo 3: Objeto Aninhado
```typescript
interface Endereco {
    readonly cidade: string;
    estado: string;
}

const endereco: Endereco = { cidade: "São Paulo", estado: "SP" };
console.log(endereco.cidade); // "São Paulo"
// endereco.cidade = "Rio de Janeiro"; // Erro: Cannot assign to 'cidade' because it is a read-only property
endereco.estado = "RJ"; // Isso é permitido
```

## Explicação
Um erro comum ao usar `readonly` é pensar que ele impede todas as modificações em um objeto. Na verdade, ele apenas impede a reatribuição da própria propriedade. Se a propriedade é um objeto, você ainda pode alterar suas propriedades internas. Além disso, o uso excessivo de `readonly` pode levar a um design menos flexível, então deve ser utilizado com cautela.

## Resumo em uma Linha
O modificador `readonly` em TypeScript permite definir propriedades como imutáveis, evitando sua reatribuição após a inicialização.
<!--
Meta Description: # O Comando "new" em TypeScript: Criação de Instâncias de Objetos ## Sinopse O comando `new` em TypeScript é utilizado para criar instâncias de classe...
Meta Keywords: new, classe, typescript, com, uma
-->

# O Comando "new" em TypeScript: Criação de Instâncias de Objetos

## Sinopse
O comando `new` em TypeScript é utilizado para criar instâncias de classes, permitindo a inicialização de objetos com propriedades e métodos definidos em uma classe.

## Documentação
O operador `new` em TypeScript é uma parte fundamental da programação orientada a objetos. Ele permite que os desenvolvedores criem instâncias de classes definidas, utilizando um construtor que pode inicializar variáveis e executar lógica durante a criação do objeto.

### Propósito
O principal propósito do `new` é instanciar uma classe, proporcionando um novo objeto que pode utilizar as propriedades e métodos definidos na classe.

### Uso
Para usar o `new`, você deve ter uma classe definida. O uso básico do `new` é o seguinte:

```typescript
class NomeDaClasse {
    propriedade: string;

    constructor(propriedade: string) {
        this.propriedade = propriedade;
    }

    metodoExemplo() {
        console.log(`Propriedade: ${this.propriedade}`);
    }
}

const minhaInstancia = new NomeDaClasse("Exemplo");
minhaInstancia.metodoExemplo(); // Saída: Propriedade: Exemplo
```

### Detalhes
- O `new` é seguido pelo nome da classe e parênteses que podem conter argumentos para o construtor.
- Quando um objeto é criado com `new`, o JavaScript automaticamente chama o construtor da classe.
- Se o construtor não retornar um objeto, o `new` retorna o objeto recém-criado.

## Exemplos
### Exemplo Básico
```typescript
class Animal {
    nome: string;

    constructor(nome: string) {
        this.nome = nome;
    }

    fazerSom() {
        console.log(`${this.nome} faz um som.`);
    }
}

const cachorro = new Animal("Rex");
cachorro.fazerSom(); // Saída: Rex faz um som.
```

### Exemplo com Múltiplos Objetos
```typescript
class Carro {
    modelo: string;
    ano: number;

    constructor(modelo: string, ano: number) {
        this.modelo = modelo;
        this.ano = ano;
    }
}

const carro1 = new Carro("Fusca", 1970);
const carro2 = new Carro("Civic", 2020);
console.log(carro1.modelo, carro2.ano); // Saída: Fusca 2020
```

## Explicação
### Armadilhas Comuns
- **Esquecer de usar `new`:** Se você chamar um construtor de classe sem `new`, ele não retornará uma instância da classe, podendo causar erros.
  
```typescript
const erro = NomeDaClasse("Test"); // Isso não cria uma instância
```

- **Métodos estáticos:** Métodos estáticos não podem ser chamados em instâncias criadas com `new`, pois são acessíveis apenas na própria classe.

### Notas Adicionais
- O `new` pode ser utilizado com classes que estendem outras classes, permitindo a herança.
- É importante garantir que os tipos de argumentos passados ao construtor sejam compatíveis com as definições de tipos na classe.

## Resumo em Uma Linha
O comando `new` em TypeScript é utilizado para criar instâncias de classes, inicializando objetos com propriedades e métodos definidos nas classes.
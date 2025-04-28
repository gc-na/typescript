<!--
Meta Description: # Extends: Entendendo o Uso em TypeScript ## Sinopse O comando `extends` em TypeScript é usado para criar relacionamentos de herança entre interfaces ...
Meta Keywords: extends, nome, typescript, interface, tipos
-->

# Extends: Entendendo o Uso em TypeScript

## Sinopse
O comando `extends` em TypeScript é usado para criar relacionamentos de herança entre interfaces e classes, permitindo a reutilização de tipos e a construção de hierarquias de tipos mais complexas.

## Documentação
Em TypeScript, o `extends` é uma palavra-chave que serve para indicar que um tipo ou interface herda propriedades e métodos de outro tipo ou interface. Essa funcionalidade é fundamental para criar tipagens mais robustas e reutilizáveis.

### Uso
1. **Extensão de Interfaces**: Quando uma interface é estendida, ela herda as propriedades de outra interface, podendo adicionar novas propriedades ou sobrepor as existentes.
   
   ```typescript
   interface Animal {
       nome: string;
       idade: number;
   }

   interface Cachorro extends Animal {
       raça: string;
   }
   ```

2. **Extensão de Classes**: Classes também podem usar `extends` para herdar de outras classes, permitindo a reutilização de código e uma estrutura mais organizada.

   ```typescript
   class Animal {
       nome: string;
       constructor(nome: string) {
           this.nome = nome;
       }
   }

   class Cachorro extends Animal {
       latir() {
           console.log('Au Au!');
       }
   }
   ```

3. **Extensão de Tipos Genéricos**: O `extends` também é utilizado em tipos genéricos para restringir os tipos que podem ser utilizados.

   ```typescript
   function imprimir<T extends Animal>(animal: T): void {
       console.log(animal.nome);
   }
   ```

## Exemplos
### Exemplo 1: Extensão de Interface

```typescript
interface Pessoa {
    nome: string;
    idade: number;
}

interface Funcionario extends Pessoa {
    cargo: string;
}

const funcionario: Funcionario = {
    nome: 'João',
    idade: 30,
    cargo: 'Desenvolvedor'
};
```

### Exemplo 2: Extensão de Classe

```typescript
class Veiculo {
    rodas: number;
    constructor(rodas: number) {
        this.rodas = rodas;
    }
}

class Carro extends Veiculo {
    constructor() {
        super(4);
    }
}

const carro = new Carro();
console.log(carro.rodas); // 4
```

### Exemplo 3: Tipo Genérico com Extensão

```typescript
function exibirNome<T extends { nome: string }>(obj: T): void {
    console.log(obj.nome);
}

exibirNome({ nome: 'Maria' });
```

## Explicação
Ao usar `extends`, é importante lembrar que:
- A herança pode criar complexidades nas estruturas de tipos, então deve ser usada com cautela.
- A ordem de extensão é importante: se uma subinterface ou subclasse não implementar ou sobrepor as propriedades exigidas pela superinterface ou superclasse, erros de compilação ocorrerão.
- O `extends` pode ser utilizado em tipos genéricos para limitar os tipos aceitos, mas isso pode limitar a flexibilidade se não for gerenciado corretamente.

## Resumo em Uma Linha
O `extends` em TypeScript permite a herança de propriedades e métodos entre interfaces e classes, promovendo a reutilização e a organização do código.
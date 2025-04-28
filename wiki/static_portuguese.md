<!--
Meta Description: # O que é "static" no TypeScript: Entenda sua Utilização e Aplicações ## Sinopse O modificador `static` em TypeScript é utilizado para definir proprie...
Meta Keywords: static, classe, que, membros, typescript
-->

# O que é "static" no TypeScript: Entenda sua Utilização e Aplicações

## Sinopse
O modificador `static` em TypeScript é utilizado para definir propriedades e métodos que pertencem à classe, e não a instâncias individuais da classe. Isso permite que você acesse essas propriedades e métodos sem a necessidade de instanciar a classe.

## Documentação
O modificador `static` é uma funcionalidade fundamental em TypeScript que permite a definição de membros de classe que são acessíveis diretamente a partir da classe, sem a necessidade de criar uma instância. Isso é especialmente útil para constantes, utilitários, ou métodos que não dependem de dados de instância.

### Propósito
A principal finalidade do `static` é fornecer um meio de encapsular lógica ou dados que são relevantes para a classe em si, ao invés de serem específicos a uma instância.

### Uso
Para declarar um membro `static`, utilize a palavra-chave `static` antes da definição do membro dentro da classe. Veja o exemplo abaixo:

```typescript
class Exemplo {
    static contador: number = 0;

    static incrementarContador() {
        this.contador++;
    }

    static obterContador(): number {
        return this.contador;
    }
}
```

Neste exemplo, `contador`, `incrementarContador`, e `obterContador` são membros estáticos da classe `Exemplo`, permitindo que sejam acessados diretamente pela classe sem instâncias.

## Exemplos
### Exemplo 1: Acesso a Membros Estáticos

```typescript
class Matematica {
    static PI: number = 3.14;

    static calcularAreaCirculo(raio: number): number {
        return this.PI * raio * raio;
    }
}

console.log(Matematica.PI); // Saída: 3.14
console.log(Matematica.calcularAreaCirculo(5)); // Saída: 78.5
```

### Exemplo 2: Contador de Instâncias

```typescript
class Usuario {
    static totalUsuarios: number = 0;

    constructor() {
        Usuario.totalUsuarios++;
    }

    static obterTotalUsuarios(): number {
        return Usuario.totalUsuarios;
    }
}

const usuario1 = new Usuario();
const usuario2 = new Usuario();

console.log(Usuario.obterTotalUsuarios()); // Saída: 2
```

## Explicação
### Armadilhas Comuns
1. **Acesso a Membros de Instância:** Membros estáticos não podem acessar diretamente membros de instância. Isso pode causar confusão se você tentar referenciar `this` dentro de um método estático.
   
2. **Herança:** Membros estáticos não são herdados da mesma maneira que membros de instância. Se uma subclasse define um membro estático com o mesmo nome de um membro estático da superclasse, você não terá acesso ao membro da superclasse a partir da subclasse.

### Notas Adicionais
- O uso de `static` pode ser uma boa prática para métodos utilitários, evitando a necessidade de instanciar objetos apenas para chamar funções.
- Ao usar membros estáticos, é importante gerenciar o estado compartilhado adequadamente, pois ele pode ser alterado por qualquer instância da classe.

## Resumo em Uma Linha
O modificador `static` em TypeScript permite definir propriedades e métodos que pertencem à classe em vez de a instâncias, facilitando o acesso e a organização do código.
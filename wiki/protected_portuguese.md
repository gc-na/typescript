<!--
Meta Description: # Modificador "protected" no TypeScript: Entendendo Acesso e Herança ## Sinopse O modificador de acesso "protected" no TypeScript permite que as propr...
Meta Keywords: protected, acesso, que, classe, typescript
-->

# Modificador "protected" no TypeScript: Entendendo Acesso e Herança

## Sinopse
O modificador de acesso "protected" no TypeScript permite que as propriedades e métodos de uma classe sejam acessíveis apenas dentro da própria classe e nas classes que a estendem. Isso proporciona um nível de encapsulamento que é útil para a herança.

## Documentação
O modificador "protected" é um dos três modificadores de acesso em TypeScript, juntamente com "public" e "private". Ele é utilizado para proteger membros (variáveis e métodos) de uma classe, permitindo que sejam acessados apenas por subclasses e pela própria classe.

### Propósito
O uso de "protected" é essencial quando se deseja restringir o acesso a certas funcionalidades de uma classe, mas ainda assim permitir que classes derivadas possam interagir com essas propriedades ou métodos.

### Uso
Para declarar um membro como "protected", basta preceder sua declaração com a palavra-chave `protected`. Exemplo:

```typescript
class Base {
    protected propriedade: string;

    constructor(prop: string) {
        this.propriedade = prop;
    }

    protected metodoProtegido() {
        console.log(`Método protegido: ${this.propriedade}`);
    }
}

class Derivada extends Base {
    mostrar() {
        console.log(`Propriedade: ${this.propriedade}`); // Acesso permitido
        this.metodoProtegido(); // Acesso permitido
    }
}

const obj = new Derivada("Exemplo");
obj.mostrar(); // Saída: Propriedade: Exemplo
               //         Método protegido: Exemplo
```

## Exemplos
### Exemplo 1: Acesso a Propriedades Protegidas
```typescript
class Animal {
    protected nome: string;

    constructor(nome: string) {
        this.nome = nome;
    }
}

class Cachorro extends Animal {
    mostrarNome() {
        console.log(`Nome do cachorro: ${this.nome}`); // Acesso permitido
    }
}

const meuCachorro = new Cachorro("Rex");
meuCachorro.mostrarNome(); // Saída: Nome do cachorro: Rex
```

### Exemplo 2: Tentativa de Acesso Externo
```typescript
class Carro {
    protected modelo: string;

    constructor(modelo: string) {
        this.modelo = modelo;
    }
}

const meuCarro = new Carro("Fusca");
// console.log(meuCarro.modelo); // Erro: 'modelo' é protegido e não pode ser acessado fora da classe
```

## Explicação
Um dos principais erros que os desenvolvedores podem cometer ao usar "protected" é confundir o nível de acesso. O acesso "protected" não permite que as propriedades sejam acessadas fora da classe e suas subclasses, o que pode levar a tentativas de acesso indevidas, resultando em erros de compilação.

Além disso, ao herdar de uma classe, mesmo que o membro seja "protected", ele ainda pode ser utilizado livremente nas subclasses, permitindo um design mais flexível e organizado. Contudo, é importante lembrar que, ao usar "protected", a implementação de subclasses deve ser cuidadosamente planejada para evitar dependências excessivas.

## Resumo em Uma Linha
O modificador "protected" no TypeScript restringe o acesso a propriedades e métodos a subclasses e à própria classe, oferecendo um controle eficaz sobre a herança e o encapsulamento.
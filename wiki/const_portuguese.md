<!--
Meta Description: # O Comando `const` em TypeScript: Tudo o que Você Precisa Saber ## Sinopse O comando `const` em TypeScript é utilizado para declarar variáveis cujo v...
Meta Keywords: const, que, não, ser, typescript
-->

# O Comando `const` em TypeScript: Tudo o que Você Precisa Saber

## Sinopse
O comando `const` em TypeScript é utilizado para declarar variáveis cujo valor não pode ser reatribuído, garantindo assim imutabilidade. Essa característica torna o `const` uma escolha preferida para variáveis que não devem ser alteradas após a sua inicialização.

## Documentação
O `const` é uma palavra-chave que foi introduzida no ECMAScript 2015 (ES6) e é amplamente utilizada em TypeScript. Sua principal função é declarar constantes — variáveis cujo valor não pode ser modificado ao longo do tempo. Isso não significa que o valor associado a uma constante não possa ser mutável; por exemplo, se a constante for um objeto ou um array, suas propriedades ou elementos podem ser alterados.

### Propósito
O uso do `const` ajuda a evitar erros de programação relacionados à reatribuição acidental de valores. Ao declarar uma variável como `const`, você está explicitamente informando ao compilador e a outros desenvolvedores que o valor não deve ser alterado.

### Uso
A sintaxe básica do `const` é muito semelhante à de `let` e `var`, mas com a diferença crucial de que não permite reatribuição:

```typescript
const nome: string = "João";
```

Tentar reatribuir a `nome` resultará em um erro de compilação.

## Exemplos
### Exemplo 1: Declaração Simples
```typescript
const cidade: string = "São Paulo";
console.log(cidade); // Saída: São Paulo
```

### Exemplo 2: Constantes de Objetos
```typescript
const pessoa = {
    nome: "Maria",
    idade: 30
};

console.log(pessoa.nome); // Saída: Maria
pessoa.idade = 31; // Isso é permitido, pois apenas a referência da constante não pode ser alterada.
console.log(pessoa.idade); // Saída: 31
```

### Exemplo 3: Arrays com `const`
```typescript
const frutas: string[] = ["maçã", "banana", "laranja"];
frutas.push("uva"); // Isso é permitido
console.log(frutas); // Saída: ["maçã", "banana", "laranja", "uva"]
```

## Explicação
Um dos principais erros que desenvolvedores iniciantes cometem ao usar `const` é confundir a imutabilidade da referência com a imutabilidade do valor. Embora a referência não possa ser alterada, o conteúdo de objetos e arrays pode ser modificado. Outro ponto importante é que `const` deve ser inicializado no momento da declaração, caso contrário, resultará em erro.

```typescript
const x; // Erro: 'const' declarations must be initialized.
```

Além disso, `const` é bloqueado em escopo, o que significa que uma variável `const` declarada dentro de um bloco (como um loop ou uma função) não está acessível fora desse bloco.

## Resumo em Uma Linha
O `const` em TypeScript é usado para declarar variáveis imutáveis, proporcionando segurança e clareza no código.
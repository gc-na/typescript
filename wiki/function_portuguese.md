<!--
Meta Description: # Funções em TypeScript: Como Utilizá-las Eficazmente ## Sinopse As funções em TypeScript são blocos de código reutilizáveis que realizam uma tarefa e...
Meta Keywords: typescript, funções, number, que, função
-->

# Funções em TypeScript: Como Utilizá-las Eficazmente

## Sinopse
As funções em TypeScript são blocos de código reutilizáveis que realizam uma tarefa específica. Elas permitem a criação de programas mais organizados e eficientes, com suporte para tipos estáticos que ajudam na detecção de erros em tempo de compilação.

## Documentação
As funções são um dos pilares da programação em TypeScript. Elas permitem que você encapsule lógica e a reutilize em diferentes partes do seu código. A sintaxe básica para declarar uma função é a seguinte:

```typescript
function nomeDaFuncao(param1: Tipo1, param2: Tipo2): TipoDeRetorno {
    // corpo da função
}
```

### Propósito
O principal objetivo das funções é promover a reutilização de código e melhorar a legibilidade e a manutenção. Com TypeScript, você pode especificar tipos para os parâmetros e o valor de retorno, o que ajuda a evitar erros comuns.

### Uso
Para utilizar uma função, você deve declará-la e, em seguida, chamá-la em seu código. Aqui está um exemplo básico:

```typescript
function soma(a: number, b: number): number {
    return a + b;
}

const resultado = soma(5, 10);
console.log(resultado); // Saída: 15
```

### Detalhes
- **Funções Anônimas**: Também é possível declarar funções sem nome, geralmente usadas em expressões de função ou como argumentos para outras funções.

```typescript
const multiplicar = function(a: number, b: number): number {
    return a * b;
};
```

- **Funções Arrow**: TypeScript também suporta funções de seta, que são uma sintaxe mais concisa.

```typescript
const dividir = (a: number, b: number): number => a / b;
```

- **Parâmetros Opcionais**: Você pode definir parâmetros como opcionais usando o operador `?`.

```typescript
function saudacao(nome: string, saudacao: string = "Olá"): string {
    return `${saudacao}, ${nome}!`;
}

console.log(saudacao("Maria")); // Saída: Olá, Maria!
```

## Exemplos
1. **Função Simples**:
    ```typescript
    function subtrair(a: number, b: number): number {
        return a - b;
    }

    console.log(subtrair(10, 4)); // Saída: 6
    ```

2. **Função com Parâmetro Opcionais**:
    ```typescript
    function cumprimentar(nome: string, saudacao: string = "Oi"): string {
        return `${saudacao}, ${nome}!`;
    }

    console.log(cumprimentar("João")); // Saída: Oi, João!
    ```

3. **Função Arrow**:
    ```typescript
    const quadrado = (n: number): number => n * n;

    console.log(quadrado(4)); // Saída: 16
    ```

## Explicação
Um erro comum ao trabalhar com funções em TypeScript é esquecer de declarar os tipos dos parâmetros ou do valor de retorno. Isso pode levar a comportamentos inesperados e à dificuldade em identificar o que está errado no código. Além disso, ao utilizar funções anônimas ou funções de seta, certifique-se de entender como o `this` se comporta, pois pode ser diferente do que você espera.

Outra armadilha é não considerar o uso de parâmetros opcionais e rest parameters. Ao definir funções que podem receber diferentes números de argumentos, você deve estar ciente de como TypeScript irá inferir os tipos e como isso pode impactar a lógica da sua função.

## Resumo em Uma Linha
As funções em TypeScript são blocos de código reutilizáveis que permitem encapsular lógica, com suporte a tipos estáticos para evitar erros em tempo de compilação.
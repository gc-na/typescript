<!--
Meta Description: # Estrutura de Controle "for" em TypeScript: Guia Completo ## Sinopse A estrutura de controle `for` em TypeScript permite a iteração sobre sequências ...
Meta Keywords: condição, typescript, uma, controle, loop
-->

# Estrutura de Controle "for" em TypeScript: Guia Completo

## Sinopse
A estrutura de controle `for` em TypeScript permite a iteração sobre sequências de dados, como arrays e objetos, facilitando a execução de um bloco de código repetidamente com base em uma condição específica.

## Documentação
A estrutura `for` é uma das formas mais comuns de controle de fluxo em TypeScript, derivada do JavaScript. Seu propósito é executar um bloco de código várias vezes enquanto uma condição é verdadeira. A sintaxe básica do `for` é:

```typescript
for (inicialização; condição; incremento) {
    // bloco de código a ser executado
}
```

### Componentes da Estrutura `for`:
1. **Inicialização**: É onde você define e inicializa uma variável de controle, que geralmente é um contador.
2. **Condição**: Uma expressão booleana que é avaliada antes de cada iteração. Enquanto essa condição for verdadeira, o loop continuará a ser executado.
3. **Incremento**: Uma expressão que é executada após cada iteração do loop, geralmente usada para atualizar a variável de controle.

### Exemplo Básico:
```typescript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```
Neste exemplo, o loop imprimirá os números de 0 a 4 no console.

## Exemplos
### Exemplo 1: Iterando sobre um Array
```typescript
const frutas: string[] = ["maçã", "banana", "laranja"];
for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
}
```
Esse código percorre o array `frutas` e imprime cada elemento.

### Exemplo 2: Usando um Loop `for` com Condição
```typescript
for (let i = 0; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(i + " é par");
    }
}
```
Aqui, o código imprime todos os números pares de 0 a 10.

## Explicação
### Armadilhas Comuns
- **Erro de Exclusão**: Certifique-se de que a condição do loop eventualmente se tornará falsa. Caso contrário, você pode acabar com um loop infinito.
- **Escopo de Variável**: Use `let` para garantir que a variável de controle tenha escopo de bloco, evitando comportamentos inesperados ao usar `var`.
- **Condição Errada**: Verifique se a condição do loop está correta para evitar iterações desnecessárias ou faltantes.

### Notas Adicionais
- O `for` é ideal para iterações onde você precisa de acesso ao índice, ao contrário de outras estruturas como `forEach`.
- Para estruturas de dados mais complexas, considere usar `for...of` ou `for...in`, que são mais adequados para iterar sobre objetos e arrays.

## Resumo em Uma Linha
A estrutura de controle `for` em TypeScript permite a iteração eficiente sobre sequências de dados, com uma sintaxe clara e flexível.
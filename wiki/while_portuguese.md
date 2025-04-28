<!--
Meta Description: # Laço While em TypeScript: Estruturas de Repetição Eficientes ## Sinopse O laço `while` em TypeScript permite a execução repetida de um bloco de códi...
Meta Keywords: condição, que, while, contador, typescript
-->

# Laço While em TypeScript: Estruturas de Repetição Eficientes

## Sinopse
O laço `while` em TypeScript permite a execução repetida de um bloco de código enquanto uma condição especificada for verdadeira. Essa estrutura é fundamental para a construção de algoritmos que requerem iterações dinâmicas.

## Documentação
O `while` é uma das estruturas de repetição disponíveis em TypeScript, permitindo que um bloco de código seja executado continuamente enquanto a condição especificada for avaliada como verdadeira. A sintaxe básica do `while` é a seguinte:

```typescript
while (condição) {
    // bloco de código a ser executado
}
```

### Propósito
O objetivo principal do laço `while` é executar um bloco de código repetidamente sem a necessidade de saber, previamente, quantas iterações serão necessárias. É útil em situações onde o número de repetições depende de uma condição que pode mudar durante a execução do programa.

### Uso
Para utilizar o `while`, é necessário definir uma condição que será verificada antes de cada iteração. O laço continuará a ser executado até que essa condição retorne `false`. É importante garantir que a condição eventualmente se torne falsa, caso contrário, o laço resultará em um loop infinito.

## Exemplos

### Exemplo Básico
```typescript
let contador: number = 0;

while (contador < 5) {
    console.log(`Contador: ${contador}`);
    contador++;
}
```
Saída:
```
Contador: 0
Contador: 1
Contador: 2
Contador: 3
Contador: 4
```

### Exemplo com Entrada do Usuário
```typescript
let senha: string = '';
const senhaCorreta: string = '1234';

while (senha !== senhaCorreta) {
    senha = prompt('Digite a senha:') || '';
    console.log('Senha incorreta, tente novamente.');
}

console.log('Senha correta!');
```

## Explicação
Um dos principais cuidados ao utilizar o `while` é garantir que a condição possa ser satisfeita em algum momento, evitando loops infinitos. Além disso, é importante lembrar que a condição é avaliada antes da execução do bloco de código, o que significa que se a condição for falsa na primeira verificação, o bloco de código nunca será executado.

### Armadilhas Comuns
- **Loop Infinito**: Certifique-se de que a condição eventualmente se tornará falsa. Um erro comum é esquecer de modificar a variável que está sendo testada na condição.
- **Valor Inicial da Condição**: Verifique os valores iniciais das variáveis envolvidas na condição para evitar execuções indesejadas ou loops que não terminam.
- **Uso de `prompt` em Ambientes Não Suportados**: O uso do `prompt` pode não funcionar em ambientes onde a interface do usuário não está disponível, como em ambiente de servidor.

## Resumo em Uma Linha
O laço `while` em TypeScript permite executar um bloco de código repetidamente enquanto uma condição especificada for verdadeira, sendo essencial para iterações dinâmicas.
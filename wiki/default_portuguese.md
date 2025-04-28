<!--
Meta Description: # O que é "default" em TypeScript: Entendendo a Exportação Padrão ## Sinopse Neste artigo, abordaremos o conceito de "default" em TypeScript, que se r...
Meta Keywords: padrão, uma, exportação, que, typescript
-->

# O que é "default" em TypeScript: Entendendo a Exportação Padrão

## Sinopse
Neste artigo, abordaremos o conceito de "default" em TypeScript, que se refere à exportação padrão de módulos. Essa característica permite que um módulo exporte uma única entidade como padrão, facilitando a importação em outros arquivos.

## Documentação
### O que é a Exportação Padrão?
A exportação padrão em TypeScript permite que você defina uma única entidade que pode ser exportada a partir de um módulo. Isso é útil quando você deseja exportar uma função, classe ou objeto que representa a principal funcionalidade de um módulo.

### Como Usar
Para exportar uma entidade como padrão, você pode utilizar a palavra-chave `export default` seguida da entidade que deseja exportar. Veja como funciona na prática:

```typescript
// arquivo: minhaClasse.ts
class MinhaClasse {
    constructor() {
        console.log("Instância da MinhaClasse criada!");
    }
}

export default MinhaClasse;
```

Para importar essa classe em outro arquivo, você faria da seguinte maneira:

```typescript
// arquivo: app.ts
import MinhaClasse from './minhaClasse';

const instancia = new MinhaClasse();
```

### Detalhes Adicionais
- Um módulo pode ter apenas uma exportação padrão.
- Ao importar uma exportação padrão, você não precisa usar chaves `{}`.
- A exportação padrão pode ser uma expressão, função ou classe.

## Exemplos
### Exemplo 1: Exportação de uma Função
```typescript
// arquivo: minhaFuncao.ts
function minhaFuncao() {
    console.log("Essa é uma função exportada como padrão!");
}

export default minhaFuncao;
```

```typescript
// arquivo: app.ts
import minhaFuncao from './minhaFuncao';

minhaFuncao(); // Saída: Essa é uma função exportada como padrão!
```

### Exemplo 2: Exportação de um Objeto
```typescript
// arquivo: meuObjeto.ts
const meuObjeto = {
    nome: "Objeto Padrão",
    valor: 42
};

export default meuObjeto;
```

```typescript
// arquivo: app.ts
import meuObjeto from './meuObjeto';

console.log(meuObjeto.nome); // Saída: Objeto Padrão
```

## Explicação
### Armadilhas Comuns
- **Tentativa de Múltiplas Exportações Padrão:** Lembre-se de que um módulo só pode ter uma exportação padrão. Tentar declarar mais de uma resultará em um erro de compilação.
- **Importação Sem Chaves:** Ao importar uma exportação padrão, não utilize chaves `{}`. Isso pode causar confusão e resultar em erros.
- **Nome da Importação:** Você pode nomear a importação de qualquer maneira. O nome não precisa coincidir com o nome da entidade exportada.

## Resumo em Uma Frase
A exportação padrão em TypeScript simplifica a forma de exportar e importar módulos, permitindo que você defina uma única entidade como a principal funcionalidade de um arquivo.
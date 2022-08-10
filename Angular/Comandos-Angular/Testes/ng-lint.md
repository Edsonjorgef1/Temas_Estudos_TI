## ng lint

De forma geral, o Lint é uma ferramenta bastante útil para checar se seu código possui algum erro em potencial ou se segue os padrões e convenções da linguagem em uso. O TypeScript também possui sua versão do lint, que é chamada de tslint. Para rodar o tslint em seu projeto, primeiro é necessário ter o arquivo tslint.json, que já é criado por padrão ao executar o comando ng new e que contém as regras de checagem que o tslint utilizará para verificar seu código. Assim, basta executar o comando ng lint dentro da pasta do projeto.

Exemplo de uso:

```js
ng lint
```

## Parâmetros:

Para esse comando podemos especificar os parâmetros apresentados na tabela abaixo

- --fix

Descrição: Corrige os erros encontrados no código. Valor padrão: false.

--type-check

Descrição: Habilita a checagem de tipo. Valor padrão: false.

- --force

Descrição: O Lint considera que o código está correto, mesmo que sejam encontrados erros. Valor padrão: false.

- --format <string>

Descrição: Define como o resultado da análise do lint deve ser exibido: json, prose, etc. Valor padrão: prose.

## ng generate class

Além de artefatos do Angular, o Angular CLI também pode criar artefatos que são puramente TypeScript, como classes, enums e interfaces. Por exemplo, o comando ng generate class cria um arquivo com o nome informado e que será colocado dentro da pasta /src/app/. Dentro desse arquivo haverá uma classe básica escrita em Typescript, cujo o nome é o mesmo do arquivo.

Exemplo de uso:

```js
ng generate class produto
```

A execução desse comando criará o arquivo /src/app/produto.ts contendo uma classe chamada Produto.

### Parâmetros

Para esse comando, podemos especificar os parâmetros apresentados na Tabela.


- --spec

Descrição: Define se deve ser gerado o arquivo de testes (arquivo com extensão .spec.ts).

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações a classe deve ser criada. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
## ng generate enum

De forma similar ao comando para criar uma classe, também é possível utilizar o Angular CLI para gerar um enum em TypeScript. A única diferença é a mudança da palavra class para enum, conforme exemplo abaixo. Nesse caso, também teremos a criação de um novo arquivo em /src/app, que conterá a declaração de um enum.

Exemplo de uso:

```js
ng generate enum situacaoProduto
```
O comando do exemplo cria o arquivo /src/app/status-produto.ts contendo um enum chamado SituacaoProduto.

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o enum deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
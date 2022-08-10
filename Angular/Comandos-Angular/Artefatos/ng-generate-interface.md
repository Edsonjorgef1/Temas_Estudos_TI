## ng generate interface

A interface é outro artefato do TypeScript que pode ser criado com o Angular CLI. A regra é similar ao que foi feito para gerar classes e enums.

Exemplo de uso:

```js
ng generate interface IProdutoService
```

A execução desse comando criará um arquivo /src/app/iproduto-service.ts contendo a declaração de uma interface com nome IProdutoService.

### Parâmetros

Para esse comando, podemos especificar apenas o parâmetro --app <string>.

- --app <string>

Descriçãp: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações a interface deve ser criada. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
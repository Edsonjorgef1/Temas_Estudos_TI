## ng generate module

Os módulos são úteis para agregar funcionalidades em comum dentro de uma aplicação. Por exemplo, é possível criar um módulo para conter todas as funcionalidades da área de administração de sua aplicação usando o comando ng generate module, conforme exemplo abaixo.

Exemplo de uso:

```js
ng generate module admin
```

O resultado dessa operação é a criação de um diretório chamado admin e um arquivo, dentro dessa pasta, chamado admin.module.ts.


### Parâmetros

- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do módulo serão colocados. Valor padrão: true.

- --spec

Descrição: Define se deve ser gerado o arquivo de testes (arquivo com extensão .spec.ts).

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o módulo deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.

- --routing

Descrição: Cria um módulo onde serão definidas as rotas da aplicação. Dessa forma, dentro de um módulo teremos um outro módulo responsável pela definição das rotas relacionadas. Valor padrão: falso.
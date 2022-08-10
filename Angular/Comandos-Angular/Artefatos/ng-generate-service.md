## ng generate service

Os serviços são úteis para separar toda a lógica que não está relacionada à visão em classes separadas como, por exemplo, o acesso a uma API para obter dados para exibição na tela. Para criar um serviço usando o CLI, basta executar o comando ng generate service.

Exemplo de uso:

```js
ng generate service api
```
O resultado disso será a criação do arquivo /src/app/api.service.ts contendo a classe que representa o serviço e o arquivo /src/app/api.service.spec.ts, que contém os testes dessa classe.

### Parâmetros:

- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do módulo serão colocados. Valor padrão: true.

- --spec

Descrição: Define se deve ser gerado o arquivo de testes (arquivo com extensão .spec.ts).

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o módulo deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.

- --module <string>

Descrição: Define para qual módulo da aplicação este guard deve ser criado.
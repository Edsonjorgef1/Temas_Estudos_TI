## ng generate pipe

Muito utilizado em aplicações Angular, um pipe é responsável por transformar um valor de entrada em outro valor desejado. Por exemplo, ele pode receber uma data e formatá-la para o padrão brasileiro. A criação de pipes também é bem simples usando o CLI, conforme pode ser visto no exemplo abaixo.

Exemplo de uso:

```js
ng generate pipe date
```

O resultado desse comando será a criação de dois arquivos: /src/app/date.pipe.ts e /src/app/date.pipe.spec.ts. O primeiro contém a declaração da classe que representa o pipe, enquanto o segundo contém os testes.

Além disso, o arquivo /src/app/app.module.ts é atualizado para informar ao Angular a existência desse novo artefato.

### Parâmetros:

Para esse comando, podemos especificar os parâmetros apresentados na Tabela.



- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do módulo serão colocados. Valor padrão: true.

- --spec

Descrição: Define se deve ser gerado o arquivo de testes (arquivo com extensão .spec.ts).

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o módulo deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.

- --module <string>

Descrição: Define para qual módulo da aplicação este guard deve ser criado.

- --skip-import

Descrição: Define se o novo pipe deve ser automaticamente importado no módulo para o qual ele foi criado. Caso contrário, será necessário importá-lo manualmente.

- --export

Descrição: Define se o pipe é visível para outros módulos da mesma aplicação.
## ng generate directive

O comando ng generate directive é utilizado para criar uma nova diretiva. Ao executá-lo, dois novos arquivos serão criados dentro da pasta /src/app: o arquivo contendo a classe que representa a diretiva e outro contendo a classe de testes para a diretiva.

Esse comando também força a atualização do arquivo app.module.ts, para informar ao Angular a existência da nova diretiva.

```js
ng generate directive upperCase
```

Parâmetros:

Para esse comando, podemos especificar os parâmetros apresentados na Tabela

Parâmetros

Descrição

- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do componente serão colocados. Valor padrão: true.

- --inline-style

Descrição: Colocar os estilos (CSS) inline, dentro do próprio arquivo ts, ao invés de criar um arquivo em separado para eles. Valor padrão: false.

- --inline-template

Descrição: Colocar os templates inline, dentro do próprio arquivo ts, ao invés de criar um arquivo em separado. Valor padrão: false.

- --prefix <string>

Descrição: Define o prefixo do seletor da diretiva. Caso não informado, é utilizado o prefixo padrão da aplicação (valor "app" ou outro definido a partir do parâmetro prefix do comando ng new).

- --spec

Descrição: Define se o arquivo de teste com extensão .spec.ts deve ser criado. Valor padrão: true.

- --view-encapsulation <string>

Descrição: Informa a estratégia de encapsulamento da View, que é relacionada ao uso do Shadow DOM (HTML 5) por sua aplicação de forma nativa ou emulada.

- --change-detection <string>

Descrição: Define a estratégia de detecção de mudanças que a diretiva deve usar.

- --module <string>

Descrição: Define para qual módulo da aplicação esta diretiva deve ser criada.

- --export

Descrição: Define se a diretiva é visível para outros módulos da mesma aplicação.

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações a diretiva deve ser criada. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
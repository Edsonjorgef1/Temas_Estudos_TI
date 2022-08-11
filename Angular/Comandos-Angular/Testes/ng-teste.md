## ng teste

Muitos comandos do Angular CLI geram um arquivo com a extensão .spec.ts. Esses são os arquivos de teste de seu projeto e você pode usar o CLI para executar todos eles e verificar se algum bug foi criado.

Exemplo de uso:

```js
ng teste
```

## Parâmetros:

Para esse comando podemos especificar os parâmetros apresentados na Tabela.


- --watch

Descrição: Recria um build que está sendo testado quando encontrar mudanças no código.

- --code-coverage

Descrição: Define se deve criar o relatório de cobertura dentro do diretório coverage/. Valor padrão: false.

- --config <string>

Descrição: Informar o arquivo de configuração. O padrão é o arquivo do Karma definido no angular-cli.json.

- --single-run

Descrição: Executar os testes apenas uma vez.

- --progress

Descrição: Exibir o progresso no console.

- --browsers <string>

Descrição: Informar quais navegadores serão usados para realizar os testes.

- --colors

Descrição: Habilita o uso de cores no resultado dos testes.

- --log-level <string>

Descrição: Definir o nível de log.

- --port <string>

Descrição: Definir a porta que deve ser usada no servidor.

- --reporters <string>

Descrição: Informar a lista de reporters que devem ser usados nos testes.

- --sourcemaps

Descrição: Criar arquivos de source map (.map).

- --poll <number>

Descrição: Define o período, em milissegundos, que será usado para verificar se ocorreram mudanças no projeto.

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o teste deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
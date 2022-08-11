## ng e2e
O termo e2e em JavaScript é utilizado para referenciar os testes do tipo End to End. Na estrutura de pastas fornecida pelo Angular CLI, esses testes encontram-se no diretório /e2e e é possível executá-los utilizando o comando do exemplo abaixo.

Exemplo de uso:

```js
ng e2e
```

## Parâmetros:

O comando ng e2e pode receber parâmetros, e os principais estão detalhados na Tabela.


- --target <string>

Descrição: Define qual tipo de build deve ser gerado: (development, production). Valor padrão: development.

- --environment

Descrição: Define qual dos ambientes definidos em /src/environments deve ser usado na geração do build.

- --aot

Descrição: Criar o build usando compilação AOT (Ahead of Time), ao invés de JIT (Just in Time). Esta opção melhora o desempenho, pois todos artefatos são previamente compilados para Javascript.

- --sourcemaps

Descrição: Criar arquivos de source map (arquivos com extensão .map).

- --base-href <string> *

Descrição: Altera a tag base-href no arquivo index.html para o valor informado.

- --deploy-url <string> *

Descrição: URL na qual a aplicação será implantada.

- --verbose

Descrição: Exibe mais informações sobre a execução do comando.

- --i18n-file <string>

Descrição: Informar onde se encontra o arquivo de internacionalização (i18n).

- --i18n-format <string>

Descrição: Informar qual o formato que se encontra o arquivo de internacionalização indicado no comando --i18n-file.

- --locale <string>

Descrição: Informar qual locale deve ser usado para internacionalização.

- --extract-css

Descrição: Por padrão, o Angular compila os estilos dentro de arquivos JS. Este parâmetro informa que esses estilos devem ser colocados dentro de arquivos CSS.

- --watch

Descrição: Recriar o build quando forem encontradas mudanças. Valor padrão: true.

- --poll <number>

Descrição: Define o período, em milissegundos, que será usado para verificar se ocorreram mudanças no projeto.

- -app <string>

Descrição: Define qual das aplicações definidas no arquivo angular-cli.json deve ser usada para ser disponibilizada no servidor.

- --port <number>

Descrição: Descrição: Define qual porta o servidor escutará. Valor padrão: 4200.

- --host <string>

Descrição: Por padrão, o servidor é acessível apenas na própria máquina onde está sendo executado. Com este comando é possível informar que ele pode ser acessado através de outras interfaces de rede.

- --ssl

Descrição: Iniciar o servidor com suporte a SSL (HTTPS).

- --ssl-key <string>

Descrição: Informar a chave privada para usar nas conexões SSL.

- --ssl-cert <string>

Descrição: Caminho para o certificado para ser usado nas conexões SSL.

- --open

Descrição: Abrir o navegador apontando para o endereço do servidor.

- --live-reload

Descrição: Informa se deve recarregar a aplicação no navegador sempre que forem encontradas mudanças no projeto.

- --specs <array>

Descrição: Sobrescreve os specs do arquivo de configuração do Protractor. É possível enviar múltiplos specs repetindo este parâmetro: --specs=spec1.ts --specs=spec2.ts.

- --element-explorer

Descrição: Inicia o Element Explorer do Protractor para fazer debug.

- --serve

Descrição: Compila e serve a aplicação. Ao utilizar este comando, todos os parâmetros usados com ng serve também estarão disponíveis.
## ng build

Todo artefato criado no Angular é escrito em TypeScript, contudo, os navegadores ainda não interpretam essa linguagem nativamente. Assim, faz-se necessário, primeiro, compilar nosso projeto para JavaScript e realizar algumas tarefas que vão deixá-lo mais apto a rodar em um servidor de produção.

Para essa tarefa, existe o comando ng build, que fará todo processamento e gerará uma pasta dist, na qual estarão os arquivos prontos para serem abertos em um navegador.

```js
ng build
```

ou

```js
ng build --prod
```

ou

```js
npm run build --prod --auto
```

ou

```js
npm run build
```

## Irá pegar as configurações padrões, para build, ler a documentação

```js
ng b
```

Depois de fazer o build do seu projeto, encontre a pasta, dist e pronto seu
projeto está pronto para ir para produção.

## Retirando os arquivos .map


```js
ng build --sourcemaps false
```

No entanto, os arquivos resultantes desse processamento ainda não estão minificados e uglified (processo que torna os arquivos ilegíveis), como todo projeto em produção deveria ser. Para esse propósito, é necessário usar a opção target com o valor production, como no comando a seguir.

Exemplo de uso de ng build para gerar versão de produção:

```js
ng build --target=production
```

É válido ressaltar que a opção target pode receber outros valores além de production. Como opção, é possível informar qualquer ambiente definido em /src/environments, por exemplo: production, development e outros criados conforme a necessidade da aplicação.

Entretanto, note que uma vez minificados e uglified, seu projeto deixa de ser "debugável" em um navegador, já que o código torna-se ilegível e possivelmente reduzido a uma única linha (imensa). Caso você não queira isso, basta informar ao ng build para gerar os arquivos do tipo source map (com extensão .map). Esses arquivos contêm informações que são interpretadas pelo navegador e permitem que seu código fonte torne-se legível novamente.

Exemplo de uso de ng build para gerar arquivos source map:

ng build --sourcemaps true
Por último, caso haja necessidade de gerar o build em outro diretório, diferente do diretório padrão (dist), basta usar o parâmetro --output-path, conforme exemplo abaixo:

Exemplo de uso de ng build mudando o diretório de saída:


```js
ng build --output-path producao
```

## Parâmetros

O comando ng build pode receber parâmetros, e os principais estão detalhados na Tabela 1.

- --target <string>

Descrição: Define qual tipo de build deve ser gerado: (development, production). Valor padrão: development.

- --environment

Descrição: Define qual dos ambientes informados em /src/environments deve ser usado na geração do build.

- --output-path <string>

Descrição: Mudar o diretório onde serão colocados os artefatos do build. Valor padrão: dist.

- --aot

Descrição: Criar o build usando compilação AOT (Ahead of Time), ao invés de JIT (Just in Time). Esta opção melhora o desempenho, pois todos artefatos são previamente compilados para JavaScript.

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

Descrição: Define o período, em miliSsegundos, que será usado para verificar se ocorreram mudanças no projeto.

- -app <string>

Descrição: Define qual das aplicações definidas no arquivo angular-cli.json deve ser usada para ser disponibilizada no servidor.

- --stats-json

Descrição: Gerar o arquivo stats.json, que pode ser analisado pelo webpack-bundle-analyzer.

Exemplo prático:

Suponha que sua equipe fechou o ciclo de desenvolvimento de uma versão do produto e que agora é necessário gerar um build da versão de produção para o cliente. Entretanto, você gostaria que fossem gerados os arquivos de Source Map, para que caso haja erro, seu cliente possa enviar esses dados. Além disso, o servidor onde esse build será disponibilizado possui o termo "producao" como prefixo de toda URL. Para gerar esse build, você pode utilizar o seguinte comando:

```js
ng build --sourcemaps --base-href producao/
```





## ng service

Uma necessidade de todo desenvolvedor é ter um servidor HTTP em sua máquina para poder testar, de forma fácil e imediata, as alterações realizadas nos arquivos do projeto. Pensando nesse problema, o Angular CLI disponibilizou o comando ng serve.

Exemplo de uso:

```js
ng serve
```
ou

```js
ng s
```

## Para emular o projeto

```js
ng serve -o
```

ou

```js
ng serve --open
```

ou

```js
ng s
```

ou

Por padrão, o servidor é criado escutando na porta 4200, entretanto, é possível alterá-la usando alguns parâmetros, como no exemplo abaixo.

Exemplo de uso de ng serve alterando a porta padrão:

```js
ng serve --port 9090
```

## Parâmetros

O comando ng serve pode receber parâmetros, e os principais estão detalhados na Tabela.

- --target <string>	Define qual tipo de build deve ser gerado: (development, production). Valor padrão: 
development.

- --environment	Define qual dos ambientes definidos em /src/environments deve ser usado na geração do build.

- --aot	Criar o build usando compilação AOT (Ahead of Time), ao invés de JIT (Just in Time). Esta opção melhora o desempenho, pois todos artefatos são previamente compilados para Javascript.

- --sourcemaps	Criar arquivos de source map (arquivos com extensão .map).
- --base-href <string> *	Altera a tag base-href no arquivo index.html para o valor informado.
- --deploy-url <string> *	URL na qual a aplicação será implantada.
- --verbose	Exibe mais informações sobre a execução do comando.
- --i18n-file <string>	Informar onde se encontra o arquivo de internacionalização (i18n).
- --i18n-format <string>	Informar qual o formato que se encontra o arquivo de internacionalização indicado no comando --i18n-file.
- --locale <string>	Informar qual locale deve ser usado para internacionalização.
- --extract-css	Por padrão, o Angular compila os estilos dentro de arquivos JS. Este parâmetro informa que esses estilos devem ser colocados dentro de arquivos CSS.
- --watch	Recriar o build quando forem encontradas mudanças. Valor padrão: true.
- --poll <number>	Define o período, em milissegundos, que será usado para verificar se ocorreram mudanças no projeto.
- -app <string>	Define qual das aplicações definidas no arquivo angular-cli.json deve ser usada para ser disponibilizada no servidor.
- --port <number>	Define qual porta o servidor escutará. Valor padrão: 4200.
- --host <string>	Por padrão, o servidor é acessível apenas na própria máquina onde está sendo executado. Com este comando é possível informar que ele pode ser acessado através de outras interfaces de rede.
- --ssl	Iniciar o servidor com suporte a SSL (HTTPS).
- --ssl-key <string>	Informar a chave privada para usar nas conexões SSL.
- --ssl-cert <string>	Caminho para o certificado para ser usado nas conexões SSL.
- --open	Abrir o navegador apontando para o endereço do servidor.
- --live-reload	Informa se deve recarregar a aplicação no navegador sempre que forem encontradas mudanças no projeto.

## Exemplo prático

Suponha que você precise criar um projeto em Angular e queira mudar o prefixo de todos os seus componentes do valor padrão "app" para "my", além de evitar a criação de arquivos de teste e a instalação das dependências. Para fazer isso, deve ser executado o seguinte comando:

```js
ng new myapp --prefix my --skip-tests --skip-install
```

Uma vez que temos o projeto criado, podemos iniciar um servidor HTTP na porta 8080 e que seja visível para qualquer máquina da rede com o comando a seguir:

```js
ng serve --port 8080 --host 0.0.0.0
```


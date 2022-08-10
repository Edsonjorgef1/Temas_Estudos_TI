## ng new

Utilizamos o comando ng new para criar um novo projeto em Angular. Ao executar esse comando, será criada uma nova pasta contendo uma estrutura de diretórios com os arquivos necessários para iniciar um projeto nesse framework, como mostra a Figura 1.

Exemplo de uso:

```js
ng new
```

Essa é a estrutura indicada pela equipe do Angular, portanto, embora seja possível alterá-la, sugerimos mantê-la. Entre essas pastas, aquela que será mais utilizada pelos desenvolvedores é a src/app, pois é nela onde encontram-se todos os arquivos do projeto, como arquivos referentes aos componentes, diretivas, filtros e módulos da aplicação. Para mais informações sobre o objetivo das demais pastas, consulte a tabela

- e2e	Testes end-to-end usando o Protractor.
- node_modules	Dependências do Node.JS necessárias no projeto.
- src/assets	Recursos externos do projeto, como CSS, imagens, bibliotecas JavaScript, etc.
- src/environments	Configuração dos ambientes da aplicação (desenvolvimento, produção, etc).

## Parâmetros

- --directory <diretório>	Informar o nome do diretório no qual a estrutura de pastas do projeto será criada.

- --dry-run	Caso o diretório do projeto já exista, não modificar os arquivos que já foram editados manualmente. Valor padrão: falso.

- --inline-style	Colocar os estilos (CSS) inline, dentro dos arquivos Typescript, ao invés de criar um arquivo em separado para eles. Valor padrão: falso.

- --inline-template	Colocar os templates inline, dentro dos arquivos Typescript, ao invés de criar um arquivo em separado. Valor padrão: falso.

- --prefix <prefixo>	Definir o prefixo que deve ser usado para todos os seletores de componentes da aplicação. Valor padrão: app.

- --routing	Criar um módulo à parte, no qual serão definidas as rotas da aplicação. Valor padrão: falso.

- --skip-git	Evitar a criação do repositório git para o projeto. Valor padrão: falso.

- --skit-commit	Evitar o primeiro commit no repositório git do projeto. Valor padrão: falso.

- --skip-install	Não fazer a instalação dos pacotes necessários para o projeto usando o npm. Valor padrão: falso.

- --skip-tests	Evitar que sejam criados os arquivos de teste.

- --source-dir <diretório>	Definir o nome do diretório onde serão criados os arquivos fonte da aplicação. Valor padrão: src.

- --style <nome>	Definir a extensão padrão para os arquivos de estilo. Valor padrão: css.

- --verbose	Imprimir mais informações sobre a execução do comando ng new.
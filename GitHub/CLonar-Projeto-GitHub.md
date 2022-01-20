Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Para clonar um projeto do GitHub

Basta você copiar a URL, do projeto que deseja,
você vai achar na opção <code>, depois clique em Code, opção HTTPS, ai você
copia a URL, e faz o comando abaixo.

```js
git clone (URL do projeto que deseja clonar)
```

Lembre-se que, se o projeto for em React, depois de clonar o projeto você deve
fazer.

```js
yarn
ou
npm install
```
## Commit semantico
type:
    feat     Adição de funcionalidade.
    fix      Correção de defeito.
    docs     Mudança em documentação.
    style    Mudança de formatação ou estilo, que não afeta a execução do código (espaço, tabulação, etc).
    refactor Mudança na organização do código, que não afeta o comportamento existente.
    test     Adição ou mudança de um teste.
    chore    Adição ou mudança em script de build, que não afeta o código de produção.
    perf     Mudança de código para melhoria de desempenho.
    ci       Mudança de configuração de integração contínua.
    build    Mudança em arquivos de build ou em dependências externas.
    temp     Commit temporário, que não deve ser incluído no CHANGELOG.

  scope:
    Opcional, pode ser qualquer coisa que especifique o escopo da mudança.
    Exemplos: subpacote, workspace, módulo, componente, página.
    `scope` é opcional, mas o conteúdo entre parênteses não pode ficar vazio.

  subject:
    Breve resumo da mudança, escrito no tempo verbal presente. Começa com letra minúscula e não há ponto final.
  
  
  git commit -m "refactor: teste Ultimo"
  
  No lugar de refactor, escolha qual o type que você quer e pronto, não esqueça de commitar na branch correta.
  
  
## Outros
Para que fazer, yarn start ou npm start, para você instalar as dependências do
projeto padrão do react, que é a pasta node_modules, ai depois de fazer isso você pode, verificar no arquivo package.json, as dependência instaladas, exemplo: bootstrap, vai estar tudo la dentro, para você ficar por dentro o que está acontecendo no projeto.

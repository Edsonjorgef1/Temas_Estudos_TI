## ng generate component

Um guard é um recurso utilizado para informar se um usuário pode navegar para uma determinada rota ou não. Ele pode ser criado através do comando ng generate guard, conforme exemplo abaixo.

Exemplo de uso:

```js
ng generate guard UserLoggedInGuard
```

O resultado da execução serão dois arquivos: um contendo a classe que representa o guard e outro contendo os testes dessa classe.

### Parâmetros 


Para esse comando, podemos especificar os parâmetros apresentados na Tabela.

- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do guard serão colocados. Valor padrão: true.

- --spec

Descrição: Define se deve ser gerado o arquivo de testes (arquivo com extensão .spec.ts).

- --module <string>

Descrição: Define para qual módulo da aplicação este guard deve ser criado.
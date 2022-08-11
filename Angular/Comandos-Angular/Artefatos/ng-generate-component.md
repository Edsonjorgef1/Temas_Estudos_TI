## ng generate component

## Criando um componente dentro de uma pasta especifica

```js
$ ng g c --module pages pages/details
```

## Como criar um componente

Aqui iremos criar um componente

```js
ng generate component primeiro-componente
```

ou

```js
ng g c primeiro-componente
```

## Agora se quiser criar um componente sem o teste unitário

```js
ng g c primeiro-componente --spec=false
```

## Para criar um componente dentro de uma pasta especifica

```js
ng g c /nomedapasta/nomedoquivo
```

Um dos artefatos mais importantes para o desenvolvimento com Angular, um componente pode ser criado de forma bastante simples, utilizando o comando ng generate component <nome>.

```js
ng generate component favorito
```
O resultado da execução desse comando é:

```js
ng generate component favorito
installing component
 create src/app/favorito/favorito.component.css
 create src/app/favorito/favorito.component.html
 create src/app/favorito/favorito.component.spec.ts
 create src/app/favorito/favorito.component.ts
 update src/app/app.module.ts
 ```

 Observe que além de criar um novo diretório e os quatro arquivos necessários para um componente, esse comando também atualiza o arquivo app.module.ts, com o objetivo de incluir nele os dados necessárias para informar ao Angular sobre esse novo componente.

### Parâmetros:

Para esse comando, podemos especificar os parâmetros apresentados na Tabela.

- --flat

Descrição: Flag que indica se deve ser criado um diretório no qual os arquivos do componente serão colocados. Valor padrão: true.

- --inline-style

Descrição: Colocar os estilos (CSS) inline, dentro do próprio arquivo ts, ao invés de criar um arquivo em separado para eles. Valor padrão: false.

- --inline-template

Descrição: Colocar os templates inline, dentro do próprio arquivo ts, ao invés de criar um arquivo em separado. Valor padrão: false.

- --prefix <string>

Descrição: Define o prefixo do seletor do componente. Caso não informado, é utilizado o prefixo padrão da aplicação (valor "app" ou outro definido a partir do parâmetro prefix do comando ng new).

- --spec

Descrição: Define se o arquivo de teste com extensão .spec.ts deve ser criado. Valor padrão: true.

- --view-encapsulation <string>

Descrição: Informa a estratégia de encapsulamento da View, que é relacionada ao uso do Shadow DOM (HTML 5) por sua aplicação de forma nativa ou emulada.

- --change-detection <string>

Descrição: Define a estratégia de detecção de mudanças que o componente deve usar.

- --skip-import

Descrição: Define se o novo componente deve ser automaticamente importado no módulo para o qual ele foi criado. Caso contrário, será necessário importá-lo manualmente.

- --module <string>

Descrição: Define para qual módulo da aplicação este componente deve ser criado.

- --export

Descrição: Define se o componente é visível para outros módulos.

- --app <string>

Descrição: É possível definir várias aplicações no arquivo angular-cli.json contendo diferentes configurações. Este parâmetro especifica para qual dessas aplicações o componente deve ser criado. Por padrão, é a primeira aplicação informada no arquivo angular-cli.json.
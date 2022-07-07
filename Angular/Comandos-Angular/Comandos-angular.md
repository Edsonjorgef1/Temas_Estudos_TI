Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Lista de comandos angular

```js
ng help
```

## Verificar comandos angular

```js
, + ctrl + barra
```

## Verificando o que tem dentro do generate

```js
ng generate --help
```

## Rodando projeto

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

## Criando um modulo

```js
 ng g module my-new-module
```

## Criando uma diretiva

```js
ng g directive my-new-directive
```

## Diretiva Pipe

```js
ng g pipe my-new-pipe
```

## Directive Service

```js
ng g service my-new-service
```

## Criando uma Class

```js
ng g class my-new-class
```

## Criando uma Interface

```js
ng g interface my-new-interface
```

## Enum

```js
ng g enum my-new-enum
```

## Fazendo um build do projeto

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

Depois de fazer o build do seu projeto, encontre a pasta, dist e pronto seu
projeto está pronto para ir para produção.

## Teste Unitários

```js
ng test
```

## Irá pegar as configurações padrões, para build, ler a documentação

```js
ng b
```

## Testes de integração

```js
ng e2e
```

## Coridigo padronizado, ele irá ver a qualidade do código

```js
ng lint
```

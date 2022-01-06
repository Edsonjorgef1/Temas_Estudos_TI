Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando o arquivo tsconfig.json

tsc --init

Vai criar um arquivo tsconfig.json, vai ser criado dentro da pasta src, significa, se eu fizer o comando tsc no terminal ele vai procurar no projeto todo arquivos typescript, de acordo com nossas configurações

Eu posso configurar, neste arquivo tsconfig.json, exemplo: mostre pra mim apenas os erros, eu não quero que gere nenhum arquivo, após a varredura, entre todas as pastas.

Posso fazer tambpem tsc -w, para monitorar os erros

## Escolhendo quais arquivos compilar

tsconfig.json

Excluindo arquivos que você não quer que gere outra vez

},
"exclude": [
    "**/*.dev.ts"  /*Exclua todos os arquivos .dev.ts, que eles não sejam compilados **/ significa em qualquer pasta*/
    "src/outro.ts" /*Excluindo um arquivo específico*/
    "node_modules" /*Excluindo a pasta, ignorando*/ 
]
"include": [
    /*Incluir arquivos, limitar o que queremos*/
    "src/script.ts"  /*Filtrando só este arquivo*/
    "include": [
        "src/*", /*Gerando arquivos, apenas desta pasta*/
        "app.ts"
    ]
]
}

## Entendendo o Target

ctrl + barra, da para verificar as versões disponível

"target": "ES5", gerando meu códgo compativel com o arquivo ecma escript 5

exemplo: o let e o const está disponível apartir do ecma script 6, preste atenção nisso
exemplo: var, e do ecma script 5 para baixo

## Trabalhando com Libs no Typescript

Se deixar a lib comentada, não aprece o erro, porque atomaticamente ele adiciona algumas bibliotecas
/*Adicionando estas bibliotecas ou deixar comentado o lib, é a mesma coisa*/
"lib": [
    "DOM", /*Adicionando uma biblioteca*/
    "ES5",
    "DOM.Iterable",
    "ScriptHost" 
],

## rootDir e outDir

outDir, criando o caminho, aonde vai ser gerado os arquivos, depois de fazer o comando tsc

"outDir": "./public/assets/js", /*Destino final é aqui dentro*/
"rootdir": "./src", /*Ele sabe que o meu projeto, os arquivos estão aqui dentro */

## removeComment, noEmit e noEmitOnError
"removeComents": true, /*Ele vai remover todo o comentario do projeto, para o projeto ficar mais leve, se eu tiver ele tiver comentado este removeComment, ele vai comentar no projeto, vai ficar vendo*/
"noEmit": true, - não gere os arquivos compilados, muito pouco utilizado
"noEmitOnError": true, - Se tiver algum erro, não emiti nada.

## Configurações para Qualidade do código, noUnusedLoacals, noUnusedParameters
tracinho vermelho é um erro
tracinho amarelo é um aviso
"noUnusedLoacals": true, /*avisar que foi criado uma variavel e não foi utilizado*/
"noUnusedParameters": true, /*Quando eu tenho um parametro que não estou usando*/
"noImplicitReturns": true, /*sem retornos implicitos, se eu não tiver retorno nenhum ele avisa, não é bom, liberar está função não*/
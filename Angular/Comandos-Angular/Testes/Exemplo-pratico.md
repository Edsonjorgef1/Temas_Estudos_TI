## Exemplo Prático 

Suponha que foram criados todos os testes de sua aplicação e, antes de enviar o código para produção, é necessário executar o Lint e ao mesmo tempo corrigir possíveis erros de estilo de código encontrados. Além disso, é uma prática na sua empresa guardar a saída do Lint em um arquivo no formato JSON. Para isto, você pode executar:

```js
ng lint --fix --format json
```

Outra boa prática de desenvolvimento é checar se erros foram introduzidos no projeto durante o último ciclo de desenvolvimento. Como todo desenvolvedor cauteloso, você pode preferir ir alterando o projeto e assim que salvar os arquivos modificados, executar os testes imediatamente, além de querer ver o resultado dos testes colorido, para facilitar a visualização. Para obter esse resultado, você pode executar o código abaixo a cada mudança feita:

```js
ng test --colors --watch
```

Por último, os testes do tipo e2e também são muito importantes e você também gostaria que eles fossem executados imediatamente, mas na versão que irá para produção. Para fazer isso, basta usar o comando abaixo:

```js
ng e2e --watch --target production
```

## Parametrizando-pipes

Os pipes podem receber parâmetros, o que permite customizar ainda mais a formatação dos dados.

Relembrando, para aplicar qualquer pipe a um dado utilizamos a sintaxe {{ dado | pipe }}. Fizemos isso no Código 1, onde utilizamos o pipe date. Contudo, embora a data tenha sido formatada naquele exemplo ela ficou em um formato americano e não brasileiro. Para resolver isso podemos usar parâmetros no pipe.

Com isso, a sintaxe muda um pouco, pois agora precisamos escrever {{ dado | pipe:”<PARAMETROS”> }}, sendo os parâmetros passados entre aspas e duplas por conversão.

Por exemplo, para usar o formato de data dia/mês/ano, mais comum aqui no Brasil, podemos utilizar os parâmetros dd/MM/yyyy com DatePipe, como mostra o Código 2.

Código 2. Usando DatePipe com parâmetros

```js
<p>{{ hoje }}</p>

<p>{{ hoje | date:"dd/MM/yyyy" }}</p>
```

Como resultado na aplicação desses parâmetros a data será apresentada como 19/03/1989.


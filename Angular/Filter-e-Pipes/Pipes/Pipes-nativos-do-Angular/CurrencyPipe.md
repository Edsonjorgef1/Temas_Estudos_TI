## CurrencyPipe

Para moedas

Após aprender como um pipe funciona você já sabe o suficiente para utilizar qualquer outro.

Por exemplo, ao aplicar CurrencyPipe em um valor qualquer teremos um código muito parecido com o que vimos anteriormente, como mostra o Código 5.


app.component.ts

```js

import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  preco = 19.99;
}
```

app.component.html

```js
<p>{{ preco }}</p>

<p>{{ preco | currency }}</p>
```


### Corrigindo problemas com localização

Uma forma de resolver esse problema é parametrizando CurrencyPipe para um local apropriado, como vemos no Código 6.

```js
<p>{{ preco }}</p>

<p>{{ preco | currency:"BRL" }}</p>
```

No caso das datas informamos a timezone e o local para formatá-las em português. Temos diversas opções de timezone, mas geralmente utilizamos os valores IST ou +0530, que são padrões internacionais.

Sabendo disso, a expressão no template do componente ficará conforme o Código 7 para apresentar o mês em português.

app.module.html

```js
  <p>{{ hoje }}</p>

  <p>{{ hoje | date:"dd/MMM/yyyy":"IST":"pt" }}</p>
```
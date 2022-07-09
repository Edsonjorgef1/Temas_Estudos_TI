Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando uma lista

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
  nomes = ["Beto", "Paulo", "Amigo", "Pai"];
  nomePrincipal = this.nomes[0];
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal }}</p>

<ul>
  <li *ngFor="let nome of nomes">
    {{ nome }}
  </li>
</ul>
```

## Criando um array com objetos e acessando o nome e idade

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
  nomes = [
    { nome: "Betso", idade: 90 },
    { nome: "Paulo", idade: 20 },
    { nome: "Fulano", idade: 40 },
    { nome: "Ciclano", idade: 30 },
    { nome: "Beltrano", idade: 10 },
  ];
  nomePrincipal = this.nomes[0];
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal.nome }}</p>

<ul>
 <!-- item = Este nome item, você pode colocar qualquer nome, e a variavel nomes, é do aquivo app.component.ts, estamos praticamente colocando tudo da variavel nomes, dentro da variavel item criada, e depois só referenciar quem você quer achar que no caso item.nome ou item.idade e o ngFor estaá fazendo um loop para imprimir os nossos dados-->
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos
  </li>
</ul>
```

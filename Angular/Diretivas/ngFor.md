Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgFor

Repete um nó para cada item de uma lista

## Lista 1

app/primeiro-componente/primeiro-componente.component.html

```js
<!--ngFor = literar uma lista de intens, repetindo elementos aonde ela é usada -->
<div class="div">
  <ul>
    <li *ngFor="let item of [1, 2, 3]">valor: {{ item }}</li>
  </ul>
</div>
```

## ngFor, Lista 2, Array, com strings

app.component.html

```js
<ul>
  <li *ngFor="let nome of nomes" style="color: #ff0000">
    {{ nome }}
  </li>
</ul>
```

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  /*Array, com strings*/
  nomes = ["beto", "Valdir", "Elio"];
  /*nomes = [  "0" ,   "1"   ,  "2"  ]*/
}
```

## ngFor, Lista 3, Array, com objetos

app.component.html

```js
<h1>Nome Principal: {{ nomePrincipal.nome }}</h1>
<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos
  </li>
</ul>

```

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  /*Array com objetos */
  nomes = [
    { nome: "Beto", idade: 90 },
    { nome: "Paulo", idade: 20 },
    { nome: "Irmao", idade: 40 },
    { nome: "Pai", idade: 60 },
    { nome: "Mae", idade: 80 },
  ];
  nomePrincipal = this.nomes[1];
}
```

## Neste exemplo vamos adicionar e remover um item

src/app/diretivas-estruturais/diretivas-estruturais.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-estruturais',
  templateUrl: './diretivas-estruturais.component.html',
  styleUrls: ['./diretivas-estruturais.component.scss'],
})
export class DiretivasEstruturaisComponent implements OnInit {
  public list: Array<{ nome: string; idade: number }> = [
    { nome: 'Dener', idade: 29 },
    { nome: 'José', idade: 59 },
    { nome: 'Isabel', idade: 65 },
  ];

  constructor() {}

  ngOnInit(): void {}
  //push adicionar um novo nome e idade
  public onClickAddList() {
    this.list.push({ nome: 'Nay', idade: 31 });
  }
  //splice ele irá remover um item
  public onClickEventList(event: number) {
    this.list.splice(event, 1);
  }
}
```

src/app/diretivas-estruturais/diretivas-estruturais.component.html

```js
<ul>
  <li *ngFor="let item of list; let i = index" (click)="onClickEventList(i)">
    <!-- i, posição do array -->
    [{{ i }}] - {{ item.nome }} - idade = {{ item.idade }}
  </li>
</ul>

<button (click)="onClickAddList()">Add</button>
```

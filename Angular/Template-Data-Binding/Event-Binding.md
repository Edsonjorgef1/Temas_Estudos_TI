Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Event Binding

É a associação de eventos que permite você escutar e responder às ações do
usuário, como pressionamentos de tecla, movimentos do mouse, cliques e toques

## Retornando string de uma funcao criada

app/primeiro-component/primeiro-componente.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <button (click)="geralTexto()">Save</button>
  <p>{{ geralTexto() }}</p>
</div>
<br />
<div>

</div>
```

app/primeiro-component/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente",
  templateUrl: "./primeiro-componente.component.html",
  styleUrls: ["./primeiro-componente.component.css"],
})
export class PrimeiroComponenteComponent implements OnInit {
  constructor() {}

  ngOnInit() {}

  //Criando uma função
  geralTexto() {
    return "Texto sendo retornado pela função";
  }
}
```

## Retornando um evento, mouseEvent

app/data-biding/data-biding.component.html

```js
import { Component, OnInit } from '@angular/core';

@Component({ selector: 'app-data-biding', templateUrl:
'./data-biding.component.html', styleUrls: ['./data-biding.component.scss'], })
export class DataBidingComponent implements OnInit { public nome: string =
'Dener'; public idade: number = 29; public maisUm: number = 1;

public checkedDisabled: boolean = false; public imgSrc: string =
'https://www.google.com.br/google.jpg'; public imgTitle: string = 'Property
Binding'; constructor() {}
//Passando um valor evento
ngOnInit(): void {} public alertInfo(valor: MouseEvent) { console.log(valor); }
}
```

app/data-biding/data-biding.component.ts

```js
<button (click)="alertInfo($event)">Evento</button>
```

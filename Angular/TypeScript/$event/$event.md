Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
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

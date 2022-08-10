Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngOnChanges

Este evento é executado sempre que um valor de um controle de entrada dentro do
componente é alterado. Sempre que um componente recebe um dado através do
@input() o ngOnChanges() é invocado

@input ele é a entrada de dados @output ele é a saidade de dados

## Exemplo alterar a variavel title

src/app/title/title.component.ts

```js
import { Component, Input, OnChanges, OnInit } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.scss'],
})
export class TitleComponent implements OnInit, OnChanges {
  @Input() public title: string = 'Bem Vindo';

  constructor() {}

  ngOnInit(): void {}
  ngOnChanges(): void {
    alert('Foi alterado com sucesso');
  }
}

```

src/app/app.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: `<app-title title="Olá Mundo"> </app-title>
    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  constructor() {}
  ngOnInit(): void {}
}
```

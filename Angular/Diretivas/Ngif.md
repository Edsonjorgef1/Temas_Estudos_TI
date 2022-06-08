Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgIf

Condicionalmente cria ou descarta visualizações do modelo.

## Aviso

app.component.html

```js
<!--ngIf = Permiti que elementos apareçam ou sumam conforme o estado da condição é alterada-->
<div *ngIf="showAviso">{{ avisoMsg }}</div>
```

app.component.ts

```js
import { Component } from "@angular/core";
import { Pessoa } from "./pessoa";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  //Aviso
  showAviso = true;
  avisoMsg = "Estem é um aviso";
}
```

## Exemplo, aparecendo ou não um cliente

app/primeiro-componente/primeiro-componente.component.html

```js
<div *ngFor="let umCliente of clientes">
  <p *ngIf="umCliente.ativo">{{ umCliente.id }} - {{ umCliente.nome }}</p>
</div>
```

app/primeiro-componente/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente",
  templateUrl: "./primeiro-componente.component.html",
  styleUrls: ["./primeiro-componente.component.css"],
})
export class PrimeiroComponenteComponent implements OnInit {
  clientes = [
    {
      id: 1,
      nome: "Fulano",
      ativo: true,
    },
    {
      id: 2,
      nome: "Beltrano",
      ativo: false,
    },
    {
      id: 3,
      nome: "Ciclano",
      ativo: true,
    },
  ];

  constructor() {}

  ngOnInit(): void {}
}
```

## Outros exemplos

app/diretivas-estruturais/diretivas-estruturais.component.html

```js
<!-- <p *ngIf="false">True</p> -->
<p *ngIf="conditional; else elseBlock">Alerta</p>
<ng-template #elseBlock>
  <p>False</p>
</ng-template>
<hr />
<p *ngIf="conditionalClick">true</p>
<p *ngIf="!conditionalClick">False</p>

<button (click)="onClick()">Clicar</button>
```

app/diretivas-estruturais/diretivas-estruturais.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-estruturais',
  templateUrl: './diretivas-estruturais.component.html',
  styleUrls: ['./diretivas-estruturais.component.scss'],
})
export class DiretivasEstruturaisComponent implements OnInit {
  public conditional: boolean = true;
  public conditionalClick: boolean = true;

  constructor() {}

  ngOnInit(): void {
    //A cada segundo vou fazer alguma coisa
    setInterval(() => {
      if (this.conditional) {
        this.conditional = false;
      } else {
        this.conditional = true;
      }
    }, 2000);
  }
  public onClick() {
    if (this.conditionalClick) {
      this.conditionalClick = false;
    } else {
      this.conditionalClick = true;
    }
  }
}
```

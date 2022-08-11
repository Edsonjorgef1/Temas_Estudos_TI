Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgIf

A primeira diretiva estrutural que veremos é o ngIf, que funciona de forma similar a estrutura condicional IF: dado um valor booleano, se verdadeiro um bloco de código deve ser executado.

No caso da diretiva ngIf, dado um valor booleano, se verdadeiro um elemento HTML deve ser renderizado para o usuário.

Diretivas estruturais como o ngIf podem ser utilizadas em qualquer elemento HTML ou componentes Angular, e são essenciais no desenvolvimento de interfaces com o Angular.

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
## Mostrando ou não um texto específico

condicional.component.html

```js
<button (click)="toggleConteudo()">Toggle</button>

<h1 *ngIf="exibirConteudo">Conteúdo oculto!</h1>
```

condicional.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public exibirConteudo = true;

  toggleConteudo() {
    this.exibirConteudo = !this.exibirConteudo;
  }

  constructor() {}

  ngOnInit(): void {}
}
```

## Olha que legal, eu posso agora tirar ou adicionar um componente se eu quiser

condicional.component.html

```js
<button (click)="toggleConteudo()">Toggle</button>

<h1 *ngIf="exibirConteudo">Conteúdo oculto!</h1>
```

src/app/condicional.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public exibirConteudo = true;

  toggleConteudo() {
    this.exibirConteudo = !this.exibirConteudo;
  }

  constructor() {}

  ngOnInit(): void {}
}
```

src/app/condicional.component.html

```js
<button (click)="toggleConteudo()">Toggle</button>

<h1 *ngIf="exibirConteudo">Conteúdo oculto!</h1>
```


## Quando clicar no botão sumir um componente

src/app.component.html

```js
<app-contador></app-contador>
<app-teste *ngIf="exibirConteudo"></app-teste>
<router-outlet></router-outlet>
```
src/app.component.ts

```js
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss'],
})
export class AppComponent {
  public exibirConteudo = true;
}
```

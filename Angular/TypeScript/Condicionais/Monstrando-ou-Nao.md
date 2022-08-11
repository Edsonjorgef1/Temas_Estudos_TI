Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
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
<button (click)="toggleConteudo()">Toggle</button>
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
  public toggleConteudo() {
    this.exibirConteudo = !this.exibirConteudo;
  }
}
```
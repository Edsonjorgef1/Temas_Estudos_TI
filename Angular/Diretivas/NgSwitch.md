Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgSwitch

Um Conjunto de diretivas que alternam entre visões alternativas. Ele é igual
switch case do javascript

src/app/diretivas-estruturais/diretivas-estruturais.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-estruturais',
  templateUrl: './diretivas-estruturais.component.html',
  styleUrls: ['./diretivas-estruturais.component.scss'],
})
export class DiretivasEstruturaisComponent implements OnInit {
  public nome: string = 'dener';

  constructor() {}

  ngOnInit(): void {}
}
```

src/app/diretivas-estruturais/diretivas-estruturais.component.html

```js
<input type="text" [(ngModel)]="nome" />
<div [ngSwitch]="'nome'">
  //Aqui é o primeiro caso
  <p *ngSwitchCase="'dener'">Dener</p>
  //Aqui é o segundo caso
  <p *ngSwitchCase="'nay'">Nay</p>

  <!-- Da para fazer nossas validações, com este Default -->
  <p *ngSwitchDefault>Deu ruim sua busca</p>
</div>
```

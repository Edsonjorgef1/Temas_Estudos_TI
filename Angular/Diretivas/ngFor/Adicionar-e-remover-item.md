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

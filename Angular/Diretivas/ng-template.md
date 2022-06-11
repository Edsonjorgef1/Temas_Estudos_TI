## ng-template

## Como adicionar, um item

Ele cria um atributo no html limpo, ele não é uma div, ele é um elemnto em html
que nos vai ajudar fazer verificações com ngIf, antes do dom ser carregado, ele
encapsula os dados para fazer validações.

src/app/diretivas-atributos/diretivas-atributos.component.html

```js
<ng-template ngFor let-item [ngForOf]="list">
  <p>{{ item.nome }}</p>
</ng-template>

<input [(ngModel)]="nome" />
<button (click)="salvar()">Salvar</button>
```

src/app/diretivas-atributos/diretivas-atributos.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-atributos',
  templateUrl: './diretivas-atributos.component.html',
  styleUrls: ['./diretivas-atributos.component.scss'],
})
export class DiretivasAtributosComponent implements OnInit {
  public valor: boolean = true;
  public heightPx: string = '20px';
  public backgroundColor: string = 'red';
  public nome: string = '';
  public list: Array<{ nome: string }> = [{ nome: 'Gilberto' }];

  constructor() {}

  ngOnInit(): void {}
  public salvar() {
    this.list.push({ nome: this.nome });
    this.nome = '';
  }
}
```

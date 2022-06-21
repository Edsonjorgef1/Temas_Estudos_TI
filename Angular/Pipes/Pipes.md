## Pipes

Ele pega as informações do interpolation e faz uma modificação ele nos ajuda a
modificar alguma coisa, o angular vem alguns Papis prontos para auxiliar no
desenvolvimento, para mais detalhes olhar a documentação.

Simbolo = |

src/app/diretivas-atributos/diretivas-atributos.component.html

```js
<input [(ngModel)]="nome" />

<button (click)="salvar()">Salvar</button>

<!-- Utilizando o pipe para deixar com letra maiuscula uppercase -->
<li *ngFor="let item of list">{{ item.nome | uppercase }}</li>

<!-- Pipe com data -->
{{ date | date: "dd/MM/yyyy" }}
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

  public date: Date = new Date();

  constructor() {}

  ngOnInit(): void {}
  public salvar() {
    this.list.push({ nome: this.nome });
    this.nome = '';
  }
}
```

src/app/app.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: ` <app-diretivas-atributos> </app-diretivas-atributos>

    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

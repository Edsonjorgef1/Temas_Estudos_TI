## ng-content

Digamos que precisamos trocar valor em um local de nosso aplicativo, ai neste
aplicativo você precisa passar um outro valor em h1 ou h2 do mesmo componente e
o restante do componente ficar igual

E também organizar a estrutura, em determinado posições

src/app/diretivas-atributos/diretivas-atributos.component.html

```js
<!-- Organizando o lugar aonde será exibido o h1 -->
<ng-Content select="h1"></ng-Content>

<ng-template ngFor let-item [ngForOf]="list">
  <p>{{ item.nome }}</p>
</ng-template>

<input [(ngModel)]="nome" />
<button (click)="salvar()">Salvar</button>
<!-- Organizando o lugar aonde será exibido o h3 -->
<ng-Content select="h3"></ng-Content>

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

src/app/app.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: ` <app-diretivas-atributos>
      <h1>Aulas de Diretivas Atributo</h1>
      <h3>Final da aula</h3>
    </app-diretivas-atributos>

    <!-- Aqui estou copiando o mesmo componente só que 
    alterando somente h1 e h3, e o restando do codigo que está no 
    html está do mesmo jeito -->

    <app-diretivas-atributos>
      <h1>Beto</h1>
      <h3>Nay torres</h3>
    </app-diretivas-atributos>

    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

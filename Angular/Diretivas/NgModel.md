Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Two-way binding

É A União do property-binding com event-binding. Use para ouvir eventos e
atualizar valores simultaneamente entre os componentes pai e filho.

## ngModel

NgModel - Adiciona vinculação de dados bidirecionais a um elemento de formulário
HTML

app/title/title.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.scss'],
})
export class TitleComponent implements OnInit {
  public nome: string = 'Dener';

  constructor() {}

  ngOnInit(): void {}
}
```

app/title/title.component.html

```js

<input [(ngModel)]="nome" />
<span>{{ nome }}</span>

```

app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { TitleComponent } from "./title/title.component";
//Importando FormsModule, para habilitar o ngModel
@NgModule({
  declarations: [AppComponent, TitleComponent],
  imports: [BrowserModule, AppRoutingModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

## Como adicionar, um item e remover uma div, digitando um texto

src/app/diretivas-atributos/diretivas-atributos.component.html

```js
<div *ngIf="nome != 'Dener'">ddddd</div>

<input [(ngModel)]="nome" /> {{ nome }}

<button (click)="salvar()">Salvar</button>

<li *ngFor="let item of list">{{ item.nome }}</li>
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
  public list: Array<{ nome: string }> = [];

  constructor() {}

  ngOnInit(): void {}
  public salvar() {
    this.list.push({ nome: this.nome });
    this.nome = '';
  }
}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { TitleComponent } from "./title/title.component";
import { DataBidingComponent } from "./data-biding/data-biding.component";
import { DiretivasEstruturaisComponent } from "./diretivas-estruturais/diretivas-estruturais.component";
import { DiretivasAtributosComponent } from "./diretivas-atributos/diretivas-atributos.component";

@NgModule({
  declarations: [
    AppComponent,
    TitleComponent,
    DataBidingComponent,
    DiretivasEstruturaisComponent,
    DiretivasAtributosComponent,
  ],
  imports: [BrowserModule, AppRoutingModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

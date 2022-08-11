Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Two-way binding

É A União do property-binding com event-binding. Use para ouvir eventos e
atualizar valores simultaneamente entre os componentes pai e filho.

## ngModule

app/title/title.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.scss'],
})
export class TitleComponent implements OnInit {
  public nome = 'Dener';

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

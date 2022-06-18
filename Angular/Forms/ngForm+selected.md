Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngForm selected

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { FormsComponent } from "./forms/forms.component";
import { FormsModule } from "@angular/forms";

@NgModule({
  declarations: [FormsComponent],
  exports: [FormsComponent],
  // Aqui eu importei o FormsModule, eu já tinha importado no src/app/app.module.ts, mas não funcionou, tive que importar aqui, para funcionar o ngForm
  imports: [CommonModule, FormsModule],
})
export class SharedModule {}
```

src/app/shared/forms/forms.component.html

```js
<form #form="ngForm">
//...................................................................
  <!-- 1 Exemplo -->
  <!--
  <select name="comidas" ngModel>
    <option value="">Selecione um alimento</option>
    <option value="X-Salada">X-Salada</option>
    <option value="X-Bacon">X-Bacon</option>
    <option value="Coxinha">Coxinha</option>
  </select>
 -->
 //..................................................................
  <!-- 2 Exemplo, passando nosso array -->
  <select name="comidas" ngModel>
    <option value="">Selecione um alimento</option>

    <!-- [ngValue]="item", assim ele aceita um objeto-->
    <!-- [value]="item", assim, não aceita um objeto, aceita assim [object Object] -->

    <option *ngFor="let item of listComidas" [ngValue]="item">
      <!-- Mesma coisa -->
      <!-- <option *ngFor="let item of listComidas" [value]="item.comida"> -->
      {{ item.comida }} - {{ item.preco }}
    </option>
  </select>

  <br />
  <br />
</form>

{{ form.value | json }}

//<!-- ngModel, ajuda a passar os valores  -->
//<!-- #form="ngForm", (#form, estou recebendo os valores, ngForm, assim podendo trabalhar com ele) -->
//<!-- form.value, estou pegando todos os valores do meu form, ai ele vai referencia o valor de name="nome", que no caso aqui é nome -->
```

src/app/shared/forms/forms.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-forms',
  templateUrl: './forms.component.html',
  styleUrls: ['./forms.component.scss'],
})
export class FormsComponent implements OnInit {
  public listComidas: Array<{ comida: string; preco: string }> = [
    { comida: 'X-salada', preco: 'R$10,00' },
    { comida: 'X-bacon', preco: 'R$11,00' },
    { comida: 'Coxinha', preco: 'R$12,00' },
  ];

  constructor() {}

  ngOnInit(): void {}
}
```

src/app/app.component.html

```js
<app-forms></app-forms>
<router-outlet></router-outlet>
```

src/app/app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
})
export class AppComponent {
  title = "App1";
}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { SharedModule } from "./shared/shared.module";

@NgModule({
  declarations: [AppComponent],
  //Aqui foi importado o FormsModule, só que não funcionou, ngForm, importando somente aqui, ai foi testado se importar o formsModule no modulo, SharedModule, já funciona, nem precisa importar aqui, mas deixei importado aqui.
  imports: [BrowserModule, AppRoutingModule, FormsModule, SharedModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

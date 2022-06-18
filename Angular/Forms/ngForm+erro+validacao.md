Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngForm + erro

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
<!-- 1 Exemplo: Se for valid, aparece true, no caso o que eu digito
  dentro do input -->
<!-- valid -->
<!--
<form #form="ngForm">
  <label>
    Nome:
    <input type="text" name="nome" ngModel required />
  </label>
  form, ele trabalha com todos os elementos
  {{ form.valid }}
</form>
-->

<!-- 2 Exemplo: Exemplos de validação  -->
<!-- valid -->

<form #form="ngForm">
  <label>
    Nome:
    <!-- #nome="ngModel"
      [ngModel]="nome.value", pegando a referencia  -->
    <input
      type="text"
      name="nome"
      #nome="ngModel"
      [ngModel]="nome.value"
      required
    />
    <span *ngIf="!nome.valid && nome.dirty && nome.touched"> Invalid </span>
    <!-- *ngIf="nome.invalid" ou "!nome.valid" -->
  </label>

  <br />
  <br />
  <!-- nome, trabalha só com o elemento dele mesmo -->
  {{ nome.valid }}
  <!-- dirty, quando vai mudar de falso para true -->
  {{ nome.dirty }}
  <!-- touched, é quando você clica no formulário -->
  {{ nome.touched }}
</form>
```

src/app/shared/forms/forms.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-forms",
  templateUrl: "./forms.component.html",
  styleUrls: ["./forms.component.scss"],
})
export class FormsComponent implements OnInit {
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

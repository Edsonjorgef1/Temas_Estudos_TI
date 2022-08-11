Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngForm + input checkbox

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
  <label>
    Angular:
    <input type="checkbox" name="angular" value="Outros" ngModel />
  </label>
  <br />
  <br />

  <label>
    Vue:
    <input type="checkbox" name="vue" ngModel />
  </label>
  <br />
  <br />

  <label>
    React:
    <input type="checkbox" name="react" ngModel />
  </label>
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

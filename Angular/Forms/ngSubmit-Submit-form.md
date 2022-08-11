Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngSubmit - Submit form

Sempre quando o furmulário tiver um submit, devemos passar os dados dele, para o
nosso forms.componentes, ai consiguimos criar um serviço, dados para um serviço,
etc... Vamos enteder agora como fazer um submit

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
<!-- 1 Exemplo: Enviando nosso formulário  -->
<!-- valid -->

<form #form="ngForm" (ngSubmit)="submitForm(form)">
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
  <button [disabled]="form.invalid">Enviar dados</button>
</form>

{{ form.value | json }}
```

src/app/shared/forms/forms.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { NgForm } from '@angular/forms';

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

  public submitForm(form: NgForm) {
    //Se for valido nosso formulário, passo ele aqui dentro, do if
    if (form.valid) {
      //Aqui podemos enviar, estas informações para um back-end
      console.log(form.value);
    }
  }
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

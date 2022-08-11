Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Utilizando o Formulário

src/app/reactive-forms/reactive-forms.component.html

```js
<form [formGroup]="cadastroForm" (ngSubmit)="submitForm()">
  <input type="text" formControlName="firstName" />
  <br />
  <input type="text" formControlName="lastName" />
  <p>
    {{ cadastroForm.get("firstName")?.value }}
  </p>
  <p
    {{ cadastroForm.get("lastName")?.value }}
  </p>
  <button>Enviar</button>
</form>
```

src/app/reactive-forms/reactive-forms.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup } from '@angular/forms';

@Component({
  selector: 'app-reactive-forms',
  templateUrl: './reactive-forms.component.html',
  styleUrls: ['./reactive-forms.component.scss'],
})
export class ReactiveFormsComponent implements OnInit {
  public cadastroForm: FormGroup = this.formBuilder.group({
    firstName: [''],
    lastName: [''],
  });

  constructor(private formBuilder: FormBuilder) {}

  ngOnInit(): void {}

  public submitForm() {
    console.log(this.cadastroForm.value);
    console.log(this.cadastroForm.value.firstName);
    console.log(this.cadastroForm.value.lastName);
  }
}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
//Importei o ReactiveFormsModule
import { ReactiveFormsModule } from "@angular/forms";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { ReactiveFormsComponent } from "./reactive-forms/reactive-forms.component";

@NgModule({
  declarations: [AppComponent, ReactiveFormsComponent],
  //Importei o ReactiveFormsModule
  imports: [BrowserModule, AppRoutingModule, ReactiveFormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

src/app/app.component.html

```js
<app-reactive-forms></app-reactive-forms>
<router-outlet></router-outlet>
```

src/app/app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `<router-outlet></router-outlet> `,
})
export class AppComponent {
  title = "reactive-forms";
}
```

src/app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";

//Componentes
import { ReactiveFormsComponent } from "./reactive-forms/reactive-forms.component";

const routes: Routes = [
  {
    path: "",
    component: ReactiveFormsComponent,
  },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

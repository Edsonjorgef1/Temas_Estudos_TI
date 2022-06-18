Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Valid e Invalid

src/app/reactive-forms/reactive-forms.component.html

```js
<form [formGroup]="cadastroForm" (ngSubmit)="submitForm()">
  <input type="text" formControlName="firstName" />
  <br />
  <input type="text" formControlName="lastName" />

  <!-- Obs: Aonde está o nome firstName, não colocar aspas duplas, porque da erro, utilizar aspas simples -->
  <span
    class="alert"
    *ngIf="
      cadastroForm.get('firstName')?.errors &&
      cadastroForm.get('firstName')?.touched &&
      cadastroForm.get('firstName')?.dirty
    "
  >
    Favor adicionar o nome
  </span>

  <p>
    {{ cadastroForm.get("firstName")?.errors | json }}
  </p>

  <p>
    {{ cadastroForm.get("firstName")?.touched | json }}
  </p>

  <p>
    {{ cadastroForm.get("firstName")?.dirty | json }}
  </p>

  <button [disabled]="cadastroForm.invalid">Enviar</button>
</form>
```

src/app/reactive-forms/reactive-forms.component.scss

```js
.alert {
  color: white;
  background-color: red;
}
```

src/app/reactive-forms/reactive-forms.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'app-reactive-forms',
  templateUrl: './reactive-forms.component.html',
  styleUrls: ['./reactive-forms.component.scss'],
})
export class ReactiveFormsComponent implements OnInit {
  cadastroForm: FormGroup = this.formBuilder.group({
    //required, quer dizer que só vai ser submitido, se tiver algum valor neste campo
    firstName: ['', Validators.required],
    lastName: [''],
  });

  constructor(private formBuilder: FormBuilder) {}

  ngOnInit(): void {}
  public submitForm() {
    //Se for valido faça isso, se não ai ele não faz nada
    if (this.cadastroForm.valid) {
      //Aqui poderia enviar paramentros para o back-end, metodo post, get etc..
      console.log(this.cadastroForm.value);
      console.log(this.cadastroForm.value.firstName);
      console.log(this.cadastroForm.value.lastName);
    }
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

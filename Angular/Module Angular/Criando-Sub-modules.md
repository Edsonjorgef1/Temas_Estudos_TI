Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando Sub Modules

```js
ng g m shared
```

## Criando um submodulo já com rotas filhas, caso precise

```js
ng g m shared --routing
```

Criar um componete agora a minha pasta shared

```js
ng g c shared/newComponent
```

src/app/shared/new-component/new-component.component.html

```js
<header>
  <h1>Header do App</h1>
</header>
```

src/app/shared/new-component/new-component.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-new-component",
  templateUrl: "./new-component.component.html",
  styleUrls: ["./new-component.component.scss"],
})
export class NewComponentComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";

@NgModule({
  //Aqui e o nome, que foi importado automatico depois de criado o componente
  declarations: [NewComponentComponent],
  //Exportando o componente, aqui deve fazer manual, pois ele n]ao faz automático
  exports: [NewComponentComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

## Agora vamos criar um arquivo, na pasta shared

Repare que depois que criar o arquivo ja irá importar o componente criado dentro
do src/app/shared/shared.module.ts src/app/shared/shared.module.ts

Criar um componete agora a minha pasta shared

```js
ng g c shared/input
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [NewComponentComponent, InputComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz
  exports: [NewComponentComponent, InputComponent],
  imports: [CommonModule],
})
//Este nome SharedModule, ele é importado depois no app.module.ts o modulo principal
export class SharedModule {}
```

src/app/shared/input/input.component.html

```js
<p>inputCriado Parabéns</p>
```

src/app/shared/input/input.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-input",
  templateUrl: "./input.component.html",
  styleUrls: ["./input.component.scss"],
})
export class InputComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/app.module.ts

Modulo principal

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { SharedModule } from "./shared/shared.module";

@NgModule({
  declarations: [AppComponent],
  //Repare que foi importado o nome, SharedModule e dentro deste module tem outros componentes criados
  //Também deve, importar o FormsModule, para que o ngModule que está dentro do shared.module.ts funcione
  imports: [BrowserModule, AppRoutingModule, FormsModule, SharedModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

src/app/app.component.html

```js
 //Este nome que está sendo importado, ele é o nome do selector do componente, no caso src/app/shared/new-component/new-component.component.ts, assim você irá ver o que foi feito dentro deste componente, no html
<app-new-component></app-new-component>
// Este outro é a mesma coisa só que é o input
<app-input></app-input>
```

## Podemos fazer de outra forma, sem precisar importar o modulo, no app.module principal

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [NewComponentComponent, InputComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz
  exports: [NewComponentComponent, InputComponent],
  imports: [CommonModule],
})
//Este nome SharedModule, ele é importado depois no app.module.ts o modulo principal
export class SharedModule {}
```

Depois de criado o modulo, basta criar um arquivo dentro da pasta shared,
index.js

src/app/shared/index.js

```js
export * from "./calculadora.module";
```

Pronto assim, temos nosso modulo público, para importar de onde quisermos.

src/app/app.module.ts

Modulo principal

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { SharedModule } from "./shared/shared.module";

@NgModule({
  declarations: [AppComponent],
  //Repare que foi importado o nome, SharedModule e dentro deste module tem outros componentes criados
  //Também deve, importar o FormsModule, para que o ngModule que está dentro do shared.module.ts funcione
  imports: [BrowserModule, AppRoutingModule, FormsModule, SharedModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

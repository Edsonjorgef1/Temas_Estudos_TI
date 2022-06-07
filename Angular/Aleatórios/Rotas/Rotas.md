Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Rotas

Gerando um projeto já com rotas

```js
ng new app-angular --routing
```

Depois de criado o projeto ele já cria um arquivo chamado

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";

//Aqui vamos definir as nossas rotas
const routes: Routes = [];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";
// Aqui ele já importo a rota automático, depois de criado o projeto
import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

Agora vamos criar um componente para a pagina01

```js
ng g c pagina01
```

Agora vamos criar um componente para a pagina02

```js
ng g c pagina02
```

## Agora vamos definir a nossa rota no arquivo

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { Pagina01Component } from "./pagina01/pagina01.component";
import { Pagina02Component } from "./pagina02/pagina02.component";

const routes: Routes = [
  //Referenciando a pagina01, depois ele importa automático a pagina01
  {
    path: "pagina01",
    component: Pagina01Component,
  },
  //Referenciando a pagina02, depois ele importa automático a pagina02
  { path: "pagina02", component: Pagina02Component },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

Agora vamos, fazer que quando clicamos na Pagina01 vá para a Pagina01 e quando
clicamos na Pagina02 vá para a Pagina02

app/app.component.html

```js
<div>
  <!-- Estamos utilizando a própria rota do angular,
  o routerLink, depois só referenciar o link como deseja -->
  <a routerLink="/pagina01">Página 1</a>
  <br />
  <a routerLink="/pagina02">Página 2</a>
  <br />
  <!-- Ou podes utilizar o botão -->
  <button routerLink="/pagina01">Página 1</button>
  <button routerLink="/pagina02">Página 2</button>
</div>
<!-- Ou -->
<nav>
  <ul>
    <li>
      <a routerLink="/pagina01">Página 1</a>
      <br />
      <a routerLink="/pagina02">Página 2</a>
    </li>
  </ul>
</nav>

<!-- Aqui estamos referenciando a rota, para funcionar-->
<router-outlet></router-outlet>
```

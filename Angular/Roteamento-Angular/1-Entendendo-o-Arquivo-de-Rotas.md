Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Entendendo o arquivo de Rotas

Gerando um projeto já com rotas

```js
ng new app-angular --routing
```

ou

Quando você gera o projeto, ele irá perguntar se você quer gerar o projeto com
rota ai você colocar y

```js
ng new app-angular
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

Agora vamos criar um componente para a home

```js
ng g c pages/home
```

Agora vamos criar um componente para sobre

```js
ng g c pages/sobre
```

Agora vamos criar um componente para pageError

```js
ng g c pages/pageError
```

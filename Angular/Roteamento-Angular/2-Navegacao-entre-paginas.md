Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando rotas

## Agora vamos definir a nossa rota no arquivo

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { HomeComponent } from "./pages/home/home.component";
import { PageErrorComponent } from "./pages/page-error/page-error.component";
import { SobreComponent } from "./pages/sobre/sobre.component";

const routes: Routes = [
  //Se nosso path, for "", vazio temos que colocar o pathMatch: 'full', para evitar que o angular renderize coisas amais
  { path: "", component: HomeComponent, pathMatch: "full" },

  //Referenciando a sobre, depois ele importa automático a sobre
  { path: "sobre", component: SobreComponent },

  //Referenciando a 404, depois ele importa automático a 404
  { path: "404", component: PageErrorComponent },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

## Quando clicarmos vamos para a proxima página

app/app.component.html

```js
<div>
  <!-- Estamos utilizando a própria rota do angular,
  o routerLink, depois só referenciar o link como deseja -->
  <a routerLink="/sobre">Página Sobre</a>
  <br />
  <a routerLink="/404">Error</a>
  <br />
  <!-- Ou podes utilizar o botão -->
  <button routerLink="/sobre">Página Sobre</button>
  <button routerLink="/404">Error</button>
</div>
<!-- Ou -->
<nav>
  <ul>
    <li>
      <a routerLink="/sobre">Página Sobre</a>
      <br />
      <a routerLink="/404">Error</a>
     <!-- Rota parametrizada /404/5 -->
        <a routerLink="['/404', 5']">Error</a>

    </li>
  </ul>
</nav>

//   Errado utilizar este metodo com href, muito lerdo, tem que ser utilizado o routerLink do angular. <a href="/sobre">Sobre</a>

<!-- Aqui estamos referenciando a rota, para funcionar-->
<router-outlet></router-outlet>
```

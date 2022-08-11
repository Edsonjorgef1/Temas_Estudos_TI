Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Rota coringa + redirectTo

src/app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { HomeComponent } from "./pages/home/home.component";
import { PageErrorComponent } from "./pages/page-error/page-error.component";
import { SobreComponent } from "./pages/sobre/sobre.component";

const routes: Routes = [
  { path: "", component: HomeComponent, pathMatch: "full" },
  { path: "sobre", component: SobreComponent },
  { path: "404", component: PageErrorComponent },
  //Quando acessar uma rota errada, irá cair em uma rota coringa e podemos
  //renderizar um componente, no caso renderizamos o error
  // { path: '**', component: PageErrorComponent },
  //Outro exemplo do coringa, metodo mais atual
  { path: "**", redirectTo: "404" },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

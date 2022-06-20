Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Parametro nas rotas

src/app/pages/sobre/sobre.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-sobre',
  templateUrl: './sobre.component.html',
  styleUrls: ['./sobre.component.scss'],
})
export class SobreComponent implements OnInit {
  constructor(private activatedRoute: ActivatedRoute) {}

  ngOnInit(): void {
    this.activatedRoute.params.subscribe((res) =>
      console.log(res['id'], res['username'], res)
    );
    // pegando informações: ?nome=123&sobrenome=teste
    this.activatedRoute.queryParams.subscribe((res) => console.log(res));
  }
}
```

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { HomeComponent } from "./pages/home/home.component";
import { PageErrorComponent } from "./pages/page-error/page-error.component";
import { SobreComponent } from "./pages/sobre/sobre.component";

const routes: Routes = [
  { path: "", component: HomeComponent, pathMatch: "full" },
  { path: "sobre/:id/:username", component: SobreComponent },
  { path: "404", component: PageErrorComponent },
  { path: "**", redirectTo: "404" },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

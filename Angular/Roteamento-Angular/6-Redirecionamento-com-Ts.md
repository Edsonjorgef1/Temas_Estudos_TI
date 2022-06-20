Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Redirecionamento com Ts

src/app/pages/sobre/sobre.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute, Router } from '@angular/router';

@Component({
  selector: 'app-sobre',
  templateUrl: './sobre.component.html',
  styleUrls: ['./sobre.component.scss'],
})
export class SobreComponent implements OnInit {
  constructor(private activatedRoute: ActivatedRoute, private router: Router) {}

  ngOnInit(): void {
    this.activatedRoute.params.subscribe((res) =>
      console.log(res['id'], res['username'], res)
    );
    // pegando informações: ?nome=123&sobrenome=teste
    this.activatedRoute.queryParams.subscribe((res) => console.log(res));

    setInterval(() => {
      // navigate, mais navegação interna
      //this.router.navigate(['404']);
      //navigateByUrl, quando for mandar para outra pagina
      this.router.navigateByUrl('404');
    }, 5000);
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

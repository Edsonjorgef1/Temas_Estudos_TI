Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Lasy Loading

É um carregamento tardio, ganha mais performace, ele carrega somente o arquivo
especifico

Primeiro temos que criar um modulo

```js
ng g m dashboard
```

src/app/dashboard/dashboard.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { HomeComponent } from "./pages/home/home.component";
import { DashboardRoutingModule } from "./dashboard-routing.module";

@NgModule({
  declarations: [HomeComponent],
  imports: [CommonModule, DashboardRoutingModule],
})
export class DashboardModule {}
```

Criar um arquivo dentro

src/app/dashboard/dasboard-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
//Dashboard
import { HomeComponent } from "./pages/home/home.component";

const routes: Routes = [
  {
    path: "",
    component: HomeComponent,
  },
];

@NgModule({
  //Aqui foi trocado para forChild, filho
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule],
})
export class DashboardRoutingModule {}
```

src/app/pages/home/home.component.html

```js
<p>Dashboard</p>
```

src/app/pages/home/home.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-home",
  templateUrl: "./home.component.html",
  styleUrls: ["./home.component.scss"],
})
export class HomeComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/pages/home/home.component.html

```js
<p>home works!</p>
```

src/app/pages/home/home.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-home",
  templateUrl: "./home.component.html",
  styleUrls: ["./home.component.scss"],
})
export class HomeComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/pages/page-error/page-error.component.html

```js
<p>page-error works!</p>
```

src/app/pages/page-error/page-error.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-page-error",
  templateUrl: "./page-error.component.html",
  styleUrls: ["./page-error.component.scss"],
})
export class PageErrorComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/pages/sobre/sobre.component.html

```js
<p>sobre works!</p>
```

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

src/app/shared/menu/menu.component.html

```js
<header>
  <nav>
    <ul>
      <li>
        <a
          routerLink="/"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Home</a
        >
      </li>
      <li>
        <a
          routerLink="/sobre"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Sobre</a
        >
      </li>

      <li>
        <a
          routerLink="/dashboard"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Dashboard</a
        >
      </li>

      <li>
        <a
          routerLink="['/404']"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Errorsss</a
        >
      </li>
    </ul>
  </nav>
</header>
```

src/app/shared/menu/menu.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-menu",
  templateUrl: "./menu.component.html",
  styleUrls: ["./menu.component.scss"],
})
export class MenuComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { HomeComponent } from "./pages/home/home.component";
import { PageErrorComponent } from "./pages/page-error/page-error.component";
import { SobreComponent } from "./pages/sobre/sobre.component";

const routes: Routes = [
  { path: "", component: HomeComponent, pathMatch: "full" },
  {
    path: "sobre",
    component: SobreComponent,
    children: [{ path: "beto", component: SobreComponent }],
    // /sobre/beto
  },
  {
    path: "dashboard",
    loadChildren: () =>
      import("./dashboard/dashboard-routing.module").then(
        m => m.DashboardRoutingModule
      ),
  },
  { path: "404", component: PageErrorComponent },
  { path: "**", redirectTo: "404" },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

src/app/app-component.html

```js
<app-menu></app-menu>
<router-outlet></router-outlet>
```

src/app/app-component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
})
export class AppComponent {
  title = "routes";
}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
//Pages
import { HomeComponent } from "./pages/home/home.component";
import { SobreComponent } from "./pages/sobre/sobre.component";
import { PageErrorComponent } from "./pages/page-error/page-error.component";
import { MenuComponent } from "./shared/menu/menu.component";

@NgModule({
  declarations: [
    AppComponent,
    HomeComponent,
    SobreComponent,
    PageErrorComponent,
    MenuComponent,
  ],
  imports: [BrowserModule, AppRoutingModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

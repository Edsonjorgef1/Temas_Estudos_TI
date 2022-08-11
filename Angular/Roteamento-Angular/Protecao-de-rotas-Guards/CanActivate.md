Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## CanActivate

Decide se uma rota (ou componente) pode ser ativada, como um sistema de login.

Primeiro criar um componente shared

```js
ng g c shared
```

```js
ng g c shared/account
```

```js
ng g c shared/guards
```

```js
ng g c shared/home
```

```js
ng g guard shared/guards/canActive
```

Escolha a opção:

CanActivate (x)

CanActivateChild

CanDeactivate

CanLoad

Ele ira gera dois arquivos

src/app/shared/can-active.guard.spec.ts

```js
import { TestBed } from "@angular/core/testing";

import { CanActiveGuard } from "./can-active.guard";

describe("CanActiveGuard", () => {
  let guard: CanActiveGuard;

  beforeEach(() => {
    TestBed.configureTestingModule({});
    guard = TestBed.inject(CanActiveGuard);
  });

  it("should be created", () => {
    expect(guard).toBeTruthy();
  });
});
```

src/app/shared/can-active.guard.ts

```js
import { Injectable } from "@angular/core";
import {
  ActivatedRouteSnapshot,
  CanActivate,
  RouterStateSnapshot,
  UrlTree,
} from "@angular/router";
import { Observable } from "rxjs";

@Injectable({
  providedIn: "root",
})
//Ele fica verificando, validações quando sai da rota em si
export class CanActiveGuard implements CanActivate {
  canActivate(
    route: ActivatedRouteSnapshot,
    state: RouterStateSnapshot
  ):
    | Observable<boolean | UrlTree>
    | Promise<boolean | UrlTree>
    | boolean
    | UrlTree {
    //False já esta indo para nossa pagina principal Home
    if (
      route.queryParams["account"] === "admin" &&
      route.queryParams["password"] === "1234"
    ) {
      console.log(route);
      console.log(state);
      return true;
    }
    console.log(route);
    console.log(state);
    return false;
  }
}
```

src/app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";

//Component Pages
import { HomeComponent } from "./shared/home/home.component";
import { AccountComponent } from "./shared/account/account.component";

//Guards
import { CanActiveGuard } from "./shared/guards/can-active.guard";

const routes: Routes = [
  {
    path: "",
    component: HomeComponent,
    canActivate: [CanActiveGuard],
  },
  {
    path: "account",
    component: AccountComponent,
  },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

src/app/shared/home.component.html

```js
<a routerLink="account" [queryParams]="{ account: 'admin', password: '1234' }">
  Account True
</a>
<br />
<a routerLink="account" [queryParams]="{ account: 'admm', password: '123444' }">
  Account False
</a>

<h1>Home</h1>
```

src/app/shared/home.component.ts

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

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Service Injeção de Dependencia

Quando vamos utilizar este serviço, salvar informações que vem do servidor, get,
post, put, delete, atualiza informações, emiti dados para outro componente,
coisas com serviços, pegar dados de uma api, consegue pegar e observar reações
dentro de um serviço.

## Criando nosso service

```js
ng g s \gerandoDentroDesteDiretório\nomeDoService
```

Aqui está sem o arquivo para teste unitário

```js
ng g s \users\users --spec=false
```

ou Com o arquivo para teste unitário

```js
ng g s \users\user
```

## Arquivo Criado

app/usersuser.service.ts

```js
import { Injectable } from "@angular/core";

@Injectable({
  providedIn: "root",
})
export class UsersuserService {
  constructor() {}
}
```

## Inicio para o desenvolvimento

## Criando nosso service

```js
ng g s \gerandoDentroDesteDiretório\nomeDoService
```

```js
ng g s service\FoodList
```

src/app/service/food-list.service.ts

```js
import { Injectable } from '@angular/core';

@Injectable({
  //Pegar informações apartir deste provideIn
  providedIn: 'root',
})
//Quem tem acesso a esta lista privada, FoodListService
export class FoodListService {
  // Lista privada
  private list: Array<string> = ['X Bacon', 'Feijão', 'Ovo'];
  constructor() {}
  public foodList() {
    return this.list;
  }
}
```

Criando Sub Modules

```js
ng g m shared
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { FoodListComponent } from "./food-list/food-list.component";

@NgModule({
  declarations: [FoodListComponent],

  exports: [FoodListComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

Criando nosso componente

```js
ng g c shared/food-list
```

src/app/shared/food-list/food-list.component.html

```js
<li *ngFor="let item of foodList">
  {{ item }}
</li>
```

src/app/shared/food-list/food-list.component.ts

```js
import { Component, OnInit } from '@angular/core';
//Services
import { FoodListService } from 'src/app/service/food-list.service';

@Component({
  selector: 'app-food-list',
  templateUrl: './food-list.component.html',
  styleUrls: ['./food-list.component.scss'],
})
export class FoodListComponent implements OnInit {
  public foodList: Array<string> = [];

  constructor(private foodListService: FoodListService) {
    // Este métdo também da certo, mas fica muito grande o código
    // let list = new FoodListService();
    // this.foodList = list.foodList();
  }

  ngOnInit(): void {
    // Metodo mais organizado
    this.foodList = this.foodListService.foodList();
  }
}
```

src/app/app.component.html

```js
<app-food-list></app-food-list>
<router-outlet></router-outlet>
```

src/app/app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
})
export class AppComponent {}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { FoodListComponent } from "./shared/food-list/food-list.component";

@NgModule({
  declarations: [AppComponent, FoodListComponent],
  imports: [BrowserModule, AppRoutingModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

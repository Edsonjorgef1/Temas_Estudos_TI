Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Subscribe

A partir que eu emitir este evento, eu vou trabalhar com subscribe e sempre
quando este evento fizer alguma coisa, o meu subscribe vai estar lá retornando o
dado, toda vez que você se inscreve ele vai ficar funcionando até ele terminar
sua ações, no caso quando você pega as informações a partir de uma api, tem que
se inscrever também em uma funcionalidade ou em um evento, apartir disso quando
se inscrevermos em um evento, ele irá ficar vendo se tem alguma informação nova,
algum dado novo, e ele sempre nos trara coisas novas. Este evento quando for
ativado deverá ser resgatado em algum lugar, ai deverá ficar ouvindo, alguma
manipulação de algum dado, algum adicionamento.

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";

//Componentes
import { FoodAddComponent } from "./food-add/food-add.component";
import { FoodListComponent } from "./food-list/food-list.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [FoodAddComponent, FoodListComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz
  exports: [FoodAddComponent, FoodListComponent],
  imports: [CommonModule],
})
//Este nome SharedModule, ele é importado depois no app.module.ts o modulo principal
export class SharedModule {}
```

src/app/services/food-list.service.ts

```js
import { EventEmitter, Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class FoodListService {
  public emitEvent = new EventEmitter();

  private list: Array<string> = ['X Bacon', 'Feijão', 'Ovo'];

  constructor() {}

  public foodList() {
    return this.list;
  }
  public foodListAdd(value: string) {
    this.foodListAlert(value);
    return this.list.push(value);
  }

  public foodListAlert(value: string) {
    return this.emitEvent.emit(value);
  }
}
```

src/app/shared/food-add/food-add.component.html

```js
<input #inputValue />
<button (click)="listAddItem(inputValue.value)">Add Item</button>
```

src/app/shared/food-add/food-add.component.ts

```js
import { Component, OnInit } from '@angular/core';
//Services
import { FoodListService } from 'src/app/services/food-list.service';

@Component({
  selector: 'app-food-add',
  templateUrl: './food-add.component.html',
  styleUrls: ['./food-add.component.scss'],
})
export class FoodAddComponent implements OnInit {
  constructor(private foodListService: FoodListService) {}

  ngOnInit(): void {}

  public listAddItem(value: string) {
    return this.foodListService.foodListAdd(value);
    // console.log(value);
  }
}
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
import { FoodListService } from 'src/app/services/food-list.service';

@Component({
  selector: 'app-food-list',
  templateUrl: './food-list.component.html',
  styleUrls: ['./food-list.component.scss'],
})
export class FoodListComponent implements OnInit {
  public foodList: Array<string> = [];

  //Estou adicionando nosso FooodListService,
  constructor(private foodListService: FoodListService) {
    //Estas duas linhas é a mesma coisa que private foodListService: FoodListService, desta forma acima é mais resumido
    // let list = new FoodListService();
    // this.foodList = list.foodList();
  }

  ngOnInit(): void {
    this.foodList = this.foodListService.foodList();

    //Sempre quando emitEvent estiver ativo eu vou se inscrever
    this.foodListService.emitEvent.subscribe((res: any) =>
      alert(`Olha você add => ${res}`)
    );
  }
}
```

src/app/app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.scss"],
})
export class AppComponent {
  title = "App1";
}
```

src/app/app.component.html

```js
<app-food-list></app-food-list>
<app-food-add></app-food-add>
<router-outlet></router-outlet>
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";
import { SharedModule } from "./shared/shared.module";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule, FormsModule, SharedModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

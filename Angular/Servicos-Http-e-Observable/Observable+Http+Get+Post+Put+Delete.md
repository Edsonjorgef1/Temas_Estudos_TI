Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Observable + Http-Get

!Verificar código!

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { HttpClientModule } from "@angular/common/http";

//Componentes
import { FoodListComponent } from "./food-list/food-list.component";
import { FoodAddComponent } from "./food-add/food-add.component";
import { FormsModule } from "@angular/forms";

@NgModule({
  declarations: [FoodListComponent, FoodAddComponent],
  exports: [FoodListComponent, FoodAddComponent],
  //Importamos o HttpClientModule
  imports: [CommonModule, HttpClientModule, FormsModule],
})
export class SharedModule {}
```

src/app/services/food-list.service.ts

```js
import { HttpClient } from '@angular/common/http';
import { EventEmitter, Injectable } from '@angular/core';
import { Observable } from 'rxjs';
import { FoodList } from '../module/food-list';

@Injectable({
  providedIn: 'root',
})
export class FoodListService {
  public emitEvent = new EventEmitter();

  private list: Array<string> = ['X Bacon', 'Feijão', 'Ovo'];

  private url: string = 'https://localhost:3000/'; //list-food

  constructor(private http: HttpClient) {}

  public foodList(): Observable<Array<FoodList>> {
    return this.http.get<Array<FoodList>>(`${this.url}list-food`).pipe(
      (res) => res,
      (error) => error
    );
  }

  //Add
  public foodListAdd(value: string): Observable<FoodList> {
    return this.http
      .post<FoodList>(`${this.url}list-food`, { nome: value })
      .pipe(
        (res) => res,
        (error) => error
      );
  }

  //Edit
  public foodListEdit(value: string, id: number): Observable<FoodList> {
    return this.http
      .put<FoodList>(`${this.url}list-food/${id}`, { nome: value })
      .pipe(
        (res) => res,
        (error) => error
      );
  }

  //Delete
  public foodListDelete(id: number): Observable<FoodList> {
    return this.http.delete<FoodList>(`${this.url}list-food/${id}`).pipe(
      (res) => res,
      (error) => error
    );
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
    return this.foodListService.foodListAdd(value).subscribe(
      (res) => res,
      (error) => error
    );
    // console.log(value);
  }
}
```

src/app/shared/food-list/food-list.component.html

```js
<li *ngFor="let item of foodList">
  {{ item.id }} -
  <input
    type="text"
    [(ngModel)]="item.nome"
    (keyup.enter)="foodListEdit(item.nome, item.id)"
  />
  <button (click)="foodListDelete(item.id)">Deletar</button>
</li>
```

src/app/shared/food-list/food-list.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { FoodList } from 'src/app/module/food-list';
//Services
import { FoodListService } from 'src/app/services/food-list.service';

@Component({
  selector: 'app-food-list',
  templateUrl: './food-list.component.html',
  styleUrls: ['./food-list.component.scss'],
})
export class FoodListComponent implements OnInit {
  public foodList: Array<FoodList> = [];

  //Estou adicionando nosso FooodListService,
  constructor(private foodListService: FoodListService) {
    //Estas duas linhas é a mesma coisa que private foodListService: FoodListService, desta forma acima é mais resumido
    // let list = new FoodListService();
    // this.foodList = list.foodList();
  }

  ngOnInit(): void {
    this.foodListService.foodList().subscribe(
      (res) => (this.foodList = res),
      (error) => console.log(error)
    );
    this.foodListService.emitEvent.subscribe(res) =>
      alert(`Olha você add => ${res.nome}`
      return this.foodList.push(res)



  public foodListEdit(value: string, id: number){
    this.foodListService.foodListEdit(value, id).subscribe(
      res => {
        return console.log(res)
      },
      error => error
    )
  }


  public foodListDelete(id: number) {
    return this.foodListService.foodListDelete(id).subscribe(
      (res) => {
        this.foodList = this.foodList.filter((item) => {
          return id !== item.id;
        }
        );
      },
      (error) => error
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

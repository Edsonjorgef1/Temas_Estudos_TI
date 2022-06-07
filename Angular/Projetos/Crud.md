Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Crud

Api que vamos utilizarm, está api fake

```js
https://reqres.in
```

Vamos utilizar a api fake, LIST USERS, metodo Get, que está no site, aonde ela
tem uma api Request, aonde temos que apontar, que é _/api/users?page=2_ e irá
retornar uma lista de usuarios, que está abaixo.

```js
{
    "page": 2,
    "per_page": 6,
    "total": 12,
    "total_pages": 2,
    "data": [
        {
            "id": 7,
            "email": "michael.lawson@reqres.in",
            "first_name": "Michael",
            "last_name": "Lawson",
            "avatar": "https://reqres.in/img/faces/7-image.jpg"
        },
        {
            "id": 8,
            "email": "lindsay.ferguson@reqres.in",
            "first_name": "Lindsay",
            "last_name": "Ferguson",
            "avatar": "https://reqres.in/img/faces/8-image.jpg"
        },
        {
            "id": 9,
            "email": "tobias.funke@reqres.in",
            "first_name": "Tobias",
            "last_name": "Funke",
            "avatar": "https://reqres.in/img/faces/9-image.jpg"
        },
        {
            "id": 10,
            "email": "byron.fields@reqres.in",
            "first_name": "Byron",
            "last_name": "Fields",
            "avatar": "https://reqres.in/img/faces/10-image.jpg"
        },
        {
            "id": 11,
            "email": "george.edwards@reqres.in",
            "first_name": "George",
            "last_name": "Edwards",
            "avatar": "https://reqres.in/img/faces/11-image.jpg"
        },
        {
            "id": 12,
            "email": "rachel.howell@reqres.in",
            "first_name": "Rachel",
            "last_name": "Howell",
            "avatar": "https://reqres.in/img/faces/12-image.jpg"
        }
    ],
    "support": {
        "url": "https://reqres.in/#support-heading",
        "text": "To keep ReqRes free, contributions towards server costs are appreciated!"
    }
}
```

## Agora vamos criar o nosso projeto já com rotas e configurar

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Rotas

Gerando um projeto já com rotas

```js
ng new app-angular --routing
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

Agora vamos criar um componente para a pagina01

```js
ng g c pagina01
```

Agora vamos criar um componente para a pagina02

```js
ng g c pagina02
```

## Agora vamos definir a nossa rota no arquivo

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { Pagina01Component } from "./pagina01/pagina01.component";
import { Pagina02Component } from "./pagina02/pagina02.component";

const routes: Routes = [
  //Referenciando a pagina01, depois ele importa automático a pagina01
  {
    path: "pagina01",
    component: Pagina01Component,
  },
  //Referenciando a pagina02, depois ele importa automático a pagina02
  { path: "pagina02", component: Pagina02Component },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

Agora vamos, fazer que quando clicamos na Pagina01 vá para a Pagina01 e quando
clicamos na Pagina02 vá para a Pagina02

app/app.component.html

```js
<div>
  <!-- Estamos utilizando a própria rota do angular,
  o routerLink, depois só referenciar o link como deseja -->
  <a routerLink="/pagina01">Página 1</a>
  <br />
  <a routerLink="/pagina02">Página 2</a>
  <br />
  <!-- Ou podes utilizar o botão -->
  <button routerLink="/pagina01"></button>
  <button routerLink="/pagina02"></button>
</div>

<!-- Aqui estamos referenciando a rota, para funcionar-->
<router-outlet></router-outlet>
```

## Vamos criar um componente chamado users

```js
ng g c users
```

Agora vamos incluir nosso componente users, para funcionar a rota

app/app-routing.module.ts

```js
import { NgModule } from "@angular/core";
import { RouterModule, Routes } from "@angular/router";
import { Pagina01Component } from "./pagina01/pagina01.component";
import { Pagina02Component } from "./pagina02/pagina02.component";
import { UsersComponent } from "./users/users.component";

const routes: Routes = [
  {
    path: "pagina01",
    component: Pagina01Component,
  },
  { path: "pagina02", component: Pagina02Component },
  // Importando o componente users, para funcionar a rota
  { path: "users", component: UsersComponent },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
```

## Vamos agora criar nosso service

Service ele é responsável em fazer a comunicação dos nossos end point la na api
que vamos usar

## Criando nosso service

```js
ng g s \gerandoDentroDesteDiretório\nomeDoService --spec=false
```

Aqui está sem o arquivo para teste unitário

```js
ng g s \users\users --spec=false
```

ou Com o arquivo para teste unitário

```js
ng g s \users\user
```

Agora vamos criar um arquivo, direto no vscode

```js
user.model.ts;
```

Agora vamos converter o arquivo json do site, que urilizamos

```js
https://reqres.in
```

site para converter o json

```js
http://json2ts.com/
```

Depois de gerado copia e cola, dentro do arquivo user model

app/user.model.ts

```js
export interface User {
  id: number;
  email: string;
  first_name: string;
  last_name: string;
  avatar: string;
}
// Objeto de resposta, aonde trás o get de muitos registros

export interface ResponseUsers {
  page: number;
  per_page: number;
  total: number;
  total_pages: number;
  data: User[];
}
```

Depois vamos editar nosso arquivo

app/users/usersuser.service.ts

```js
import { Injectable } from '@angular/core';
import { Observable } from 'rxjs';
import { ResponseUsers } from './user.model';
import { HttpClient } from '@angular/common/http';

@Injectable({
  providedIn: 'root',
})
export class UsersuserService {
  // Url da nossa api
  private url = 'https://reqres.in/api/users';

  constructor(private http: HttpClient) {}

  // ResponseUsers, foi aonde referenciamos em nossa api, user.model.ts
  // Observable, ele chama e fica observando
  // Quando chamarmos o getUsers, ficamos aguardando o retorno, e quando der o retorno vamos fazer alguma coisa
  getUsers(): Observable<ResponseUsers> {
    return this.http.get<ResponseUsers>(this.url);
  }
}
```

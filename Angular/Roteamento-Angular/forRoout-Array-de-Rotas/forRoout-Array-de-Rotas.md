## forRoout-Array-de-Rotas

Aqui irei explicar como funciona o forRout um array de rotas, você deve navagear entre as paginas

app/app.component.html

```js
<div class="wrapper">
  <mt-header></mt-header>
  <!-- Full Width Column -->
  <div class="content-wrapper">
    <div class="container">
      <router-outlet></router-outlet> <!-- Aqui foi adicionado o router-outLet, para que possa navegar entre as paginas-->
    </div>
  </div>

  <!-- snakbar deve ser aqui -->
  <footer class="main-footer">
    <div class="container">
      <div class="pull-right hidden-xs"><b>Version</b> 1.0.0</div>
      <strong>Meat</strong> Angular Application
    </div>
  </footer>
</div>
```

app/app.routes.ts

```js
import { Routes } from "@angular/router";
import { AboutComponent } from "./about/about.component";
import { HomeComponent } from "./home/home.component";
import { RetaurantsComponent } from "./retaurants/retaurants.component";

export const ROUTES: Routes = [
  { path: "", component: HomeComponent },
  { path: "restaurants", component: RetaurantsComponent },
  { path: "about", component: AboutComponent },
];
```

app/app.module.ts

```js
import { BrowserModule } from "@angular/platform-browser";
import { NgModule } from "@angular/core";
import { HttpModule } from "@angular/http";
import { RouterModule } from "@angular/router";

import { ROUTES } from "./app.routes"; // Deve importar aqui o ROUTES, repare que estou importado o arquivo app.routes aonde está o path que são minhas rotas

import { AppComponent } from "./app.component";
import { HeaderComponent } from "./header/header.component";
import { HomeComponent } from "./home/home.component";
import { AboutComponent } from "./about/about.component";
import { RetaurantsComponent } from './retaurants/retaurants.component';

@NgModule({
  declarations: [AppComponent, HeaderComponent, HomeComponent, AboutComponent, RetaurantsComponent],
  imports: [BrowserModule, HttpModule, RouterModule.forRoot(ROUTES)], // Passando meu array de rotas, RouterModule.forRoot(ROUTES)],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

.......................................................................

app/about/about.component.html

```js
<!-- INÍCIO DO CONTEÚDO -->
<section class="content-header">
  <h1>Sobre</h1>
</section>

<section class="content">
  <p class="lead">Meat | Aplicação que demonstra as features do Angular</p>
  <p class="lead">MIT license</p>
  <p class="lead">
    Copyright 2017 COD3R (<a href="http://www.cod3r.com.br"
      >http://www.cod3r.com.br</a
    >)
  </p>
  <p class="lead">
    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to
    deal in the Software without restriction, including without limitation the
    rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
    sell copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:
  </p>
  <p class="lead">
    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.
  </p>
  <p class="lead">
    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
    FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
    IN THE SOFTWARE.
  </p>
  <p class="lead">
    Imagens usadas na aplicação por
    <a href="http://www.freepik.com" target="_blank">freepik.com</a>
  </p>
</section>
<!-- FIM DO CONTEÚDO -->
```

app/about/about.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "mt-about",
  templateUrl: "./about.component.html",
})
export class AboutComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

///////////////////////////////////////////////////////////////////////

app/header/header.component.html

```js
<!-- Início do header -->
<header class="main-header">
  <nav class="navbar navbar-static-top">
    <div class="container">
      <div class="navbar-header">
        <a [routerLink]="['/']" class="navbar-brand"><b>Meat</b></a>
        <button
          type="button"
          class="navbar-toggle collapsed"
          data-toggle="collapse"
          data-target="#navbar-collapse"
        >
          <i class="fa fa-bars"></i>
        </button>
      </div>

      <!-- Collect the nav links, forms, and other content for toggling -->
      <div class="collapse navbar-collapse pull-left" id="navbar-collapse">
        <ul class="nav navbar-nav">
          <li routerLinkActive="active">
            <a [routerLink]="['/restaurants']">Restaurantes</a>
          </li>
          <li routerLinkActive="active">
            <a [routerLink]="['/about']">Sobre</a>
          </li>
        </ul>
      </div>
      <!-- /.navbar-collapse -->
    </div>
  </nav>
</header>
<!-- Fim do header -->
```

app/header/header.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "mt-header",
  templateUrl: "./header.component.html",
})
export class HeaderComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```
///////////////////////////////////////////////////////////////////////
app/home/home.component.html

```js
<!-- INÍCIO DO CONTEÚDO -->
<section class="content-header"></section>

<section class="content">
  <div class="jumbotron welcome-jumbotron">
    <h1>Bem vindo ao Meat!</h1>
    <p>Está com fome? Peça e receba em casa.</p>
    <a class="btn btn-primary btn-lg" [routerLink]="['/restaurants']"
      >Ver Restaurantes</a
    >
  </div>
</section>
<!-- FIM DO CONTEÚDO -->

```

app/home/home.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "mt-home",
  templateUrl: "./home.component.html",
})
export class HomeComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

///////////////////////////////////////////////////////////////////////
app/retaurant/retaurant.component.html

```js
<!-- INíCIO do CONTEÚDO -->
<section class="content-header">
  <h1>Todos os Restaurantes</h1>
</section>

<section class="content">
  <div class="row">
    <div class="col-sm-6 col-xs-12">
      <a href="detail-restaurant.html">
        <div class="place-info-box">
          <span class="place-info-box-icon"
            ><img src="assets/img/restaurants/tasty.png"
          /></span>

          <div class="place-info-box-content">
            <span class="place-info-box-text">Tasty Treats</span>
            <span class="place-info-box-star"
              ><i class="fa fa-star"></i> 4.5</span
            >
            <span class="place-info-box-detail">Bakery</span>
            <span class="place-info-box-detail">40-65m</span>
          </div>
          <!-- /.info-box-content -->
        </div>
      </a>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->

    <div class="col-sm-6 col-xs-12">
      <div class="place-info-box">
        <span class="place-info-box-icon"
          ><img src="assets/img/restaurants/icy.png"
        /></span>

        <div class="place-info-box-content">
          <span class="place-info-box-text">Ice Cream</span>
          <span class="place-info-box-star"
            ><i class="fa fa-star"></i> 4.5</span
          >
          <div class="place-info-box-detail">Ice Creams</div>
          <span class="place-info-box-detail">40-65m</span>
        </div>
        <!-- /.info-box-content -->
      </div>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->

    <div class="col-sm-6 col-xs-12">
      <div class="place-info-box">
        <span class="place-info-box-icon"
          ><img src="assets/img/restaurants/burgerhouse.png"
        /></span>

        <div class="place-info-box-content">
          <span class="place-info-box-text">Burger House</span>
          <span class="place-info-box-star"
            ><i class="fa fa-star"></i> 4.5</span
          >
          <div class="place-info-box-detail">Hamburgers</div>
          <span class="place-info-box-detail">40-65m</span>
        </div>
        <!-- /.info-box-content -->
      </div>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->

    <div class="col-sm-6 col-xs-12">
      <div class="place-info-box">
        <span class="place-info-box-icon"
          ><img src="assets/img/restaurants/coffeecorner.png"
        /></span>

        <div class="place-info-box-content">
          <span class="place-info-box-text">Coffee Corner</span>
          <span class="place-info-box-star"
            ><i class="fa fa-star"></i> 4.5</span
          >
          <div class="place-info-box-detail">Coffee Shop</div>
          <span class="place-info-box-detail">40-65m</span>
        </div>
        <!-- /.info-box-content -->
      </div>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->
    <div class="col-sm-6 col-xs-12">
      <div class="place-info-box">
        <span class="place-info-box-icon"
          ><img src="assets/img/restaurants/greenfood.png"
        /></span>

        <div class="place-info-box-content">
          <span class="place-info-box-text">Green Food</span>
          <span class="place-info-box-star"
            ><i class="fa fa-star"></i> 4.5</span
          >
          <div class="place-info-box-detail">Traditional</div>
          <span class="place-info-box-detail">40-65m</span>
        </div>
        <!-- /.info-box-content -->
      </div>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->

    <div class="col-sm-6 col-xs-12">
      <div class="place-info-box">
        <span class="place-info-box-icon"
          ><img src="assets/img/restaurants/breadbakery.png"
        /></span>

        <div class="place-info-box-content">
          <span class="place-info-box-text">Bread &amp; Bakery</span>
          <span class="place-info-box-star"
            ><i class="fa fa-star"></i> 4.5</span
          >
          <span class="place-info-box-detail">Bakery</span>
          <span class="place-info-box-detail">40-65m</span>
        </div>
        <!-- /.info-box-content -->
      </div>
      <!-- /.info-box -->
    </div>
    <!-- /.col -->
  </div>
</section>

<!-- FIM  do CONTEÚDO -->
```

app/retaurant/retaurant.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "mt-retaurants",
  templateUrl: "./retaurants.component.html",
})
export class RetaurantsComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```
Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando um componente dentro de uma pasta especifica

```js
$ ng g c --module pages pages/details
```

## Como criar um componente


Aqui iremos criar um componente

```js
ng generate component primeiro-componente
```

ou

```js
ng g c primeiro-componente
```

Agora se quiser criar um componente sem o teste unitário

```js
ng g c primeiro-componente --spec=false
```

Para criar um componente dentro de uma pasta especifica

```js
ng g c /nomedapasta/nomedoquivo
```

Depois de criado o componente.repare que ele irá aparecer na pasta
src/app/primeiro-componente

Depois de criado seu componente você irá se deparar com quatro arquivos

primeiro-componente.component.css

<!-- Estilização do componente em css -->

```js
.bg { background-color: #cccccc; }
```

app/primeiro-componente/primeiro-componente.component.html

<!-- Aqui irá conter o Html -->

```js
//Aqui estou chamando o css, com o metodo class
<div class="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
```

app/primeiro-componente/primeiro-componente.component.spec.ts

<!-- Aqui contém os testes unitários do componente,
que também foi criado automático -->

```js
import { ComponentFixture, TestBed } from "@angular/core/testing";

import { PrimeiroComponenteComponent } from "./primeiro-componente.component";

describe("PrimeiroComponenteComponent", () => {
  let component: PrimeiroComponenteComponent;
  let fixture: ComponentFixture<PrimeiroComponenteComponent>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [PrimeiroComponenteComponent],
    }).compileComponents();
  });

  beforeEach(() => {
    fixture = TestBed.createComponent(PrimeiroComponenteComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it("should create", () => {
    expect(component).toBeTruthy();
  });
});
```

app/primeiro-componente/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente", // Aqui o selector, este nome é qual irei importar depois o componente
  templateUrl: "./primeiro-componente.component.html", // Aqui está conectando o arquivo html
  styleUrls: ["./primeiro-componente.component.css"], // Aqui está conectando o arquivo css
})
export class PrimeiroComponenteComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

**\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***\*\*\*\***\*\***

app/app.modules.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";

/*Importando app.component, automático que será executado em primeiro lugar*/
import { AppComponent } from "./app.component";

/*Importando componente, criado, automaticamente*/
import { PrimeiroComponenteComponent } from "./primeiro-componente/primeiro-componente.component";

@NgModule({
  declarations: [AppComponent, PrimeiroComponenteComponent], // Aqui dentro está os componentes criados e importados automáticos dentro de []
  imports: [BrowserModule, AppRoutingModule],
  providers: [],
  bootstrap: [AppComponent], // Aqui ele está referenciando que o AppComponent será o primeiro arquivo a ser executado
})
export class AppModule {}
```

app/app.component.ts

```js
import { Component } from "@angular/core"; // Importando componente

@Component({
  selector: "app-root", // Este app-root está salvando toda nossa aplicação, no arquivo inde.html, que foi criado automático também
  templateUrl: "./app.component.html", // Aqui ele está conectando o arquivo html, este arquivo que será renderizado em primeiro lugar e dentro dele que vamos importar os componetes que criamos
  styleUrls: ["./app.component.css"], // aqui estamos conectando o arquivo css, a estilização do nosso html, deste proprio componente que está sendo renderizado em primeiro lugar
})
export class AppComponent {
  // Exportando o componente
  title = "angularaulas";
}
```

Desta forma, se quiser expluir o arquivo app/app.component.html e o css Repare
que a rota adicionei direto aqui dentro, no template

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: "<router-outlet></router-outlet>",
})
export class AppComponent {}
```

app/app.component.html

```js
<h1>Página teste</h1>
<app-primeiro-componente></app-primeiro-componente> //Aqui estou importando o componente app/primeiro-componente/primeiro-componente.component.ts, selector: "app-primeiro-componente", o nome do selector, é este nome que estamos importando
// Aqui podemos importar quantos componentes quisermos, agora fica melhor a visualização dos componentes criados e assim melhor a manutenção e também podemos reutilizar os componentes assim deixando nosso código menor.
```

app/index.html

```js
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Angularaulas</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <app-root></app-root>
  /*Este app-root é aonde está salvando toda a nossa aplicação,
  ele está sendo referenciado no nosso arquivo app/app.components*/
</body>
</html>
```

## Desta forma, é mais facil de importar e exportar

Criar um componente, chamado calculadora

ng g c calculadora/caculadora

src/app/calculadora/componentes/calculadora.component.html

```js
<p>calculadora works!</p>
```

src/app/calculadora/componentes/calculadora.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-calculadora",
  templateUrl: "./calculadora.component.html",
  styleUrls: ["./calculadora.component.scss"],
})
export class CalculadoraComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/calculadora/componentes/index.ts

```js
export * from "./calculadora.component";
```

Dentro da calculadora foi criado um modulo

```js
ng g m calculadora
```

src/app/calculadora/calculadora.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { CalculadoraComponent } from "./components";

@NgModule({
  imports: [CommonModule],
  declarations: [CalculadoraComponent],
  exports: [CalculadoraComponent],
})
export class CalculadoraModule {}
```

src/app/app.module.ts

```js
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

import { AppRoutingModule } from "./app-routing.module";
import { AppComponent } from "./app.component";

import { CalculadoraModule } from "./calculadora";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule, CalculadoraModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
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

src/app/app.component.html

```js
<app-calculadora></app-calculadora>
<router-outlet></router-outlet>
```

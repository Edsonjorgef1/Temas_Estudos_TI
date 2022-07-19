Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Uma aplicação Angular é baseada em componentes. Com eles, nós podemos encapsular
comportamentos e regras da interface, torando a criação de aplicações algo mais
simples. Inclusive, um componente pode encapsular outros componentes.

## Componentes

Atualmente, o Angular é um dos mais conhecidos frameworks para desenvolvimento web. Criado e mantido pela Google, ele já tem uma longa estrada no mercado. Uma das partes mais importantes de um projeto Angular é o que chamamos de componentes, pois eles são a parte lógica da aplicação.

## Estrutura de um componente

Os componentes são classes escritas em TypeScript que recebem o decorator @Component, assim como mostra o Código 1. Vamos analisar esse código juntos ao longo dessa seção, portanto não se preocupe em entendê-lo completamente agora. Atente-se apenas para o fato dele ser uma classe com um decorator, por enquanto.

```js
@Component({  selector: 'cadastro',
   templateUrl: 'cadastro.component.html',
    styleUrls: ['cadastro.component.css']
})
export class CadastroComponent {

}
```
Quando analisamos a estrutura de um componente, podemos dividi-lo nas seguintes partes:

Metadata: são definições que iremos informar ao Angular que a nossa classe é um Component, por meio de decorators, nesse caso @Component
Classe: assim como em qualquer linguagem de programação que utiliza o paradigma da orientação a objeto, possui suas propriedades e métodos
Um Component é um tipo de classe existente em uma aplicação Angular, eles são identificados com o decorator @Component. Neste decorator existem algumas propriedades mais utilizadas como: selector, templateUrl e style. Vamos especificá-las:

selector é como identificamos o nosso componente. Para todo o componente existe um elemento único associado que permite que ele seja adicionado em um documento HTML. Nesse caso, o nome do elemento desse componente é cadastro e deve ser escrito como <cadastro></cadastro>
TemplateUrl é o nome do documento HTML que será a parte visual do componente. Nele podemos ter código em HTML juntamente com todos os bindings e diretivas necessários para a exibição do componente no navegador
Template também usado para descrever a parte visual do componente, porém nesse caso podemos fornecer código HTML "hard coded", como texto
styleUrl é onde informamos quais folhas de estilo contêm o código CSS que será aplicado ao template do componente.
Com isso podemos concluir que a estrutura de um componente Angular deve ser formada por esses três elementos, template (HTML), estilo (CSS) e classe (TypeScript). Essas partes são organizadas em arquivos separados e unidas nos metadados do componente através do decorator @Component

No Código 2 vemos uma outra forma de descrever o template do componente usando a propriedade template, sem a necessidade de criar um arquivo HTML no projeto.

```js
@Component({  selector: 'cadastro',
    template:'<input type="text"[(ngModel)]="nome" name="nome" id="nome"/>',
    styleUrls: ['cadastro.component.css']
})
export class CadastroComponent {

}
```

Como boa prática, o código HTML implementado na propriedade template deve conter poucas linhas. Caso este seja um código mais elaborado é recomendável colocá-lo em um documento HTML, utilizando a propriedade templateUrl para indicar a localização deste arquivo.

Podemos fazer referência ao Component CadastroComponent em outros componentes do projeto usando o seletor cadastro. Nesse caso basta colocarmos a tag <cadastro></cadastro> dentro do HTML do template.


## Para emular o projeto

```js
ng serve -o
```

ou

```js
ng serve --open
```

ou

```js
ng s
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

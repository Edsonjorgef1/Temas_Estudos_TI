Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Exibindo dados, atraves de uma variavel

app/primeiro-component/primeiro-componente.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>{{title}}<p/>
  <p>Que legal</p>
</div>
<br />
<div>
    <h4>{{ meutitulo + meutitulo2 }}</h4>
    <p>Olá {{meutitulo}} <p/>

</div>
```

app/primeiro-component/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente",
  templateUrl: "./primeiro-componente.component.html",
  styleUrls: ["./primeiro-componente.component.css"],
})
export class PrimeiroComponenteComponent implements OnInit {
  meutitulo = "Exibindo dados, atraves de uma variavel";
  meutitulo2 = "Exibindo dados, 2 ";
  //Quando colocamos puclic, quer dizer que podemos utilizar em outros lugares da nossa aplicação
  public title = 'Bem Vindo';
  //public title: string = 'Bem vindo';
  //Private, não pode ser usado em outros lugares
  //private title = 'Bem Vindo';
  constructor() {}

  ngOnInit(): void {}
}
```

## Outro exemplo

pagina.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-pagina',
  templateUrl: './pagina.component.html',
  styleUrls: ['./pagina.component.scss'],
})
export class PaginaComponent implements OnInit {
  public titulo: any;
  public texto: any;

  constructor() {}

  ngOnInit(): void {
    this.titulo = 'O que são Components no Angular';
    this.texto = `Olá template string`;
  }
}
```
pagina.component.html

```js
<div id="header">
  <h1><p class="textoTitulo">Artigo</p></h1>
</div>
<div id="titulo">
  <h2>{{ titulo }}</h2>
</div>
<div id="texto">
  {{ texto }}
</div>
```
app.component.html

```js
<app-pagina></app-pagina>
<router-outlet></router-outlet>
```
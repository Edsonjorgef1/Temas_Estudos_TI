Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## public

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
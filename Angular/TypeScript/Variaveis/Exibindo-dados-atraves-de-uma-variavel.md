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

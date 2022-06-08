### Interpolation

A interpolação de texto permite que você incorpore valores dinâmicos em seus
modelos HTML

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

<h2>Interpolation</h2>
<p>{{ nome }} tem {{ idade }} anos</p>
<p>{{ nome }} tem mais de 28 anos?</p>
<p>{{ idade > 28 }}</p>

<p>Quanto é {{ idade }} + {{ maisUm }}?</p>
<p>{{ idade + maisUm }}</p>

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
  public meutitulo: string = "Exibindo dados, atraves de uma variavel";
  public meutitulo2: string = "Exibindo dados, 2 ";
  //Quando colocamos puclic, quer dizer que podemos utilizar em outros lugares da nossa aplicação
  public title: string = "Bem vindo!";
  //public title: string = 'Bem vindo';
  //Private, não pode ser usado em outros lugares
  //private title = 'Bem Vindo';

  public nome: string = 'Dener';
  public idade: number = 29;
  public maisUm: number = 1;

  constructor() {}

  ngOnInit(): void {}
}
```

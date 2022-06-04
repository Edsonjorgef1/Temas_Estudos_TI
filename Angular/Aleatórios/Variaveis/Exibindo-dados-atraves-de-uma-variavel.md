Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Exibindo dados, atraves de uma variavel

app/primeiro-component/primeiro-componente.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
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
  constructor() {}

  ngOnInit(): void {}
}
```

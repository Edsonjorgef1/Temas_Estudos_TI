## Retornando objeto de uma funcao criada id e nome

Propriedade id e propriedade nome Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

app/primeiro-component/primeiro-componente.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
<br />
<div>
  <p>{{ cliente.id }}</p>
  <p>{{ cliente.nome }}</p>
    <p>{{ cliente.id }} - {{ cliente.nome }}</p>

</div>
<div>
  <p></p>
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
  cliente = {
    id: 1,
    nome: "Fulano",
  };

  constructor() {}

  ngOnInit() {}
}
```

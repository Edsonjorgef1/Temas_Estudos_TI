Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Retornando objeto

app/primeiro-componente/primeiro-componente.component.html

```js
<div>
  <p>{{ cliente.nome }}</p>
  <p>{{ cliente.id }}</p>
  <p>{{ cliente.nome }} - {{ cliente.id }}</p>
</div>
```

app/primeiro-componente/primeiro-componente.component.ts

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

  ngOnInit(): void {}
}
```

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Aviso

app.component.html

```js
<!--ngIf = Permiti que elementos apareçam ou sumam conforme o estado da condição é alterada-->
<div *ngIf="showAviso">{{ avisoMsg }}</div>
```

app.component.ts

```js
import { Component } from "@angular/core";
import { Pessoa } from "./pessoa";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  //Aviso
  showAviso = true;
  avisoMsg = "Estem é um aviso";
}
```

## Exemplo, aparecendo ou não um cliente

app/primeiro-componente/primeiro-componente.component.html

```js
<div *ngFor="let umCliente of clientes">
  <p *ngIf="umCliente.ativo">{{ umCliente.id }} - {{ umCliente.nome }}</p>
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
  clientes = [
    {
      id: 1,
      nome: "Fulano",
      ativo: true,
    },
    {
      id: 2,
      nome: "Beltrano",
      ativo: false,
    },
    {
      id: 3,
      nome: "Ciclano",
      ativo: true,
    },
  ];

  constructor() {}

  ngOnInit(): void {}
}
```

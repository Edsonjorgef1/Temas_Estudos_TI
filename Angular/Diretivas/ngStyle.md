## ngStyle

Adicona ou remove estilos no html

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

app/primeiro-componente/primeiro-componente.component.html

```js
<div [ngStyle]="{ 'background-color': isRed ? 'red' : 'blue' }">
  Texto
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
  constructor() {}

  ngOnInit() {}

  isRed = true;
}
```

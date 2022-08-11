Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Increment e Decrement

app/primeiro-componente/primeiro-componente.component.html

```js
<div class="div">
  <h1>{{ count }}</h1>
  <button (click)="increment()">+1</button>
  <button (click)="decrement()">-1</button>
</div>
```

app/primeiro-componente/primeiro-componente.component.css

```js
.div {
  background-color: #d43d3d;
}
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
  // Inicializando o contador em zero
  count: number = 0;

  constructor() {}

  ngOnInit() {}
  //Criando Increment do contador
  increment(): void {
    this.count += this.count < 10 ? 1 : 0;
  }
  //Criando Decrement do contador
  decrement(): void {
    this.count -= this.count ? 1 : 0;
  }
}
```

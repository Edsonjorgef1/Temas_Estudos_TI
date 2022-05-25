Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Retornando string de uma funcao criada

app/primeiro-component/primeiro-componente.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>{{ geralTexto() }}</p>
</div>
<br />
<div>

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
  constructor() {}

  ngOnInit() {}

  //Criando uma função
  geralTexto() {
    return "Texto sendo retornado pela função";
  }
}
```

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Buscando um nome especifico array

app.component.html

```js
<h1 class="h1">Buscando um nome específico no array</h1>
<p>Nome Principal: {{ nomePrincipal }}</p>
```

app.component.css

```js
.h1 {
  color: blue;
}
```

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  nomes = ["beto", "Valdir", "Elio"];
  /*nomes = [  "0" ,   "1"   ,  "2"  ]*/

  nomePrincipal = this.nomes[0];
}
```

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngOnInit()

Este evento é inicializado após o Angular exibir pela primeira vez as
propriedades vinculadas aos dados ou quando o componente foi inicializado. Este
evento é usado principalmente em um componente para inicializar dados em
componente.

app.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: "<router-outlet></router-outlet>",
})
export class AppComponent implements OnInit {
  constructor() {}
  ngOnInit(): void {
    setTimeout(() => {
      console.log(1);
    }, 5000);
  }
}
```

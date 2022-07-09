Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Aviso

app.component.html

```js
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

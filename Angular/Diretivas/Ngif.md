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

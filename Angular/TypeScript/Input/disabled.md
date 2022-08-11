## Disabled

app/app.component.html

```js
<input type="text" [disabled]="hideInput" />
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
  hideInput = true;
}
```

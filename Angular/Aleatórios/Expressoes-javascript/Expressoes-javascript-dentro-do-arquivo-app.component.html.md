Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Javascript, posso programar aqui

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<!-- Aqui eu posso colocar qualquer expressão em javascript que eu quiser -->
<!-- {{Tudo o que tiver aqui dentro ira ser interpretado como javascript}} -->
{{ 2 + 3 }}
```

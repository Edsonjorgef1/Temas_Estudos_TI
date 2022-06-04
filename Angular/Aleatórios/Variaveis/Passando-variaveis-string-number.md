Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Passando variaveis, nome (string) e idade (Number)

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
  nome = "Beto";
  idade = 90;
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

Meu nome é {{ nome }} e eu tenho {{ idade }} anos
```

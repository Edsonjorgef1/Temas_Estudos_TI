Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Passando a variavel title

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
<h1 class="h1">{{ title }}</h1>
```

app.component.css

```js
.h1 {
  color: blue;
}
```

## Passando a variavel title, nome e idade

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas"; /*Variavel title*/
  nome = "Beto"; /*Variavel nome*/
  idade = 30; /*Variavel idade*/
}
```

app.component.html

```js
Meu nome é {{ nome }} e eu tenho {{ idade }} anos
```

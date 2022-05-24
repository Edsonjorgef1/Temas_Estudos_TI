Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## 1 Exemplo

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `<h1>Meu próprio HTML</h1>`,
})
export class AppComponent {
  title = "angularaulas";
}
```

## 2 Exemplo

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
<h1>Meu próprio Html</h1>
<h4>Sub-legenda legal</h4>
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
<h1>{{title}}</h1> // Aqui eu passei o nome title,do aquivo, app.component.ts
<h4>Sub-legenda legal</h4>
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

## Agora vamos colocar uma variavel dentro de um input, eu consigo colocar está variavel aonde eu quiser

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
<input type="text" value="{{ nome }}" />
```

## Total de itens que eu tenho em uma array e nome

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
  nomes = ["Beto", "Paulo", "Amigo", "Pai"];
  nomePrincipal = this.nomes[0];
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal }}</p>
```

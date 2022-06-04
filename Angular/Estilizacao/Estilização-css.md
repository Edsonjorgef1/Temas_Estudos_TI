## Styles e Class

## Estilos inline

app/app.component.html

```js
<!-- 1 Forma de estilização -->
<div style="color: #00ff00">Texto 1</div>

<!-- 2 Forma de estilização -->
<div
  [style]="{
    width: '100px',
    heigth: '100px',
    fontSize: tamanhoFonte,
    backgroundColor: 'blue'
  }"
>
  Texto class 1
</div>

<!-- 3 Forma de estilização -->
<div [style.width.px]="100">Texto 3</div>
```

app/app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  tamanhoFonte: 20;
}
```

## Estilos Class

```js
<!-- 4 Forma de estilização (Vericar como adicionar class nas divs) -->
<div [class]="{ class1: false, class2: false }">Texto Class</div>

<!-- 5 Forma de estilização -->
<div [class]="{ menu: true, ativo: false }">Texto menu 1</div>
<div [class]="{ menu: true, ativo: true }">Texto menu 2</div>

<!-- 6 Forma de estilização  -->
<div [class.teste]="true">Texto</div>

<!-- 7 Forma de estilização  -->
<div [class]="{ menu: false }">Texto</div>
```

## Estilos Class 2 Opção

app.component.html

```js
<div class="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
```

app.component.css

```js
.bg {
  background-color: #cccccc;
}
```

## Estilos ID

app.component.html

```js
<div id="bg">
  <h3>Esse é meu primeiro componente</h3>
  <p>Que legal</p>
</div>
```

app.component.css

```js
#bg {
  background-color: #cccccc;
}
```

# Html dentro do arquivo

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  template: ` <h1 class="h1">Olá Mundo</h1> `,
})
export class AppComponent {
  title = "angularaulas";
}
```

app.component.css

```js
.h1 {
  color: blue;
}
```

## html em outro aquivo, mais organizado

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
}
```

app.component.html

```js
<h1 class="h1">Meu proprio Html</h1>
```

app.component.css

```js
.h1 {
  color: blue;
}
```

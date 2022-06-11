Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando Sub Modules

```js
ng g m shared
```

Criar um componete agora a minha pasta shared

```js
ng g c shared/newComponent
```

src/app/shared/new-component/new-component.component.html

```js
<header>
  <h1>Header do App</h1>
</header>
```

src/app/shared/new-component/new-component.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-new-component",
  templateUrl: "./new-component.component.html",
  styleUrls: ["./new-component.component.scss"],
})
export class NewComponentComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";

@NgModule({
  declarations: [NewComponentComponent],
  //Exportando o componente
  exports: [NewComponentComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

## Agora vamos criar um arquivo, na pasta shared

Repare que depois que criar o arquivo ja irá importar o componente criado dentro
do src/app/shared/shared.module.ts src/app/shared/shared.module.ts

Criar um componete agora a minha pasta shared

```js
ng g c shared/input
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [NewComponentComponent, InputComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz
  exports: [NewComponentComponent, InputComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

src/app/shared/input/input.component.html

```js
<p>inputCriado Parabéns</p>
```

src/app/shared/input/input.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-input",
  templateUrl: "./input.component.html",
  styleUrls: ["./input.component.scss"],
})
export class InputComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

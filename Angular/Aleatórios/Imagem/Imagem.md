Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Topicos

.Imagem, abrindo uma imgem, com uma url

app.component.html

```js
<!-- Aparecendo imagem, outro jeito, atual hoje -->
<img [src]="imagem" />

<!-- Aparecendo imagem, atual hoje -->
<img src="{{ imagem }}" />

<!-- Aparecendo imagem, outro jeito, bind é antigo -->
<img bind-src="imagem" />

<img [src]="imagem" [title]="imgTitle" [alt]="imgTitle" />
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
  //Imagem
 public imagem: string = "https://www.google.com.br/google.jpg";
 public imgTitle: string = 'Property Binding';

}
```

## Aparecendo ou sumindo uma imagem

app/title/title.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-title",
  templateUrl: "./title.component.html",
  styleUrls: ["./title.component.scss"],
})
export class TitleComponent implements OnInit {
  condicional = true;
  constructor() {}

  ngOnInit(): void {}
}
```

app/title/title.component.html

```js
<div *ngIf="condicional">
  <img src="{{ itemImageUrl }}" />
</div>
```

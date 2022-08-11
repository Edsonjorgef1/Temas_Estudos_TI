Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Property Binding

Ajuda a definir valores para propriedades de elementos ou diretivas HTML

## Aparecendo e sumindo um botão [disable]

app/title/title.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-title",
  templateUrl: "./title.component.html",
  styleUrls: ["./title.component.scss"],
})
export class TitleComponent implements OnInit {
  disabledButton = false;

  constructor() {}

  ngOnInit(): void {}
}
```

app/title/title.component.html

```js

<button [disabled]="disabledButton">Button</button>
```

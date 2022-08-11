Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Two-way binding

É A União do property-binding com event-binding. Use para ouvir eventos e
atualizar valores simultaneamente entre os componentes pai e filho.

## ngModule

app/title/title.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.scss'],
})
export class TitleComponent implements OnInit {
  public nome = 'Dener';

  constructor() {}

  ngOnInit(): void {}
}
```

app/title/title.component.html

```js

<input [(ngModel)]="nome" />
<span>{{ nome }}</span>

```

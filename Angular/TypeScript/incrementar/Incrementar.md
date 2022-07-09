## Incrementar

contador.component.html

```js
<h1>{{ numero }}</h1>
<button (click)="incrementar()">Incrementar</button>
```

contador.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public numero = 1;

  constructor() {}

  ngOnInit(): void {}
  incrementar() {
    //this.numero = this.numero + 1;
    this.numero++;
  }
}
```



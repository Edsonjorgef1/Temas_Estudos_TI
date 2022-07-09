## property-binding

property-binding.component.html

```js
<img [src]="imgURL"/>

<a [href]= "url">Acessar</a>
```

property-binding.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public imgURL = 'https://devmedia.com.br/logo.png';
  public url = 'https://engenheiroyoutuber.com.br';

  constructor() {}

  ngOnInit(): void {}
}
```
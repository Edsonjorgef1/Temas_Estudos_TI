## Exemplo com string interpolation

interpolation.component.html

```js
<a href="{{ url }}" title="Acessar">Acessar</a>
```

interpolation.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-contador',
  templateUrl: './contador.component.html',
  styleUrls: ['./contador.component.scss'],
})
export class ContadorComponent implements OnInit {
  public url = 'https://engenheiroyoutuber.com.br';

  constructor() {}

  ngOnInit(): void {}
}
```

## property-binding

property-binding.component.html

```js
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
  public url = 'https://engenheiroyoutuber.com.br';

  constructor() {}

  ngOnInit(): void {}
}
```

## Outro exemplo

```js
<a routerLink="/restaurants">Restaurantes</a>
//ou
<a [routerLink]="['/restaurants']">Restaurantes</a>
```
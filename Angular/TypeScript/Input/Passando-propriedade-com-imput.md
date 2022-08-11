Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Passando uma propriedade com imput

```js
header.component.ts

import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-header',
  templateUrl: './header.component.html',
  styleUrls: ['./header.component.scss'],
})
export class HeaderComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
  user = { name: 'Beto' };
}
```

header.component.html

<input type="text" [value]="user.name" />
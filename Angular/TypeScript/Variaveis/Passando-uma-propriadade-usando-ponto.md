Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Passando uma propriedade usando o ponto

teste.component.html

```js
<h1>{{ title }}</h1>
<p>Teste, {{ user.name }}</p>
```

teste.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-teste',
  templateUrl: './teste.component.html',
  styleUrls: ['./teste.component.scss'],
})
export class TesteComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
  title: string = 'Meu componente';
  user = { name: 'Beto' };
}
```

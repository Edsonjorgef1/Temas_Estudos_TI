Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Keypress

O método onKeyPress possui um parâmetro, que chamamos de event, mas que poderia ter qualquer outro nome. É partir desse parâmetro que conseguiremos acesso as informações do evento emitido.

```js
console.log(event.target.value.length);
```

Ao pressionar uma tecla, diferentes eventos podem ser emitidos. KeyPress, fica sendo emitido enquanto a tecla continuar sendo pressionada. KeyUp e KeyDown ocorrem uma única vez. KeyUp quando a tecla é solta e KeyDown quando ela é pressionada.


Não se esqueça de informar ao Angular que $event deve ser passado como parâmetro para o método onKeyPress($event).


caixa-de-texto.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-caixa-de-texto',
  templateUrl: './caixa-de-texto.component.html',
  styleUrls: ['./caixa-de-texto.component.scss'],
})
export class CaixaDeTextoComponent implements OnInit {
  onKeyPress(event: any) {
    console.log(event.target.value.length);
  }

  constructor() {}

  ngOnInit(): void {}
}
```

caixa-de-texto.component.html

```js
<textarea (keypress)="onKeyPress($event)"></textarea>
```

app.component.html

Conponente principal

```js
<app-caixa-de-texto></app-caixa-de-texto>
<router-outlet></router-outlet>
```

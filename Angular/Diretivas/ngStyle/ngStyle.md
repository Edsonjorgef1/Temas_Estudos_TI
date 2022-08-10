Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngStyle

NgStyle - Adiciona e remove um conjunto de estilos HTML /_Aqui mechamos direto
no style do html_/

Adicona ou remove estilos no html

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

app/primeiro-componente/primeiro-componente.component.html

```js
<div [ngStyle]="{ 'background-color': isRed ? 'red' : 'blue' }">
  Texto
</div>
```

app/primeiro-componente/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente",
  templateUrl: "./primeiro-componente.component.html",
  styleUrls: ["./primeiro-componente.component.css"],
})
export class PrimeiroComponenteComponent implements OnInit {
  constructor() {}

  ngOnInit() {}

  isRed = true;
}
```

## Aumentando e diminuindo a altura

src/app/diretivas-atributos/diretivas-atributos.component.html

```js
<p [ngStyle]="{ height: heightPx, background: backgroundColor }">NgStyle</p>
```

src/app/diretivas-atributos/diretivas-atributos.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-atributos',
  templateUrl: './diretivas-atributos.component.html',
  styleUrls: ['./diretivas-atributos.component.scss'],
})
export class DiretivasAtributosComponent implements OnInit {
  public valor: boolean = true;
  public heightPx: string = '20px';
  public backgroundColor: string = 'red';

  constructor() {}

  ngOnInit(): void {
    setInterval(() => {
      if (this.valor) {
        this.valor = false;
      } else {
        this.valor = true;
      }
      if (this.heightPx == '20px') {
        this.heightPx = '50px';
        this.backgroundColor = 'blue';
      } else {
        this.heightPx = '20px';
        this.backgroundColor = 'red';
      }
    }, 2000);
  }
}
```



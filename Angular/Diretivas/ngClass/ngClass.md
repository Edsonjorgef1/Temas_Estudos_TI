## ngClass

NgClass - Adiciona e remove um conjunto de class CSS /_Exemplo: Fex uma
validação se não tiver correto ele muda a class para vermelho ou fundo azul,
mostrar a class para a pessoa_/ Com ngClass você pode fazer validações

app/diretivas-estruturais/diretivas-estruturais.component.html

```js
<p [ngClass]="{ active: valor, disabled: !valor }">NgClass</p>
```

app/diretivas-estruturais/diretivas-estruturais.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-atributos',
  templateUrl: './diretivas-atributos.component.html',
  styleUrls: ['./diretivas-atributos.component.scss'],
})
export class DiretivasAtributosComponent implements OnInit {
  public valor: boolean = true;

  constructor() {}

  ngOnInit(): void {
    setInterval(() => {
      if (this.valor) {
        this.valor = false;
      } else {
        this.valor = true;
      }
    }, 2000);
  }
}

```

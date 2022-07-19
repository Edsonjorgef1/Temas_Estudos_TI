Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## ngOnDestroy

É executado antes do Angular destruir o componente. O ideal é que esse método seja utilizado para promover uma 'limpeza' no componente, tal como remover events handler por exemplo, antes da sua destruição para evitar memory leaks.

Ele vai ser ativado quando destruirmos alguma coisa, quando destruirmos um
componente, ai la no componente irá falar fui destruido, então envoque uma ação
Opção de uso: 1 - Quando fazermos as requisições ele é utilizado para não gerar
memoria liq no nossa angular. 2 - Fazer aparecer alguma coisa depois do
componente ser destruído e aparecer uma mensagem depois de destruído.

src/app/title/title.component.ts

```js
import { Component, Input, OnChanges, OnDestroy, OnInit } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.scss'],
})
export class TitleComponent implements OnInit, OnChanges, OnDestroy {
  @Input() public title: string = 'Bem Vindo';
  constructor() {}

  ngOnInit(): void {}
  ngOnChanges(): void {}
  ngOnDestroy(): void {
    //Quando for destruido importei o onDestroy, ai faço alguma coisa
    //Lá no app.component.ts, quando clicar no botão ela vai destruir o componente ai, aqui depois de importado você diz o que deve fazer
    console.log('Deu bom ele foi destruido');
  }
}
```

src/app.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-root',
  template: ` <app-title *ngIf="destruir"></app-title>
    <br />
    <button (click)="destruirComponent()">Destruir componente</button>
    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  public destruir: boolean = true;

  constructor() {}

  ngOnInit(): void {}

  public destruirComponent() {
    this.destruir = false;
  }
}
```

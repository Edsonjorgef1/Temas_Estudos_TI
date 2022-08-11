Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## mouseEvent

Quando passar o mouse em cima, irá te mostrar o eixo x e y

app/data-biding/data-biding.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-data-biding',
  templateUrl: './data-biding.component.html',
  styleUrls: ['./data-biding.component.scss'],
})
export class DataBidingComponent implements OnInit {
  public nome: string = 'Dener';
  public idade: number = 29;
  public maisUm: number = 1;

  public checkedDisabled: boolean = false;
  public imgSrc: string = 'https://www.google.com.br/google.jpg';
  public imgTitle: string = 'Property Binding';

  public position: { x: number; y: number } = { x: 0, y: 0 };
  // Sem o tipo
  // public position: any

  constructor() {}

  ngOnInit(): void {}
  public alertInfo(valor: MouseEvent) {
    //Sem o tipo,  public alertInfo(valor: any) {
    console.log(valor);
  }
  public mouseMoveTeste(valor: MouseEvent) {
    // Sem o tipo, public mouseMoveTeste(valor: any) {
    // console.log(valor);
    this.position.x = valor.offsetX;
    this.position.y = valor.offsetY;
  }
}
```

app/data-biding/data-biding.component.html

```js
<h2>Interpolation</h2>
<p>{{ nome }} tem {{ idade }} anos</p>
<p>{{ nome }} tem mais de 28 anos?</p>
<p>{{ idade > 28 }}</p>

<p>Quanto é {{ idade }} + {{ maisUm }}?</p>
<p>{{ idade + maisUm }}</p>
<hr />
<h2>Property Binding</h2>
<button [disabled]="checkedDisabled">Button</button>

<img [src]="imgSrc" [title]="imgTitle" [alt]="imgTitle" />

<button (click)="alertInfo($event)">Evento</button>


//Evento, quando passar o mouse
<div
  (mousemove)="mouseMoveTeste($event)"
  style="background: red; width: 300px; height: 300px"
></div>
{{ position.x }} - {{ position.y }}
```

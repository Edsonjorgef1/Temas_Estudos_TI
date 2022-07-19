Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Tooltipe

Quando passar o mouse em cima faça alguma coisa

tooltip-example.component.ts

```js
import { Component, } from '@angular/core';

@Component({
  selector: 'app-tooltip-example',
  templateUrl: './tooltip-example.component.html',
  styleUrls: ['./tooltip-example.component.css']
})
export class TooltipExampleComponent {

  public visible = false;

  exibeTooltip() {
    this.visible = true;
  }

  escondeTooltip() {
    this.visible = false;
  }
}
```

tooltip-example.component.html

```js
<p class="term" (mouseover)="exibeTooltip()" (mouseleave)="escondeTooltip()">DOM</p>

<div class="tooltip" [class.visible]="visible">
    <p>The Document Object Model (DOM) connects web pages to scripts or
        programming languages by representing the structure of a document—such
        as the HTML representing a web page—in memory. Usually that means
        JavaScript, although modelling HTML, SVG, or XML documents as objects
        is not part of the JavaScript language, as such.</p>
</div>
```

tooltip-example.component.scss

```js
.tooltip {
    background-color: #444;
    border: 1px solid #333;
    border-radius: 8px;
    color: #fff;
    display: none;
    max-width: 500px;
    padding: 10px 15px;
    position: absolute;
  }
   
  .tooltip p {
    font: 14px/1.6 "Helvetica Neue", sans-serif;
    margin: 0;
    padding: 0;
  }
   
  .visible {
    display: inline-block;
  }
   
  .term {
    cursor: pointer;
    display: inline-block;
  }
```

app.component.html

```js
<app-tooltip-example></app-tooltip-example>
```
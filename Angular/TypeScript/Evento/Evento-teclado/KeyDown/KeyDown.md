## Assim que a tecla espaço for precionada, o seu evento ocorrera


app.component.ts

```js
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss'],
})
export class AppComponent {
  keyDown(event: any): void {
    console.log(`Key down: ${event}`);
  }
}
```
app.component.html

```js
<input (keydown.space)="keyDown($event)" />

<router-outlet></router-outlet>
```
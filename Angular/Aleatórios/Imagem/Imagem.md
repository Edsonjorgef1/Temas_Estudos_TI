Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Topicos

.Imagem, abrindo uma imgem, com uma url

app.component.html

```js
<!-- Aparecendo imagem, atual hoje -->
<img src="{{ imagem }}" />

<!-- Aparecendo imagem, outro jeito, atual hoje -->
<img [src]="imagem" />

<!-- Aparecendo imagem, outro jeito, bind é antigo -->
<img bind-src="imagem" />
```

app.component.ts

```js
import { Component } from "@angular/core";
import { Pessoa } from "./pessoa";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  //Imagem
  imagem = "https://www.google.com.br/google.jpg";
}
```

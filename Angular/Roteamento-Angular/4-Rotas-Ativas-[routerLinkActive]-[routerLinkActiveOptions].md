Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Rotas ativas

Quando tiver em determinado rota vamos pintar

[routerLinkActive]="['class']" Quando meu link tiver ativo no meu navegador, ele
ira colocar uma class

[routerLinkActiveOptions]="{ exact: true }" Aqui e para ser exato qual o link eu
quero

src/app/shared/menu/menu.component.html

```js
<header>
  <nav>
    <ul>
      <li>
        <a
          routerLink="/"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Home</a
        >
      </li>
      <li>
        <a
          routerLink="/sobre"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Sobre</a
        >
      </li>
      <li>
        <a
          routerLink="['/404']"
          [routerLinkActive]="'active'"
          [routerLinkActiveOptions]="{ exact: true }"
          >Errorsss</a
        >
      </li>
    </ul>
  </nav>
</header>
```

src/app/shared/menu/menu.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-menu",
  templateUrl: "./menu.component.html",
  styleUrls: ["./menu.component.scss"],
})
export class MenuComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

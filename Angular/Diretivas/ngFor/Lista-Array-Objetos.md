## ngFor, Lista 3, Array, com objetos

app.component.html

```js
<h1>Nome Principal: {{ nomePrincipal.nome }}</h1>
<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos
  </li>
</ul>

```

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  /*Array com objetos */
  nomes = [
    { nome: "Beto", idade: 90 },
    { nome: "Paulo", idade: 20 },
    { nome: "Irmao", idade: 40 },
    { nome: "Pai", idade: 60 },
    { nome: "Mae", idade: 80 },
  ];
  nomePrincipal = this.nomes[1];
}
```

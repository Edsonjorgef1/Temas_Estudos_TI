Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Fazendo mostrar um aviso, mostrar um aviso especifico seja qual for

pessoa.ts

```js
export class Pessoa {
  public id: number;
  public nome: string;
  public idade: number;

  constructor(id: number, nome: string, idade: number) {
    this.id = id;
    this.nome = nome;
    this.idade = idade;
  }

  getTipo() {
    if (this.idade <= 15) {
      return 'Criança';
    } else if (this.idade > 15 && this.idade <= 20) {
      return 'Jovem';
    } else if (this.idade > 20 && this.idade <= 50) {
      return 'Adulto';
    } else if (this.idade > 50 && this.idade <= 80) {
      return 'Idoso';
    } else this.idade > 80 && this.idade <= 80;
    {
      return 'Super Sayadin';
    }
  }
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal.nome }}</p>

<div *ngIf="nomes.length <= 4">
  <input type="text" />
  <button>Adicionar</button>
</div>

<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<p *ngIf="nomes.length > 2">Tem muitos nomes cadastrados</p>

<div *ngIf="showAviso">{{ avisoMsg }}</div>
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
  title = "angularaulas";
  nomes = [
    new Pessoa(1, "Beto", 90),
    new Pessoa(2, "Paulo", 20),
    new Pessoa(3, "Fulano", 40),
    new Pessoa(4, "Ciclano", 60),
    new Pessoa(5, "Mae", 90),
    new Pessoa(6, "Joao", 5),
  ];
  nomePrincipal = this.nomes[0];

  //Aviso
  showAviso = true;
  avisoMsg = "Estem é um aviso";
}
```


Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Condicionais

## Se tiver mais de dois nomes, aparece uma messagem se não, ficará sem mensagem

app.component.ts

```js
import { Component } from "@angular/core";
import { Pessoa } from "./pessoa";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  /*Array com objetos */
  nomes = [
    new Pessoa(1, "Bonieky", 90),
    new Pessoa(2, "Paulo", 20),
    new Pessoa(3, "Fulano", 20),
    new Pessoa(4, "Ciclano", 20),
    new Pessoa(5, "Beltrano", 20),
    new Pessoa(6, "Joao", 5),
  ];
  nomePrincipal = this.nomes[0];
}
```

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
    } else this.idade > 80 && this.idade <= 80; // Faça assim nesta linha
    {
      return 'Super Sayadin';
    }
  }
}

```

app.component.html

```js
<h1>Nome principal: {{ nomePrincipal.nome }}</h1>

<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<p *ngIf="nomes.length > 2">Tem muitos nomes cadastrados</p>

```

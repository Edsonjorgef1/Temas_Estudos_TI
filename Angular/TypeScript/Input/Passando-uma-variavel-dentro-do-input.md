## Passando uma variavel dentro do input

app.component.ts

```js
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  nome = "Beto"; // Variavel
}
```

app.component.html

```js
<input type="text" value="{{ nome }}" />
```

## Passando uma variavel, dentro do input de um array

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li *ngFor="let item of nomes" style="color: #ff0000">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<p *ngIf="nomes.length > 2">Tem muitos nomes cadastrados</p>

<div *ngIf="showAviso">{{ avisoMsg }}</div>

<input type="text" value="{{ nomePrincipal.nome }}" />

```

app/app.component.ts

```js
import { Component } from "@angular/core";
import { Pessoa } from "./pessoa";

@Component({
  selector: "app-root",
  styleUrls: ["./app.component.css"],
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "angularaulas";
  /*Array com objetos */
  nomes = [
    new Pessoa(1, "Beto", 90),
    new Pessoa(2, "Paulo", 20),
    new Pessoa(3, "Fulano", 20),
    new Pessoa(4, "Ciclano", 20),
    new Pessoa(5, "Beltrano", 20),
    new Pessoa(6, "Joao", 5),
  ];
  nomePrincipal = this.nomes[1];
}
```

app/pessoa.ts

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

## Também posso passar uma variavel, desta forma, 1

app/app.component.html

```js
<input type="text" [value]="msgTexto" />
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
  msgTexto = "Estem é um aviso";
}
```

## Também posso passar uma variavel, desta forma, 2

app/app.component.html

```js
<input type="text" bind-value="msgTexto" />
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
  msgTexto = "Estem é um aviso";
}
```

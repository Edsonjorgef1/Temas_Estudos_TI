Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Clicando e trocando a cor

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
  corPrincipal = "#FF0000";

  /*Criando uma função */
  trocarCor = (cor: string) => {
    return (this.corPrincipal = cor);
  };
}
```

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li *ngFor="let item of nomes" [style.color]="corPrincipal">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<!-- <button (click)="corPrincipal = '#0000FF'">Aperte aqui</button> -->

<!-- ou -->

<button (click)="trocarCor('#0000FF')">Colocar Azul</button>
<button (click)="trocarCor('#FF0000')">Colocar Vermelho</button>
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

## Criar eventos de click que compartilham informações inclusive com loops com coisas dinamicas, vamos criar um evento de click, ele irá mandar o item do proprio loop, o item do proprio loop será uma classe de uma própria pessoa

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li
    *ngFor="let item of nomes"
    [style.color]="corPrincipal"
    (click)="clicou(item)"
  >
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>
<!-- Clicou trocou o title -->
<button (click)="title = 'Testando 1,2,3'">Mudar Titulo</button>
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
    } else this.idade > 80 && this.idade <= 80;
    {
      return 'Super Sayadin';
    }
  }
}
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
  corPrincipal = "#FF0000";

  /*Criando uma função */
  clicou = (pessoa: Pessoa) => {
    // return alert('Clicou em: ' + pessoa.nome);
    return alert("Clicou em um " + pessoa.getTipo());
  };
}
```

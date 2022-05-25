Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Topicos

.Imput, algumas forma do value input

.Utilizando uma expressão, somátoria com o value

.Imagem, abrindo uma imgem, com uma url

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

<!-- Formas de como utilizar o value no input -->
<!-- <input type="text" value="nome" /> -->
<!-- ou -->
<!-- <input type="text" value="{{ nomePrincipal.nome }}" /> -->
<!-- ou -->

<!-- Passando uma empressão -->
<input type="text" [value]="1 + 2" />

<!-- Passando uma variavel -->
<input type="text" [value]="nomePrincipal.nome" />
<!-- ou -->
<!-- Passando uma variavel -->
<input type="text" bind-value="nomePrincipal.nome" />

<!-- Condicional, baseado em alguma variavel especifica -->
<input type="text" [disabled]="true" />

<!-- ou -->

<input type="text" [disabled]="hideInput" />

<br />
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

  //Criando uma variavel
  hideInput = false;

  //Imagem
  imagem = "https://www.google.com.br/google.jpg";
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

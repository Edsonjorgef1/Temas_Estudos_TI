Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Quando você digita alguma coisa em algum canto o que acontece, o que faz para pegar este valor, como faz o procedimento em relação ao teclado

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal }}</p>

<!-- Valor que ira aparecer no campo quando carregar -->
<!--(input)="trocarNome(nomeInput.value)"  // Desta forma com o (input), quando você clica no teclado ele ja digita  -->
<!--(keyup)="trocarNome(nomeInput.value)"  // Desta forma com o (keyup), só quando eu troca a tela que ele faz o efeito, a questão de memoria este é melhor pois só vai trocar a letra depois que soltar a tecla  -->
<!-- (keyup.enter)="trocarNome(nomeInput.value)" // Ele só irá escrever o que foi digitado depois de fazer o Enter do teclado-->
<input
  #nomeInput
  type="text"
  [value]="nomePrincipal"
  (keyup.enter)="trocarNome(nomeInput.value)"
/>

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
    } else this.idade > 80 && this.idade <= 80; // Faça assim nesta linha
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
  nomePrincipal = "Beto";

  /*Criando uma função */
  trocarNome = (novoNome: string) => {
    return (this.nomePrincipal = novoNome);
  };

  corPrincipal = "#FF0000";

  /*Criando uma função */
  clicou = (pessoa: Pessoa) => {
    // return alert('Clicou em: ' + pessoa.nome);
    return alert("Clicou em um " + pessoa.getTipo());
  };
}
```

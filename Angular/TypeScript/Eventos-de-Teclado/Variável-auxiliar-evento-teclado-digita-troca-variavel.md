Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Variável auxiliar de envento de teclado, um recurso bem legal do angular, quando digita troca a minha variavel

No angular ele só atualiza variaveis detalhes quando vem acoplado com um evento
especifico, tem que acontecer um evento específico, que agente determino que ele
aconteça para que o angular entre em ação e faça alguma coisa

app.component.html

```js
<h1>{{ title }}</h1>
<h4>Sub-legenda legal</h4>

<p>Total de nomes: {{ nomes.length }}</p>
<p>Nome Principal: {{ nomePrincipal }}</p>

<!-- <input type="text" #nomeInput (keyup)="(0)" /> -->

<!-- Aqui você digita o que você desejar, depois clicar em enter e já irá ficar na variavel -->
<!-- <input type="text" #nomeInput (keyup.enter)="trocarNome(nomeInput.value)" /> -->

<!-- Agora eu quero limpar o campo depois que der o enter -->
<!-- (keyup)="(0)" // Se quiser ver o que está escrevendo, ai depois de clicar no enter, apaga a variavel -->
<input
  type="text"
  #nomeInput
  (keyup)="(0)"
  (keyup.enter)="trocarNome(nomeInput.value); nomeInput.value = ''"
/>

<!-- Basta adicionar o nomeInput.value já consigo buscar os meus dados -->
<p>Variavel: {{ nomeInput.value }}</p>

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

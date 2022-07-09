
## LIsta Array String

A diretiva estrutural *ngFor, parte da sintaxe de templates do Angular, funciona de forma similar a estrutura de laço for … of, do JavaScript.

Utilizamos a diretiva *ngFor sempre que precisamos replicar um elemento HTML na interface de forma dinâmica. Esse cenário é bem comum quando precisamos criar diversos elementos HTML a partir dos itens de uma coleção. Veremos um exemplo abaixo.


Relembrando a estrutura for … of
A estrutura de repetição for … of do JavaScript foi introduzida pelo ECMAScript 2015, o ES6, e permite percorrermos objetos iteráveis, tais como Arrays, Maps e Sets. Com ele podemos declarar uma variável local, que no código abaixo se chama livro, e utilizá-la para armazenar os itens da coleção, um por vez, a cada iteração do for.


```js
let livros = [
   'Como morrem os pobres e outros ensaios',
   'A revolução dos bichos',
   '1988'
];

for (let livro of livros) {
  console.log(livro);
}
```
O código acima imprimirá todos os livros no console, na ordem em que estão listados no array:

```js
Como morrem os pobres e outros ensaios
	A revolução dos bichos
1988
```
Para testarmos o *ngFor crie um componente chamado ListaLivros executando o comando a seguir.

```js
ng generate component ListaLivros
```

Abra o arquivo lista-livros.component.ts e insira o código abaixo:

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-lista-livros',
  templateUrl: './lista-livros.component.html',
  styleUrls: ['./lista-livros.component.css']
})
export class ListaLivrosComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }

  public livros = [
    'Como morrem os pobres e outros ensaios',
    'A revolução dos bichos',
    '1988'
 ];

}
```
Nota: Como vimos no curso Exibindo dados no template, para que o template do componente seja capaz de acessar atributos da classe do componente, esses atributos precisam ter visibilidade pública, definida pela palavra chave public.
No template do nosso componente (arquivo lista-livros.component.html) utilizamos a diretiva estrutural *ngFor para replicar uma determinada estrutura HTML, no caso o elemento li:

```js
<ul>
 <li *ngFor="let livro of livros">{{ livro }}</li>
</ul>
```
A partir desse momento, de forma invisível, o Angular se encarregará de gerar a estrutura HTML final, que será renderizada pelo browser:

```js
<ul>
 <li>Como morrem os pobres e outros ensaios</li>
 <li>A revolução dos bichos</li>
 <li>1988</li>
</ul>
```
Nota: Assim como a diretiva *ngIf, vista na aula anterior, a diretiva *ngFor também pode ser utilizada em conjunto com qualquer elemento HTML ou componentes Angular.
Para exibir o código no navegador, abra o arquivo app.component.html e insira o seguinte código:

```js
<app-lista-livros></app-lista-livros>
```

## ngFor, Lista 2, Array, com strings

app.component.html

```js
<ul>
  <li *ngFor="let nome of nomes" style="color: #ff0000">
    {{ nome }}
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
  /*Array, com strings*/
  nomes = ["beto", "Valdir", "Elio"];
  /*nomes = [  "0" ,   "1"   ,  "2"  ]*/
}
```


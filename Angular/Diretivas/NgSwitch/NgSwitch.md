Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgSwitch

Um Conjunto de diretivas que alternam entre visões alternativas. Ele é igual
switch case do javascript

src/app/diretivas-estruturais/diretivas-estruturais.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-diretivas-estruturais',
  templateUrl: './diretivas-estruturais.component.html',
  styleUrls: ['./diretivas-estruturais.component.scss'],
})
export class DiretivasEstruturaisComponent implements OnInit {
  public nome: string = 'dener';

  constructor() {}

  ngOnInit(): void {}
}
```

src/app/diretivas-estruturais/diretivas-estruturais.component.html

```js
<input type="text" [(ngModel)]="nome" />
<div [ngSwitch]="'nome'">
  //Aqui é o primeiro caso
  <p *ngSwitchCase="'dener'">Dener</p>
  //Aqui é o segundo caso
  <p *ngSwitchCase="'nay'">Nay</p>

  <!-- Da para fazer nossas validações, com este Default -->
  <p *ngSwitchDefault>Deu ruim sua busca</p>
</div>
```
## ngSwitch, outro exemplo

A diretiva estrutural ngSwitch é análoga a estrutura de controle de fluxo switch, que aprendemos em algoritmos e lógica de programação. Com ela, em lugar de utilizarmos múltiplos ngIf podemos utilizar uma única diretiva ngSwitch com múltiplos ngSwitchCase.

Relembrando a estrutura switch

```js
let livro = 'O Chamado de Cthulhu';
let autor;

switch (livro) {
 case 'O Chamado de Cthulhu':
   autor = 'H. P. Lovecraft'
   break;

 case 'A Tormenta de Espadas':
   autor = 'George R. R. Martin';
   break;

 case '1984':
   autor = 'George Orwell';
   break;

 case 'O Silmarillion':
   autor = 'Tolkien, J.R.R.';
   break;

 default:
   autor = 'Desconhecido';
   break;
}

console.log(livro);
console.log(autor);
```

No exemplo acima realizamos a comparação da variável livro com os diversos cases do switch. O bloco executado será aquele em que o valor de livro for o mesmo que o do case. Todos os demais serão ignorados. Além disso, ao final da estrutura, definimos uma condição padrão, ou default, que será executada sempre que o valor de livro não for igual a nenhuma das opções anteriores.

O exemplo a seguir imprimirá o resultado:

O Chamado de Cthulhu
H. P. Lovecraft


/********************************************************************************/
Utilizando ngSwitch

A necessidade de uma condicional de múltiplas possibilidades também pode acontecer quando construímos interfaces com o Angular. Nesse caso, utilizamos a diretiva estrutural ngSwitch.

Para esse exemplo vamos criar três componente. São eles: Revista, Livro e Filme. Eles só vão exibir uma mensagem dizendo que o componente foi carregado, dessa forma vamos conseguir vizualizar o funcionamento do ngSwitch.

Execute o código a seguir para criar o componente Revista.

ng generate component Revista

O código do componente Revista (arquivo revista.component.ts) pode ser visto a seguir:


```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-revista',
  templateUrl: './revista.component.html',
  styleUrls: ['./revista.component.css']
})
export class RevistaComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {    }
}
```

Veja agora o código do seu template (arquivo revista.component.html):

```js
<h1>Componente revista carregado com sucesso</h1>
```

A seguir crie o componente Livro utilizando o seguinte comando:

```js
ng generate component Livro
```

O código do componente Livro (arquivo livro.component.ts) pode ser visto a seguir:

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-livros',
  templateUrl: './livros.component.html',
  styleUrls: ['./livros.component.css']
})
export class LivrosComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {   }
}
```

Veja agora o código do seu template (arquivo livro.component.html):

```js
<h1>Componente Livro carregado com sucesso</h1>
```

A seguir crie um novo componente chamado Filme utilizando o seguinte comando:

```js
ng generate component Filme
```

O código do componente Filme (arquivo filme.component.ts) pode ser visto a seguir:

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-filme',
  templateUrl: './filme.component.html',
  styleUrls: ['./filme.component.css']
})
export class FilmeComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {  }

}
```

Veja agora o código do seu template (arquivo filme.component.html):

```js
<h1>Componente Filme carregado com sucesso</h1>
```

Agora para utilizar o ngSwitch vamos criar um componente chamado Produto executando o comando abaixo:

```js
ng generate component Produto
```

Digamos que meu componente Produto pode receber diversos tipos de produto: livro, filme, revista, curso, etc. Com base no tipo desse produto, o componente Produto deve escolher qual componente será exibido para o usuário. Na classe do nosso componente (arquivo produto.component.ts) teremos a seguinte implementação:

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-produto',
  templateUrl: './produto.component.html',
  styleUrls: ['./produto.component.css']
})
export class ProdutoComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }

  public produto = {
    tipo: 'filme',
    titulo: 'Psicopata Americano',
    ano: '2000'
  };

  public setProduto(produto) {
      this.produto = produto;
  }
}
```

Nota: Para fins didáticos um produto foi mockado, escrito manualmente dentro do componente, no atributo produto. Em uma situação de mundo real, esse dado seria passado como parâmetro para o componente através do decorator Input do Angular.
No template do nosso componente Produto (arquivo produto.component.html), utilizando a diretiva ngSwitch para escolher qual componente deve ser instanciado dentro do componente

```js
<div [ngSwitch]="produto.tipo">
 <app-revista *ngSwitchCase="'revista'">  </app-revista>
 <app-livro *ngSwitchCase="'livro'">  </app-livro>
 <app-filme *ngSwitchCase="'filme'">  </app-filme>

 <span *ngSwitchDefault>Produto desconhecido </span>
</div>
```

A diretiva ngSwitch receberá o tipo do produto, que será comparado com cada um dos atributos *ngSwitchCase listados dentro da estrutura. Por fim, caso nenhuma condição seja atendida, o Angular renderizará o elemento span que possui o atributo *ngSwitchDefault.

Nota: Como vimos no curso Exibindo dados no template, envolvemos o atributo ngSwitch com os caracteres [ e ] para que o Angular se encarregue de realizar o binding dos dados da classe do componente com o template. Dessa forma, sempre que o atributo produto da classe for alterado, o Angular executará a comparação e renderizará o componente equivalente.

Para testar este exemplo altere o arquivo app.component.html da seguinte forma:

```js
<app-produto></app-produto>
```

Como o produto que utilizamos no exemplo é do tipo filme, o componente FilmeComponent será carregado:

Componente Filne carregado com sucesso
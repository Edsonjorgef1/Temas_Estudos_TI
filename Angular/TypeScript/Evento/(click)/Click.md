Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Click

✓ Qual elemento vai emitir o evento?
No nosso caso button;

✓ Qual o nome do evento que será emitido pelo elemento?
click!

app.component.ts

```js
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss'],
})
export class AppComponent {
  onClick(event: any) {
    console.log('Recebi um click');
  }
}
```

app.component.html

(click) = Nome do evento

"onClick($event)" = Método do componente

```js
<button (click)="onClick($event)">Me Clica</button>

<router-outlet></router-outlet>
```

## Agora vamos fazer um click, utilizando outro componente

Aqui criaremos o componente

```js
ng g c click-me
```

click-me.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-click-me',
  templateUrl: './click-me.component.html',
  styleUrls: ['./click-me.component.scss'],
})
export class ClickMeComponent implements OnInit {
  onClick() {
    console.log('Recebi um click');
  }

  constructor() {}

  ngOnInit(): void {}
}
```

click-me.component.html

(click) = Nome do evento

"onClick($event)" = Método do componente

```js
<button (click)="onClick()">CLick Me</button>
```

app.component.html

Componente Principal

```js
<app-click-me></app-click-me>

<router-outlet></router-outlet>
```


## Básico do click

app/primeiro-componente/primeiro-componente.component.html

```js
<!-- (evento)="metodo()" -->
<!-- (click)="clicked()" -->

<!-- Clicando em uma div -->
<div class="bg" (click)="clicked()">
  <!-- Clicando em um texto  -->
  <h1 (click)="clicked()">Olá</h1>
  <!-- Clicando em um botton  -->
  <button (click)="clicked()">button</button>
</div>
<button (click)="alertInfo()">Evento</button>
<button (click)="alertInfo('Deu bom Dener')">Evento</button>
```

app/primeiro-componente/primeiro-componente.component.css

```js
.bg {
  background-color: #d43d3d;
}
```

app/primeiro-componente/primeiro-componente.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-primeiro-componente",
  templateUrl: "./primeiro-componente.component.html",
  styleUrls: ["./primeiro-componente.component.css"],
})
export class PrimeiroComponenteComponent implements OnInit {
  // Criando metodo clicked
  clicked(): void {
    window.alert("ola");
  }

  constructor() {}

  ngOnInit() {}
  /*public altertInfo(){
    altert('Deu bom')
  }*/
  /*ou*/
   public alertInfo(valor: string) {
    alert(valor);
  }
}
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

## Clicando e trocando a cor, básico

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li *ngFor="let item of nomes" [style.color]="corPrincipal">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<button (click)="corPrincipal = '#0000FF'">Aperte aqui</button>
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
  nomePrincipal = this.nomes[2];

  corPrincipal = "#FF0000";
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

## Clicando e executando uma função

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
  nomePrincipal = this.nomes[2];
  corPrincipal = "#FF0000";
  // Criando uma função, quando for clicado o botão irá executar está função
  trocarCor = () => {
    this.corPrincipal = "#00FF00";
  };
}
```

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li *ngFor="let item of nomes" [style.color]="corPrincipal">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<button (click)="trocarCor()">Aperte aqui</button>
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

## Clicando e passando parametros

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
  nomePrincipal = this.nomes[2];
  corPrincipal = "#FF0000";
  //
  trocarCor = (cor: string) => {
    this.corPrincipal = cor;
  };
}
```

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li *ngFor="let item of nomes" [style.color]="corPrincipal">
    {{ item.nome }} - {{ item.idade }} anos - {{ item.getTipo() }}
  </li>
</ul>

<button (click)="trocarCor('#0000FF')">Colocar Azul</button>

<button (click)="trocarCor('#FF0000')">Colocar Vermelho</button>
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

## Criando um evento de click no próprio <li>, quando clicar no nome, ele irá aparecer quem foi clicado

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li
    *ngFor="let item of nomes"
    [style.color]="corPrincipal"
    (click)="clicou(item)"
  >
    {{ item.nome }} - {{ item.idade }} anos = {{ item.getTipo() }}
  </li>
</ul>
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

  nomePrincipal = this.nomes[2];

  corPrincipal = "#FF0000";

  clicou = function (pessoa: Pessoa) {
    //alert('Clicou em: ' + pessoa.nome);
    // ou
    alert("Clicou em: " + pessoa.getTipo());
  };
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

## Clicando e trocando o nome da variavel

app/app.component.html

```js
<h1>{{ title }}</h1>
<p>Nome principal: {{ nomePrincipal.nome }}</p>

<ul>
  <li
    *ngFor="let item of nomes"
    [style.color]="corPrincipal"
    (click)="clicou(item)"
  >
    {{ item.nome }} - {{ item.idade }} anos = {{ item.getTipo() }}
  </li>
</ul>
//Clicou trocou o nome da variavel
<button (click)="title = 'Testando 1,2,3'">Mudar Titulo</button>
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

  nomePrincipal = this.nomes[2];

  corPrincipal = "#FF0000";

  clicou = function (pessoa: Pessoa) {
    //alert('Clicou em: ' + pessoa.nome);
    // ou
    alert("Clicou em: " + pessoa.getTipo());
  };
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

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## @input()

Entrada de dados

## Criando Sub Modules

```js
ng g m shared
```

Criar um componete agora a minha pasta shared

```js
ng g c shared/newComponent
```

src/app/shared/new-component/new-component.component.html

```js
<header>
  <h1>Header do App</h1>
</header>
```

src/app/shared/new-component/new-component.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-new-component",
  templateUrl: "./new-component.component.html",
  styleUrls: ["./new-component.component.scss"],
})
export class NewComponentComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";

@NgModule({
  declarations: [NewComponentComponent],
  //Exportando o componente
  exports: [NewComponentComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

## Agora vamos criar um arquivo, na pasta shared

Repare que depois que criar o arquivo ja irá importar o componente criado dentro
do src/app/shared/shared.module.ts src/app/shared/shared.module.ts

Criar um componete agora a minha pasta shared

```js
ng g c shared/input
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [NewComponentComponent, InputComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz automático
  exports: [NewComponentComponent, InputComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

src/app/shared/input/input.component.html

```js
<p>inputCriado Parabéns</p>
```

src/app/shared/input/input.component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-input",
  templateUrl: "./input.component.html",
  styleUrls: ["./input.component.scss"],
})
export class InputComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

## Agora vamos utilizar o @input()

src/app/shared/input/input.component.ts

```js
import { Component, Input, OnInit } from '@angular/core';

@Component({
  selector: 'app-input',
  templateUrl: './input.component.html',
  styleUrls: ['./input.component.scss'],
})
export class InputComponent implements OnInit {
  //Aqui estamos fazendo, a entrada de dados com o @input()
  @Input() public contador: number = 0;

  constructor() {}

  ngOnInit(): void {}
}
```

src/app/shared/input/input.component.html

```js
<p>Contador = {{ contador }}</p>
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";

@NgModule({
  //Inporto o componente, InputComponet, automático
  declarations: [NewComponentComponent, InputComponent],
  //Aqui deve exportar, o InputComponent, pois ele não faz automático
  exports: [NewComponentComponent, InputComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

src/app/app.components.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-root',
  template: ` <app-input [contador]="addValue"> </app-input>
    <br />
     <!-- Criamos um [contador]="recebe está variavel, que no caso ela está iniciando com 10" -->

    <!-- Criando botão, e quando for clicado chama a função add -->
    <button (click)="add()">Add</button>

    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  // Criando vama variavel publica, addValue e tipamos ela em number, que no caso iniciara em 10,
  public addValue: number = 1;

  constructor() {}

  ngOnInit(): void {}
  //Criando uma funcão, add, quando clicar o botão, irá chamar está função, e somar +1
  public add() {
    this.addValue += 1;
  }
}
```

## Agora vamos utilizar o output

Criar um componete agora a minha pasta shared

```js
ng g c shared/output
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";
//Aqui foi importado o componente OutputComponent, automático
import { OutputComponent } from "./output/output.component";

@NgModule({
  declarations: [NewComponentComponent, InputComponent, OutputComponent],
  //Exportando o componente, OutputComponente, tem que fazer isso aqui, o angular não faz automático
  exports: [NewComponentComponent, InputComponent, OutputComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

src/app/shared/output/output.component.ts

```js
import { Component, EventEmitter, OnInit, Output } from '@angular/core';

@Component({
  selector: 'app-output',
  templateUrl: './output.component.html',
  styleUrls: ['./output.component.scss'],
})
export class OutputComponent implements OnInit {
  // Agora vamos aprender como utiliza o output
  //Agora está pronto para exportar, esta emitindo os dados
  @Output() public enviarDados = new EventEmitter();

  public list: Array<{ nome: string; idade: number }> = [
    { nome: 'Beto', idade: 34 },
    { nome: 'Mae', idade: 27 },
    { nome: 'Pai', idade: 21 },
  ];
  constructor() {}

  ngOnInit(): void {}
  // ver o posicionamento atravpes do [event]
  public getDados(event: number) {
    //Agora vamos enviar
    this.enviarDados.emit(this.list[event]);
    // Teste
    // console.log(this.list[event]);
  }
}
```

src/app/shared/output/output.component.html

```js
<!-- Index, ele serve para ver o posicionamento do -->
<p *ngFor="let item of list; let i = index">
  {{ item.nome }}
  {{ item.idade }}
  <button (click)="getDados(i)">Enviar dados</button>
</p>
```

app/app-component.ts

```js
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-root",
  template: ` <!-- Componente app-output -->
    <app-output></app-output>

    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  constructor() {}

  ngOnInit(): void {}
}
```

## Agora vamos resgatar os dados do outro componente

app/app-component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-root',
  template: ` <!-- Componente app-output -->

    <ng-template [ngIf]="getDados">
      <h1>{{ getDados.nome }}</h1>
      <h2>{{ getDados.idade }}</h2>
    </ng-template>
    <!-- Recebendo o evento do meu output -->
    <!-- SetDados captura meu evento, apartir do ($event) -->
    <app-output (enviarDados)="setDados($event)"></app-output>

    <router-outlet></router-outlet>`,
})
export class AppComponent implements OnInit {
  //Este valor indefined, que deixa mecher nos valores dele
  public getDados: { nome: string; idade: number } | undefined;
  constructor() {}

  ngOnInit(): void {}
  public setDados(event: { nome: string; idade: number }) {
    this.getDados = event;
  }
}
```

src/app/shared/output/output.component.html

A partir do momento que clicar no botão ele vai emitir um dado para fora, esta
dado vai ser capturado por nosso evento, e este evento vai popular nosso get
Itens

```js
<!-- Index, ele serve para ver o posicionamento do -->
<p *ngFor="let item of list; let i = index">
  {{ item.nome }}
  {{ item.idade }}
  <button (click)="getDados(i)">Enviar dados</button>
</p>
```

src/app/shared/output/output.component.ts

```js
import { Component, EventEmitter, OnInit, Output } from '@angular/core';

@Component({
  selector: 'app-output',
  templateUrl: './output.component.html',
  styleUrls: ['./output.component.scss'],
})
export class OutputComponent implements OnInit {
  // Agora vamos aprender como utiliza o output
  //Agora está pronto para exportar, o enviarDados
  @Output() public enviarDados = new EventEmitter();

  public list: Array<{ nome: string; idade: number }> = [
    { nome: 'Beto', idade: 34 },
    { nome: 'Mae', idade: 27 },
    { nome: 'Pai', idade: 21 },
  ];
  constructor() {}

  ngOnInit(): void {}
  // ver o posicionamento atravpes do [event]
  public getDados(event: number) {
    //Agora vamos enviar
    this.enviarDados.emit(this.list[event]);
    // Teste
    // console.log(this.list[event]);
  }
}
```

src/app/shared/shared.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
import { NewComponentComponent } from "./new-component/new-component.component";
import { InputComponent } from "./input/input.component";
//Aqui foi importado o componente OutputComponent, automático
import { OutputComponent } from "./output/output.component";

@NgModule({
  declarations: [NewComponentComponent, InputComponent, OutputComponent],
  //Exportando o componente, OutputComponente, tem que fazer isso aqui, o angular não faz automático
  exports: [NewComponentComponent, InputComponent, OutputComponent],
  imports: [CommonModule],
})
export class SharedModule {}
```

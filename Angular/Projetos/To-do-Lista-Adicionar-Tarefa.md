Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## To-do, Lista de Tarefa

Clicou irá fazer uma lista das suas tarefas

app.components.ts

```js
import { Component } from "@angular/core";
import { Tarefa } from "./tarefa";

@Component({
  selector: "app-root",
  templateUrl: "./app.component.html",
})
export class AppComponent {
  title = "Lista de Tarefas";

  tarefas = [new Tarefa("Fazer Bolo"), new Tarefa("Testar o app")];

  /*Criando uma função */
  addTarefa = (tarefa: string) => {
    return this.tarefas.push(new Tarefa(tarefa));
  };
}
```

tarefa.ts

```js
export class Tarefa {
  public titulo: string;

  constructor(titulo: string) {
    this.titulo = titulo;
  }
}
```

tarefa.spec.ts

```js
import { Tarefa } from "./tarefa";

describe("Tarefa", () => {
  it("should create an instance", () => {
    expect(new Tarefa()).toBeTruthy();
  });
});
```

app.component.html

```js
<h1>{{ title }}</h1>

<input
  type="text"
  #newTarefa
  (keyup)="(0)"
  (keyup.enter)="addTarefa(newTarefa.value); newTarefa.value = ''"
/>
<button (click)="addTarefa(newTarefa.value); newTarefa.value = ''">
  Adicionar
</button>

<ul>
  <li *ngFor="let tarefa of tarefas">
    {{ tarefa.titulo }}
  </li>
</ul>
```

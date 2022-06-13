Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgModules

Um module é um mecanismo para agrupar components, diretivas, pipes e serviços
relacionados, de forma a combinar com outros módulos para criar um aplicativo.

Uma aplicação angular pode ser pensada como um quebra cabeça. Onde cada bloco,
tem como objetivo fornecer uma funcionalidade ou recurso específico.

Construimos um software como se fosse um quebra cabeça e conforme esse quebra
cabeça cresce, fica difícil e oneroso a sua manutenção. Por isso adotamos alguns
modelos de arquitetura e construção de software. O Angular fornece uma boa
maneira de organizar esses blocos de forma simples e eficaz usando módulos
(também conhecidos como ngModules)

Anatomia (ngModule)

@NgModule({ declarations: [], imports: [], exports: [], providers: [],
bootstrap: [], })

Declarations = serve para declarar nossos componentes dentro daquele modulo
especifico

import = ele importa funcionalidades de outros componentes

export = ele serve para exportar o seu modulo alem de declarar

providers = aonde você quer fazer uma requeisição externa temos que declarar o
nosso service dentro do ngmodel para utilizar nossa injeção de dependencia

bottstrap = utilizar em nosso componente principal, ele é a inicialização do
nosso modulo, que fica no app.component no centro principal de nossa aplicação

## Exemplo:

Importando FormsModule, para funcionar o ngModules

src/modules/home/home.module.ts

```js
import { NgModule } from "@angular/core";
import { CommonModule } from "@angular/common";
//Componentes
import { ComponentsComponent } from "./components/components.component";
import { HeaderComponent } from "./components/header/header.component";
import { TodoButtonDeleteAllComponent } from "./components/todo-button-delete-all/todo-button-delete-all.component";
import { TodoInputAddItensComponent } from "./components/todo-input-add-itens/todo-input-add-itens.component";
import { TodoListComponent } from "./components/todo-list/todo-list.component";
//Page
import { HomeComponent } from "./pages/home/home.component";
import { FormsModule } from "@angular/forms";

@NgModule({
  declarations: [
    ComponentsComponent,
    HeaderComponent,
    TodoButtonDeleteAllComponent,
    TodoInputAddItensComponent,
    TodoListComponent,
    HomeComponent,
  ],
  //Importando formsModule, para funionar o ngModel, que está sendo utilizado no html
  imports: [CommonModule, FormsModule],
})
export class HomeModule {}
```

src/modules/home/components/todo-list/todo-list.component.html

```js
<section>
  <ul>
    <!-- Este i, vamos utilizar ele quando fomos deletar -->
    <li *ngFor="let item of taskList; let i = index">
      <input type="checkbox" [(ngModel)]="item.checked" />
      <input type="text" [(ngModel)]="item.task" />

      <button>
        <img src="assets/icons/icon-trash.svg" alt="" />
      </button>
    </li>
  </ul>
</section>

<app-todo-input-add-itens></app-todo-input-add-itens>
<app-todo-button-delete-all></app-todo-button-delete-all>
```

src/app/modules/model/task-list.ts

```js
export interface TaskList {
  task: string;
  checked: boolean;
}
```

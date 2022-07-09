Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Loading

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
<!-- Aqui se tiver,  !taskList.length, isso ! siginifica false, se tiver false faça o loading  -->
<section [ngClass]="{ loading: !taskList.length }">
  <!-- Desta forma, ngIf, se meu tasList, não tiver nada, minha lista não ira aparecer -->

  <ul *ngIf="taskList.length">
    <!-- Se tiver com valor adicionar a lista -->

    <li *ngFor="let item of taskList; let i = index">
      <!-- Este i, vamos utilizar ele quando fomos deletar -->

      <input type="checkbox" [(ngModel)]="item.checked" />
      <input type="text" [(ngModel)]="item.task" />

      <button>
        <img src="assets/icons/icon-trash.svg" alt="" />
      </button>
      <!-- Teste -->
      <!-- {{ item | json }} -->
    </li>
  </ul>
</section>

<app-todo-input-add-itens></app-todo-input-add-itens>
<app-todo-button-delete-all
  *ngIf="taskList.length"
></app-todo-button-delete-all>

```

src/app/modules/model/task-list.ts

```js
export interface TaskList {
  task: string;
  checked: boolean;
}
```

src/modules/home/components/todo-list/todo-list.component.ts

```js
import { Component, OnInit } from '@angular/core';

//Interface
import { TaskList } from '../../model/task-list';

@Component({
  selector: 'app-todo-list',
  templateUrl: './todo-list.component.html',
  styleUrls: ['./todo-list.component.scss'],
})
export class TodoListComponent implements OnInit {
  //public taskList: Array<{ task: string; checked: boolean }> = [];
  //Adicinando a taskList
  public taskList: Array<TaskList> = [
    //Se aqui tiver, sem nada o loading, será visualizado
    { task: 'Minha nova Task', checked: true },
    { task: 'Minha nova Task 2', checked: false },
  ];

  constructor() {}

  ngOnInit(): void {}
}
```

src/modules/home/components/todo-list/todo-list.component.scss

```js
@import "../../../../../dist/scss/variables.scss";

section {
  width: 100%;
  min-height: 250px;

  background: $secondary-background-color;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.08);

  margin-top: 20px;

  // Loading
  &.loading {
    background-image: url("../../../../../assets/img/bg-task.png");
    background-repeat: no-repeat;
    background-position: center 30px;
  }

  ul {
    padding: 20px;

    li {
      display: flex;
      justify-content: space-between;
      align-items: center;

      margin-bottom: 10px;

      input {
        &[type="checkbox"] {
          width: 5%;
        }
        &[type="text"] {
          width: 80%;
          padding: 5px 10px;
          border: none;

          font-size: 16px;
          color: $primary-text-color;
          &.checked {
            text-decoration: line-through;
          }
        }
      }

      button {
        width: 5%;
        background: none;
        border: none;
      }
    }
  }
}
```

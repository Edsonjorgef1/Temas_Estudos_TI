Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Criando uma interface

A iterface ajuda a fazer a parte de comunicação entre metodos, se fomos criar um
novo item na nossa lista,um novo nó na nossa lista, para ficar batendo nas
nossas informações

```js
ng g interface modules/home/model/TaskList
```

src/app/modules/home/model/TaskList

```js
export interface TaskList {}
```

src/app/home/components/todo-list/todo-list.component.ts

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
  public taskList: Array<TaskList> = [];
  constructor() {}

  ngOnInit(): void {}
}
```

app/home/modules/home/model/task-list.ts

```js
export interface TaskList {
  task: string;
  checked: boolean;
}
```
